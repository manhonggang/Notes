_This article was originally posted on [Kongregate’s Developer Blog](https://developers.kongregate.com/)._

Part I
------

I’ve given a few talks in the past about the appeal and general mechanics of idle games, but what if you actually wanted to make one? Theory and patterns are nice, but there’s some complicated math running behind it. And how on earth do you balance a game that has insanely large numbers?

This article is Part I of what will be a three-part series detailing topics covered in my [most-recent talk](http://www.slideshare.net/AnthonyPecorella/quest-for-progress-gdc-europe-2016). Part I discusses core ideas of growth, cost, prestige, and generator balancing. Part II will look into alternate growth methods (especially derivative-based). Part III will look at prestige cycles and balance.

The models for all of the charts produced in these articles are [available as spreadsheets](http://kon.gg/idle-math-spreadsheets). Please feel free to duplicate, peruse, experiment, extend, etc.!

Let’s start by specifying some terminology to make talking about this easier.

*   **Primary Currency:** This is the main number that is being incremented, generally the goal of the game. Usually it’s some form of money.
*   **Generator:** The items in the game that produce primary currency. The rate of production, or income, is measured as currency per second.
*   **Primary Exchange Currency:** In some cases generators produce a different currency that is exchanged for primary currency. For example, in Clicker Heroes the generators produce DPS, which is then converted into gold by killing monsters. That layer of separation can give you a bit more control over the growth of the primary currency in the game, since you can modify the “exchange rate” over time.
*   **Multiplier:** Any of a variety of upgrades that multiplies your generator power. These can be explicit upgrades, based on number of generators owned, etc. Their purpose is to (temporarily) get production closer to, or ahead of, costs.
*   **Prestige:** A reset of most elements of the game (especially generators and multipliers), but gaining currency (prestige currency) and/or persistent multipliers to accelerate the next time through. Similar to a “New Game+”.

At the most basic level, idle games are a seesaw between production rates and costs. Early on in a run, your production will exceed costs while eventually costs will become prohibitive. This is typically accomplished by having costs grow exponentially while production grows at a linear or polynomial rate. To put that into formulas:

![cost_{next} = cost_{base} \times (rate_{growth})^{owned}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-94c5e6e8536a6369b8676ea4d139d669_l3.svg "Rendered by QuickLaTeX.com")

![production_{total} = (production_{base} \times owned) \times multipliers](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-f4030b41551558374dc7c40670819670_l3.svg "Rendered by QuickLaTeX.com")

With AdVenture Capitalist Lemonade Stands, the ![rate_{growth} = 1.07](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-59700d3c21494b4829c7e19431ac7e3f_l3.svg "Rendered by QuickLaTeX.com"), ![cost_{base} = 4^*](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-121b7168c898069b123829adfda4b355_l3.svg "Rendered by QuickLaTeX.com"), and ![production_{base} = 1.67/sec](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-22ec616d3e9ed33e71126253ef732676_l3.svg "Rendered by QuickLaTeX.com"). So if you own 10 Lemonade Stands:

![cost_{next} = 4 \times (1.07)^{10} = 7.87](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-404c24abef93f5b2a788aba5e6412d93_l3.svg "Rendered by QuickLaTeX.com")

Meanwhile, the production rate is:

![production_{total} = (1.67 \times 10) \times 1 = 16.7 / sec](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-99063a4d5233a208b6c4b4d9fb86f003_l3.svg "Rendered by QuickLaTeX.com")

![^*](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-23d72291ecff8dadcee086f6970c5c7b_l3.svg "Rendered by QuickLaTeX.com")It’s technically 3.738, since you get the first one for free and it’s actually the second one that costs 4.

Here are the actual values for AdVenture Capitalist (thank you AdCap wiki!):

![](https://cdn1.kongcdn.com/assets/files/0001/8435/anthony_idle_1.png)

So early on you’re earning well beyond the cost of a new generator every second. Let’s look at that in graph form. Note that when you own 25 and 50 Lemonade Stands, the rate gets a (stacking) x2 multiplier.

![](https://cdn1.kongcdn.com/assets/files/0001/8436/anthony_idle_2.png)

And we can see a slightly bigger picture if we use a log scale y-axis.

![](https://cdn4.kongcdn.com/assets/files/0001/8437/anthony_idle_3.png)

Early on, your production rate is high and you can keep buying, and the multipliers bump you back up whenever it gets close. But eventually the costs become overwhelming, and the time you would have to wait to be able to afford the next generator gets prohibitively long.

Mathematically, exponential growth (anything of the form ![n^x](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-5332b4c9aabb753714164e3ba1172d65_l3.svg "Rendered by QuickLaTeX.com"), for ![n > 1](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-2bbc634b95086614c85d16b5a6aaa05f_l3.svg "Rendered by QuickLaTeX.com")) will eventually catch and far exceed any polynomial growth (![x^k](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-81e025d46b78edcab0363d17fe2192ae_l3.svg "Rendered by QuickLaTeX.com")) no matter how big ![k](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-3422b6bb5c160593658b7c39425d9880_l3.svg "Rendered by QuickLaTeX.com") is or how small ![n](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-b170995d512c659d8668b4e42e1fef6b_l3.svg "Rendered by QuickLaTeX.com") is. (_Thank you pickten for noticing I wrote these backwards at first!_) This can take a very long time in some cases, but that’s where balancing comes in. (If you want a great overview about tiers of quickly growing functions, check out [this post](https://www.reddit.com/r/incremental_games/comments/2ztcfk/linear_polynomial_exponential_and_more_growth/) by Eclipse1agg, the developer of [True Exponential](http://angarg12.github.io/TrueExponential/).)

In this example, once things really start to slow down, you would be looking to do a prestige to multiply your production rate. Doing that looks like this, with each successive prestige sliding up on the graph. The result is that each prestige allows the player to get farther through the cost curve before falling behind.

[![](https://cdn1.kongcdn.com/assets/files/0001/8438/anthony_idle_4.png)](http://angarg12.github.io/TrueExponential/)

But that’s for a single generator. What happens when you have multiple generators, each with different costs and rates? Now the player has choices about what to invest in, and things get more complicated. Fortunately, we can model optimal behavior too! In this model we define “optimal” as having the best income:cost ratio, and we determine that at every purchase opportunity.

Players aren’t going to follow this exactly because the optimal choice will often be far too micromanage-y for a human. “Buy one Generator 2, then three Generator 1s, then a Generator 3, then another Generator 1,” etc. Instead, players usually buy in bulk to simplify the decision process…or to be super OCD (always keeping at multiples of 100). But over the long run, players will roughly be in this ballpark.

Here’s what it looks like for the first 5 generators in AdVenture Capitalist, with x2 multipliers kicking in when you own 25 and 50 of a generator. You can see the expected spikes in purchases right around 25 and 50 multipliers kicking in, since those are temporarily overvalued. _Note: this model simplifies income to be per-second instead of requiring a timer to complete, so higher-end, slower generators get over-favored._

[![](https://cdn1.kongcdn.com/assets/files/0001/8439/anthony_idle_5.png)](http://angarg12.github.io/TrueExponential/)

If we look at a log scale of income rates, though, you’ll notice that the newest generator is nearly always dominant once it can be purchased. That’s not very interesting for the player, though. It means that older generators are largely irrelevant and removes any interesting decisions. Even if smaller generators are technically “optimal,” they may not matter. For example, it may be that you can buy a lemonade stand that generates 10 currency/sec for 5 currency or a car wash that generates 10,000 currency/sec for 7,500 currency. Lemonade is a better deal, but as a player you’re not going to “feel” the impact and so it doesn’t seem worth purchasing, or perhaps more accurately not worth the effort to consider purchasing.

[![](https://cdn2.kongcdn.com/assets/files/0001/8447/anthony_idle_6.png)](http://angarg12.github.io/TrueExponential/)

However, even with a simple model like this one, we can start to emulate the shifting priorities of the various generators. In the above image we don’t have any purchasable multiplier upgrades, and every generator gets the same multiplier count bonuses shown in the table below (only Gen 1 hits 100):

[![](https://cdn2.kongcdn.com/assets/files/0001/8444/anthony_idle_7.png)](http://angarg12.github.io/TrueExponential/)

If we modify these numbers and keep everything else the same (including still not having any purchasable upgrades), we can create a very different picture. We’ll use these multiplier values instead:

[![](https://cdn4.kongcdn.com/assets/files/0001/8445/anthony_idle_8.png)](http://angarg12.github.io/TrueExponential/)

And here’s the resulting income graph:

[![](https://cdn3.kongcdn.com/assets/files/0001/8446/anthony_idle_9.png)](http://angarg12.github.io/TrueExponential/)

Now that’s much more interesting! As you progress through the game, different generators take priority and have the biggest impact on income. The player gets to try to identify these priorities (they won’t always be obvious right away), and this provides more variety and less predictability. And if you have purchasable upgrades, you have even more options for providing this sort of variation for the players.

**BONUS CONTENT!**

While putting all this together, I derived two very useful formulas that will save you from brute-forcing with some lengthy for-loops. The first will calculate the cost of bulk-buying generators, the second will calculate the max generators you can buy with your current funds. These will only work for simple exponential growth that doesn’t have shifting costs or exponents, so make sure your particular application works for it. For both of these, the variables are:

![n](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-b170995d512c659d8668b4e42e1fef6b_l3.svg "Rendered by QuickLaTeX.com") = the number of generators to buy  
![b](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-f56d50c26583f9a035ff6b4e3c0ca5c0_l3.svg "Rendered by QuickLaTeX.com") = the base price  
![r](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-c409433a9e2dfcdb83360a974d243f18_l3.svg "Rendered by QuickLaTeX.com") = the price growth rate exponent  
![k](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-3422b6bb5c160593658b7c39425d9880_l3.svg "Rendered by QuickLaTeX.com") = the number of generators currently owned  
![c](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-41a04eeea923a1a0c28094a8a4680525_l3.svg "Rendered by QuickLaTeX.com") = the amount of currency owned

![cost = b * \frac{r^k(r^n-1)}{r-1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6056c454ef70ae1185e463a296a6143e_l3.svg "Rendered by QuickLaTeX.com")

![max = floor(log_r(\frac{c(r-1)}{b(r^k)}+1))](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-c29321bc2abb7cb020b68f418d1b1c34_l3.svg "Rendered by QuickLaTeX.com")

Or, if your language can’t do a non-standard ![log](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-8be4d2112cc5843c884521b1309c65d5_l3.svg "Rendered by QuickLaTeX.com") base, you can use a standard ![log](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-8be4d2112cc5843c884521b1309c65d5_l3.svg "Rendered by QuickLaTeX.com") or ![ln](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-97f71e96dc481f3a382e1c8588930917_l3.svg "Rendered by QuickLaTeX.com") and divide it like this:

![max = floor(\frac{log(\frac{c(r-1)}{b(r^k)}+1)}{log(r)})](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-87da66f03ffccb19bcc8c3fc4f831b13_l3.svg "Rendered by QuickLaTeX.com")

Part II
-------

In Part I of this three-part series, we looked at some of the standard math behind rapid-growth idle games, primarily at the relationships between exponential and polynomial growth and some methods of checking and adjusting the balance of the various generators over time.

In Part II we’re going to explore a different option for growth outside of the Cookie Clicker model that the vast majority of idle games use these days.

In the “standard” model, there is a primary ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com") and a bunch of generators (![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com"), ![\color{BurntOrange}{Gen 2}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-fdba23d3ef1d71b253e382380f168c2d_l3.svg "Rendered by QuickLaTeX.com"), etc.) that produce that ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com"). In AdVenture Capitalist these are the investments generating cash. In Clicker Heroes these are the heroes generating damage, which is then converted into gold.

![](https://cdn3.kongcdn.com/assets/files/0001/8771/chrome_2016-10-28_14-33-49.jpg)

But who says that generators have to produce primary ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com")? What happens if generators generate other generators, like this?

![](https://cdn4.kongcdn.com/assets/files/0001/8770/chrome_2016-10-28_14-33-38.jpg)

You have a single generator producing the ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com") and then a cascading chain of generators producing the previous tier. So ![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com") is the rate at which ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com") is generated. ![\color{BurntOrange}{Gen 2}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-fdba23d3ef1d71b253e382380f168c2d_l3.svg "Rendered by QuickLaTeX.com") is the rate at which ![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com") is generated, and so on. Anyone else getting twitchy calculus flashbacks? Good, because you should: these are derivatives! _(Note: if you don’t know or remember calculus, don’t worry — you’re about to learn some!)_

Let’s say for a second that a single generator (![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com")) produces one ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com") (the y-axis, representing total ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com")) each second (the x-axis, representing total time). We’ll graph cash in green (obvi!) and you’ll see the single ![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com") generator in blue. So over time the number of ![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com")s doesn’t change, and each second we gain 1 ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com").

![](https://cdn1.kongcdn.com/assets/files/0001/8773/chrome_2016-10-28_14-46-03.jpg)

Now let’s say we have a single ![\color{BurntOrange}{Gen 2}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-fdba23d3ef1d71b253e382380f168c2d_l3.svg "Rendered by QuickLaTeX.com") that produces ![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com")s at 1 per second. What does our graph look like now?

First we need to clarify one oddity of looking at continuous graphs for a discrete problem like this. A ![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com") will produce exactly 1 ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com") in a second. But what if that ![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com") is being produced that same second? It won’t generate a full ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com") point but instead only half of one. You can think of it like ![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com") only half-existing in the second it is created, but even if it doesn’t make total sense, if you can accept that rule then everything else lines up in that beautiful way that math always does. With that out of the way, let’s look at the magic.

At time ![t](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-b4e3cbf5d4c5c6d9b702dd139f14c147_l3.svg "Rendered by QuickLaTeX.com")\=0, we have a single ![\color{BurntOrange}{Gen 2}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-fdba23d3ef1d71b253e382380f168c2d_l3.svg "Rendered by QuickLaTeX.com") that will never change, no ![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com")s, and no ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com").

![t](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-b4e3cbf5d4c5c6d9b702dd139f14c147_l3.svg "Rendered by QuickLaTeX.com")\=1, still a single ![\color{BurntOrange}{Gen 2}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-fdba23d3ef1d71b253e382380f168c2d_l3.svg "Rendered by QuickLaTeX.com"), now a single ![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com") (produced by the ![\color{BurntOrange}{Gen 2}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-fdba23d3ef1d71b253e382380f168c2d_l3.svg "Rendered by QuickLaTeX.com")), and that 0.5 ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com") produced by that in-progress ![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com").

![t](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-b4e3cbf5d4c5c6d9b702dd139f14c147_l3.svg "Rendered by QuickLaTeX.com")\=2, we’re up to 2 ![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com")s, one of which generates a whole ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com") (the ![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com") created in ![t](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-b4e3cbf5d4c5c6d9b702dd139f14c147_l3.svg "Rendered by QuickLaTeX.com")\=1) and one generates a half ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com"). Add that to the previous half and we have two ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com") at ![t](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-b4e3cbf5d4c5c6d9b702dd139f14c147_l3.svg "Rendered by QuickLaTeX.com")\=2.

Now let’s graph it!

![](https://cdn1.kongcdn.com/assets/files/0001/8772/chrome_2016-10-28_14-44-19.jpg)

That ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com") graph looks suspiciously like a parabola, no? It is in fact ![y = \frac{x^2}{2}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-3121d7b754a85ebb3e23a87a4b861d12_l3.svg "Rendered by QuickLaTeX.com"). For those of you who remember your integrals, that equation will look familiar as the integral of ![y = x](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-b4d8fb7c6b387ef45c3cce67b68e681c_l3.svg "Rendered by QuickLaTeX.com") (which is the equation that produces the blue angled line up there). Without going too much further down a calculus lesson, here’s the summary.

A derivative is a rate of change. In this growth model, each generator represents the rate of change of the next-tier-down generator, and thus can be considered a derivative. Because these are in sequence, we can effectively keep taking integrals from a starting point to see what growth becomes as you get higher tiers of generators. The series of integrals looks like this:

![1, x, \frac{x^2}{2}, \frac{x^3}{6}, \frac{x^4}{24}, ..., \frac{x^n}{n!}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-8023e58954eba993eb895ac803221c11_l3.svg "Rendered by QuickLaTeX.com")

So if we had 4 tiers of generators, starting with a single ![Gen4](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-27be56281c72742d013881fdd33d1134_l3.svg "Rendered by QuickLaTeX.com"), the ![\color{ForestGreen}{currency}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9397f8b5a4cdfac9b394d3aa354454c0_l3.svg "Rendered by QuickLaTeX.com") would be growing at ![\color{ForestGreen}\frac{x^4}{24}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-3578f2cf66af0bd1d203d6726cfdea9d_l3.svg "Rendered by QuickLaTeX.com"), and at time ![t](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-b4e3cbf5d4c5c6d9b702dd139f14c147_l3.svg "Rendered by QuickLaTeX.com") the total number of all generators would be ![1](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-4868771cbc422b5818f85500909ce433_l3.svg "Rendered by QuickLaTeX.com") + ![\color{Maroon}{t}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9ae0f9edf96f8787c2b2abaf2e361e53_l3.svg "Rendered by QuickLaTeX.com") + ![\color{BurntOrange}{\frac{t^2}{2}}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-dc0f16802804eff9230ac20d620b24c8_l3.svg "Rendered by QuickLaTeX.com") + ![\color{Cerulean}{\frac{t^3}{6}}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-ae4206c6690f3c5b7e651833b2d57282_l3.svg "Rendered by QuickLaTeX.com").

And, just to complete our circle, we’ll take a very quick look at an example from upper-level calculus. A certain type of infinitely summed series is called a Taylor Series, and there is a specific case that’s super relevant.

![e^x = \sum_{n=1}^{\infty} 1 + x + \frac{x^2}{2} + \frac{x^3}{6} + … + \frac{x^n}{n!}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-29b4e05ae3bd67c20b8bb8b6b6476cc0_l3.svg "Rendered by QuickLaTeX.com")

In other words, as we get more and more tiers of generators (as n goes up), we approach ![e^x](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-34e96bdd13dc6d8d98abb2717b4e8bf3_l3.svg "Rendered by QuickLaTeX.com"), which is…exponential growth!

![](https://cdn3.kongcdn.com/assets/files/0001/8742/tumblr_mhpp3g0gYM1r5rl88o1_500.gif)

Okay, so that was a lot of theoretical math — where did that actually get us? We’ve learned that setting up a chain of generators starts to approach exponential growth, which means it will have a lot of the properties that we had used in our exponential games. Plus, since you’re not going to have infinite generators, you’ll still always eventually lag behind actual exponential growth, so costs (at exponential levels) will still outpace production (with derivative-based growth) as we want. I also find that it just “feels” good – as you gain more tiers you get to see the lower tiers get truly huge – it’s like having multiple AdVenture Capitalist games all working together!

There are a few games that already do this, perhaps most clearly is the aptly named [Derivative Clicker](http://gzgreg.github.io/DerivativeClicker/) by [gzgreg](https://github.com/gzgreg) (forked from [icehawk78](https://github.com/Icehawk78)), seen in the animated .gif below. Note that the single Graduate Student (![\color{Maroon}{Gen 3}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-05ee749dc9d47955d1ac4983a25ce74e_l3.svg "Rendered by QuickLaTeX.com")) is producing one Undergrad (![\color{BurntOrange}{Gen 2}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-fdba23d3ef1d71b253e382380f168c2d_l3.svg "Rendered by QuickLaTeX.com")) per tick, while the High Schoolers (![\color{Cerulean}{Gen 1}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-6c821547331480bd34cd80fb8ede9e6e_l3.svg "Rendered by QuickLaTeX.com"), which produce dollars) being generated go up quickly — 10, then 11, then 12, etc. as the Undergrads increase. Exactly as we set up above.

![](https://cdn4.kongcdn.com/assets/files/0001/8748/2016-10-27_14-41-14.gif)

We can check out [Derivative Clicker code](https://github.com/gzgreg/DerivativeClicker/tree/gh-pages) to learn a little more, and indeed the costs are calculated using a basic exponential function as expected. The cost of High Schoolers for example is ![5 \times 1.1^n](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-3a82c2259c464f0ad7c1f5c0c08def45_l3.svg "Rendered by QuickLaTeX.com"). So still exponential costs, and growth is happening sub-exponentially, which is perfect!

Cirrial’s [Shark Game](http://cirri.al/sharks/) (a fantastic idle game if you haven’t tried it) also makes use of generators producing other generators; for example, the Nurse Sharks create Sharks that harvest fish.

One of the major balance issues to solve is how to keep purchasing of lower-level tiers relevant. As you can see in the gif above, I’m gaining lots of high schoolers every second, for free. Why would I ever buy more? The answer could be that you wouldn’t and you can design your game that way, but if you want to keep them relevant, well, gzgreg’s solution is an elegant one.

Notice that each generator up there has two numbers: a total owned, and then one in parentheses, which is the number actually purchased. The cost of a generator is calculated based on the purchased number, not the owned number. But more importantly, he has created tier boosts. For example, every **purchased** tier 1 building (like the High Schooler) boosts the production of all tier 1 buildings by 0.05%. This means that even when I have billions of High Schoolers, there’s still value in me being able to buy more manually, which creates a great sense of having lots of possible and influential ways to spend your resources.

One last point on the topic. What I laid out above is the simplest version of a derivative-based system, but as a game designer you have a lot more flexibility than that, and you should be open to exploring that space. For example, here’s the general cost and production chart for Derivative Clicker. Notice that it has two currencies and generators have dependency on the production of one another, which makes for some excellent interplay during the game.

[![](https://cdn1.kongcdn.com/assets/files/0001/8746/Pasted_image_at_2016_10_27_05_29_PM.png)](https://cdn1.kongcdn.com/assets/files/0001/8746/Pasted_image_at_2016_10_27_05_29_PM.png)

So I would encourage you to explore different types of progression within your game. The standard all-generators-contribute-to-a-primary-currency progression is great and powerful, but it can also be combined with things like this derivative-based generator concept.

Make generators. Draw lines between them. See what happens! Maybe one generator can produce multiple currencies. Or multiple generators. Or maybe even [more idle games](http://www.kongregate.com/games/kongregate/idleplex). The world’s your oyster, have fun with it. ![🙂](https://s.w.org/images/core/emoji/13.0.0/svg/1f642.svg)

Part III
--------

In Part I we looked at some of the standard math behind rapid-growth idle games, primarily at the relationships between exponential and polynomial growth and some methods of checking and adjusting the balance of the various generators over time.

In Part II we explored different options for growth outside of the Cookie Clicker exponential model, as well as other options for interactions of generators.

Now, in the final part, we will look at prestige loops, including analyzing the design behind real-world examples and how to vary them to keep things interesting for the player.

The ability to reset your game with a multiplier to progress, often called a “prestige,” is one of the crucial mechanics behind most modern idle games, originally popularized (and conceived?) by Orteil’s Cookie Clicker. At a high level, these systems serve two primary purposes:

1) They create the “ladder climbing” effect that contributes to why idle games are so compelling. It gives players the ability to reset with a huge boost that gives a sense of power and progres. This is similar to how “launch games” (like [Burrito Bison: Launcha Libre](http://www.kongregate.com/games/JuicyBeast/burrito-bison-launcha-libre) or [Curl Up and Fly](http://www.kongregate.com/games/Kongregate/curl-up-and-fly)) have the player go as far as possible, then upgrade, then launch again.

2) They rein growth back into a more manageable number. This can give you as a developer a more stable number to key progress and upgrades off of, since growth here will be slower.

_Note: I have incorrectly called this “taking a log” in the past. Most prestiges are a fractional exponent (e.g. a square or cube root) rather than a mathematical log function, so growth is still very large in some cases. Clicker Heroes is an exception that really does have a log-type effect. That said, some of these games have since added systems that do substantially rein in numbers, such as Realm Grinder’s Reincarnations and AdVenture Capitalist’s Mega Bucks._

The amount of prestige currency generated can be calculated off a variety of factors, including (but not limited to):

*   Max earnings (Realm Grinder)
*   Lifetime earnings (Cookie Clicker, AdVenture Capitalist)
*   Earnings since last reset (Egg, Inc.)
*   Number of upgrades purchased since last reset (Clicker Heroes)

These fall into two primary categories: lifetime stats and since-reset. This fundamental difference guides general reset behavior in a significant way. Let’s dig into each of these examples a bit more to see how. For these formulas, the variables will be:

![Δp](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-57985b32257dcd0df114d11d0bdc0551_l3.svg "Rendered by QuickLaTeX.com") = prestige currency to gain  
![p](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-3bf85f1087e9fbed3a319341134ac1a2_l3.svg "Rendered by QuickLaTeX.com") = total prestige currency  
![c_L](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-c56710f8646f268194a186b2f6565cd7_l3.svg "Rendered by QuickLaTeX.com") = lifetime currency  
![c_M](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-bcb73d8bc5ca232524ed5e18d4d5c697_l3.svg "Rendered by QuickLaTeX.com") = max currency  
![c_R](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-a97d78ceb94c8fabe69c588fb8ac16a7_l3.svg "Rendered by QuickLaTeX.com") = currency this run

**First up, Realm Grinder:**

![](https://cdn3.kongcdn.com/assets/files/0001/9389/Gems.png)

![p = \frac{\sqrt{1 + 8 \cdot\frac{c_M}{10^{12}}} - 1}{2}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-70b8db99e1b12189bed81ca830198198_l3.svg "Rendered by QuickLaTeX.com")

That seems like a pretty bizarre formula, but it’s actually very simple. Why? The equation for the amount ![c_M](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-bcb73d8bc5ca232524ed5e18d4d5c697_l3.svg "Rendered by QuickLaTeX.com") required for ![p](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-3bf85f1087e9fbed3a319341134ac1a2_l3.svg "Rendered by QuickLaTeX.com") is:

![c_M=10^{12}\cdot\frac{p(p+1)}{2}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-9627b5fd5fe3d381412154db418b2a06_l3.svg "Rendered by QuickLaTeX.com")

You may recognize that as the summation formula. So now we need to solve for ![p](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-3bf85f1087e9fbed3a319341134ac1a2_l3.svg "Rendered by QuickLaTeX.com"). Hmm, let’s see…

![p^2+p-\frac{2c_M}{10^{12}}=0](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-dd00193f9315c82ea631488f1be9eaa8_l3.svg "Rendered by QuickLaTeX.com")

Yup, that’s right. You’re about to use the quadratic formula. For your job/hobby. In the real world. I bet you never thought you would! Plug it in and you’ll get that first equation up there. _(This legitimately got me so excited that I posted about it on Facebook.)_

![](https://gameanalytics.com/wp-content/uploads/2017/07/download.png)

_© Saturday Morning Breakfast Cereal (SMBC), used with permission_

Since this formula is based on the square root of the max currency earned, it means that if you reset at the same point you will earn literally no more prestige currency. To double prestige currency, a player would need to earn 4 times as much as the previous run, so that gives you a rough target to keep in mind when modeling and balancing.

**Next, AdVenture Capitalist:**

![](https://cdn2.kongcdn.com/assets/files/0001/9390/2015-07-10_00002.jpg)

![p = 150\cdot\sqrt{\frac{c_L}{10^{15}}}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-376a27167fb0a82f4f716db21cc42cb8_l3.svg "Rendered by QuickLaTeX.com")

Here we similarly have a square root, but this time based on lifetime earnings. Again assuming we want to double prestige currency each run, how much more than the previous run do we need to earn? It depends a bit on your assumptions about the previous run, but it’s likely somewhere in the similar 3x – 4x range. However, a fundamental difference is that you can keep resetting at the same point and gain currency. That said, the amount of currency diminishes each time, which means that players do need to be able to advance to make appreciable gains.

**How about Cookie Clicker?**

![](https://cdn4.kongcdn.com/assets/files/0001/9391/Hco.png)

![p = \sqrt[3]{\frac{c_L}{10^{12}}}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-2ccfac25ea7950926c46ec3aa46b1b9c_l3.svg "Rendered by QuickLaTeX.com")

It is also based on lifetime earnings, but using a cube root, meaning to double prestige currency, a player needs to earn roughly 8 times the previous run.

On the other side we have the systems that are agnostic to previous performance — each run is an independent event as far as the prestige currency calculation is concerned. This means that if you reset at the same point a few times in a row you will get the same amount of currency each time. This is a very different dynamic that can create ideal strategies that don’t involve much progress in the game beyond a certain point.

These types of systems must be balanced quite differently. They have very flat curves for calculating prestige currency (that is, getting farther in a run has rapidly diminished returns).

**Let’s look at Egg, Inc.:**

![](https://cdn2.kongcdn.com/assets/files/0001/9393/chrome_2017-01-12_17-45-57.png)

![\Delta p = (\frac{c_R}{10^6})^{0.14}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-a424227b2dcd1a8792e4854d03250aaa_l3.svg "Rendered by QuickLaTeX.com")

That’s roughly an exponent of ![\frac{1}{7}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-ad9e98aa7250277761bf01899f916f02_l3.svg "Rendered by QuickLaTeX.com"). So where doubling in Realm Grinder would require 4 times as much as the previous run, Egg, Inc. would require 128 (![2^7](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-8a90bdbedea77816b26ff9dc73ea0d51_l3.svg "Rendered by QuickLaTeX.com")) times as much! This could be done for a variety of design reasons, but I think one of the clearest is to nudge players into more active play and reduce the influence of time on progression. Or conversely, to accelerate progress in an offline-limited system.

In the case of Egg, Inc. I believe it to be the latter. Players are limited to 2 hours of offline play by the game. By allowing players to earn equivalent currency on equivalent runs, the game minimizes the dependency of idle gains, which is important since it has created hard limits on those gains. Progress then happens in staircase tiers through the sub-prestige loop (which roughly multiplies earnings by 5x each time) and general upgrades.

Clicker Heroes, on the other hand, has no such limits to offline gains. Instead it has a very steep difficulty curve that makes progression through the main series of “hero zones” fairly slow. As a result, the ability to keep earning prestige currency at about the same point gives players the ability to progress despite a pretty substantial progress wall. The currency itself is based on the number of upgrades purchased for the generators (heroes). Because the cost of upgrades grows at an exponential rate, this does effectively “take a log” of the overall growth curve.

Pulling these all together, in the chart below we look at the relative prestige currency gains based on earnings relative to the previous run. So the ![x](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-ede05c264bba0eda080918aaa09c4658_l3.svg "Rendered by QuickLaTeX.com")\-axis is a multiple of the previous run, meaning ![x](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-ede05c264bba0eda080918aaa09c4658_l3.svg "Rendered by QuickLaTeX.com")\=1 is earning the same amount as the previous run, ![x](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-ede05c264bba0eda080918aaa09c4658_l3.svg "Rendered by QuickLaTeX.com")\=2 is double, etc. The ![y](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-0af556714940c351c933bba8cf840796_l3.svg "Rendered by QuickLaTeX.com")\-axis is prestige currency, normalized to the amount currently owned. So ![y](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-0af556714940c351c933bba8cf840796_l3.svg "Rendered by QuickLaTeX.com")\=1 would mean that you would double your prestige currency (i.e. you earn +100%). For the sake of sanity, we’re making an assumption that the previous earnings for the lifetime calculations were ¾ of the total earnings (i.e. the previous run quadrupled the lifetime earnings to that point), so lifetime earning is ![\frac{4}{3}](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-0d50443e9b625e846a8f38e891bba33d_l3.svg "Rendered by QuickLaTeX.com") of the previous run.

[![](https://cdn4.kongcdn.com/assets/files/0001/9386/chrome_2017-01-12_16-08-25.png)](https://cdn4.kongcdn.com/assets/files/0001/9386/chrome_2017-01-12_16-08-25.png)

Looking at ![y](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-0af556714940c351c933bba8cf840796_l3.svg "Rendered by QuickLaTeX.com")\=1 you can see rough relative earnings required to double your current prestige currency. As expected, this occurs at ![x](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-ede05c264bba0eda080918aaa09c4658_l3.svg "Rendered by QuickLaTeX.com")\=1 for both Egg, Inc. and Clicker Heroes, since they are independent from previous runs. Both of those curves flatten out quickly, though, and are overtaken by the other three before long.

So, that was a quick look at a variety of ways to calculate prestige currency and the design implications of them. But once you settle on a method for your game (or even use a few methods if you want to get crazy with multiple prestige currencies), how do you balance it?

To try to get a bit of a handle on this I put together “yet another spreadsheet”™ to let you play around with implications of varying the parameters. It can be found in this collection of [idle game models](https://drive.google.com/drive/folders/0B-XwqDnGiT2KWjdPbzNURkhKbmM), specifically sheet 3a. This is a very simple prestige system with only a single generator, but it can help understand the dynamics at play.

One thing to consider is that in the same way that you want to make progress through a run somewhat “bumpy” with slow parts and fast parts, you likely want to have similar variation in your prestige resets too. Much of this variation comes from the interplay of multipliers/upgrades and the rate at which prestige currency is gained (as well as the player’s targets for when to reset). Predicting player behavior in this case is difficult, but you can likely capture most players by varying within reasonable ranges.

[![](https://cdn4.kongcdn.com/assets/files/0001/9388/EXCEL_2017-01-12_16-34-32.png)](https://cdn4.kongcdn.com/assets/files/0001/9388/EXCEL_2017-01-12_16-34-32.png)

In this chart, generated by that spreadsheet, the ![y](https://gameanalytics.com/wp-content/ql-cache/quicklatex.com-0af556714940c351c933bba8cf840796_l3.svg "Rendered by QuickLaTeX.com")\-axis is the number of generators owned. Each time that hits 0 it’s a prestige reset. You can see bumps of rapid purchases at 300, 400, 500, etc. generators owned — those are due to multipliers kicking in at those totals.

There’s also a fairly long prestige starting at 120 minutes. It finally breaks at 500 generators, which is when a large 16x multiplier triggers. This is a case in which the model likely would be off — a player who just hit a big milestone is likely to keep going for a while since that’s a fast section of the game. The point being that you should not use this model as an accurate simulation but instead as a way to try to get a rough feel for how your system would behave.

So, that’s three blog posts full of equations, graphs, and spreadsheets. While I hope that those will be useful tools for anyone working on an idle game, I think the meta takeaways are:

*   There’s a lot more variety possible than the two most-common models (Cookie Clicker and Clicker Heroes). In particular, think about ways that generators can interact with one another. Draw a flowchart, then mess around with the arrows.
*   Balancing progression is hard. Spreadsheet models can help, but there’s a lot of iteration required and you have many tools at your disposal.
*   When designing your game, determine where the “fun” is and focus on that. Is it unfolding new features? Collecting tons of achievements? Optimizing the prestige loop? The novelty of big numbers on their own is largely gone, but there are still many opportunities for surprising and delighting players.

And with that we’ll conclude this series of idle math blog posts. I hope they have been helpful, and as always please reach out if you have any questions or cool games you want to share. ![🙂](https://s.w.org/images/core/emoji/13.0.0/svg/1f642.svg)

_If you would like to contact me, shoot me an email at [anthony@kongregate.com](mailto:anthony@kongregate.com). I also want to give credit to the tools used in this post: [MathJax](https://www.mathjax.org/) did the awesome live-rendering of LaTeX and [Desmos](https://www.desmos.com/) is a slick in-browser graphing calculator with some great educational functionality._

[[Incremental_games - Linear, Polynomial, Exponential (and more) growth explained]]