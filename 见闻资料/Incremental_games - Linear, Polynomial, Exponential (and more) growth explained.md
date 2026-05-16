---
modified: 2026-05-16T13:22:55+08:00
---
> 译文：[[增量游戏——线性、多项式、指数（以及更多）增长方式详解]]

https://www.reddit.com/r/incremental_games/comments/2ztcfk/linear_polynomial_exponential_and_more_growth/

Inspiration and information for this tutorial comes mainly from [this wiki](https://oeis.org/wiki/Growth_of_sequences).

If you are a regular of this sub you will see the terms Linear, Polynomial and Exponential thrown around sometimes. There are [blogs and tutorials](http://mrhen.com/blog/?cat=11) that make a good job at explaining the role these functions have at balancing incremental games (which sometimes can be quite math intensive). Still, there is some people who seems lost about what different functions growth means.

Growth refers to **how fast a sequence of numbers increases**. In an incremental game these sequences usually are resources by time or prices based on levels. It is also important the concept of bound. **We say B bounds A** (above) **if B grows faster than A**, that is, at some point B becomes bigger than A and stays bigger forever (the same apply for bounded below).

Notice that bound is concerned to how fast a sequence gets big, not particular values. Let see an example:

A: 1.000.000, 2.000.000, 3.000.000...

B: 1, 4, 9, 16...

We may think A grows faster because it has way bigger numbers. However, after a (long) while it looks like this.

A:9.99999E11, 1.0E12, 1.000001E12

B:9.99998E11, 1.0E12, 1.000002E12

Therefore B grows faster than A.

When a sequence is bounded above and below by the same function, **we say that it grows like that function**, e.g. Quadratic growth. Again, we are not concerned with specific values, but with how the sequence evolves. This concept is useful because we can use it to classify sequences, comparing them to well known mathematical functions.

███

**The holy trinity.**

Linear, Polynomial (degree >=2) and Exponential are by far the most common used growth rates for incrementals. The reason is that they bound each other in order (Linear < Polynomial < Exponential) and **can be combined to balance the progress in a game in terms of production and prices**.

If prices grow slower than production, at some point buying stuff becomes trivial since you produce more than you spend, and the balance is broken. If they grow at the same rate, the time that it requires to buy something is kept almost constant (e.g. 1 every 10 minutes) which may or may not be interesting. If prices grow faster, it will longer and longer to buy new stuff, slowing down progress. This slow down is used by designers to force the player to hit a "wall" were progress is too slow, usually forcing some kind of action (prestige, moving to a new section of the game) to continue progressing.

We are now going to proceed to explain each one individually.

█

**Polynomial.**

█

**Linear.**

**Description:** Grows like a linear function.

**Example function:** x

**Example sequence:** 1,2,3,4,5...

[Plot](http://bit.ly/1CImVpC)

**Explanation:** Although we usually talk about linear and polynomial as different things, linear is a kind of polynomial, specifically of degree 1.

Linear growth is the one most people will be familiar with, as it is everywhere in our daily life. This sequence grows at a fixed rate, so the different between two consecutive elements is the same. It is also how people intuitively think about how things progress: if going somewhere takes 1 hour, going twice further will take roughly 2 hours. If buying something cost 100$, buying 5 of it will cost 500$, and so on.

**Possible uses:** Linear growth is almost always used as a resource generation rate. It is simple, it is easy to work with, and people is familiar with it. They also are naturally trained to work with it and can easily make guesses about how it will progress.

█

**Superlinear.**

█

**Quadratical.**

**Description:** Grows like a polynomial of degree 2.

**Example function:** x2

**Example sequence:** 1,4,9,16,25...

[Plot](http://bit.ly/1bkSsBR)

**Explanation:** When we talk about polynomial, usually we mean any polynomial with degree >= 2. A polynomial with degree exactly 2 has an special name, quadratic.

As we can see from the example sequence, unlike in linear growth, here the distance between two consecutive numbers gets bigger and bigger. Now lets look at the distance between two consecutive numbers:

3,5,7,9,11...

We can see that although the distance grows bigger, it does so at a constant rate of 2.

People have a harder time understanding quadratic growth because it is not as commonplace as linear in our daily lives. One of such few examples would be the following: in a sports tournament, each team needs to play a match against each other team. In that case, the number of total matches is in the order of x2 (thanks to [this post](http://www.quora.com/What-are-some-examples-of-quadratic-growth-that-would-be-applicable-to-high-school-students)for the inspiration).

**Possible uses:** Since quadratic sits in the middle between linear and exponential, it can be used both for prices and for generate resources. A tipycal example for resource generation is a "building that creates buildings", as seen in [Derivative Clicker](http://gzgreg.github.io/DerivativeClicker/)

█

**Cubic,Quartic,etc.**

**Description:** Polynomials of degrees 3 (x3), 4(x4), etc. The same description of Quadratic applies, but each one growing faster.

█

**Exponential.**

**Description:** The growth rate of the sequence is a factor of the current value.

**Example function:** 2x

**Example sequence:** 2,4,8,16,32,64,128,256...

[Plot](http://bit.ly/1EzAhQ4)

**Explanation:** Exponential growth is the one people usually has most problems with. We know that it grows fast, but people usually doesn't fully understand what this fast means. It is usually mistaken with a polynomial of a high degree, because these polynomials produce large values.

As in polynomial case, we see how the distance between numbers grows bigger. Lets take a look at the distance between two consecutive numbers.

2,4,8,16,32,64,128

As we can see, unlike for polynomials, the difference in the distance between two consecutive numbers is not constant, but it increases. This means that not only numbers grow apart with time, but this trend accelerates with time.

Exponential growth is also present in some real life situations, but usually complex enough so that some people can get lost on it. For instance, the interest rate in loans or bank savings follow exponential growth, since they are multiplied by a rate each year. Also the population of some organisms like virus and bacterial follow exponential growth e.g. the total population of viruses doubles every day.

**Possible uses:** Exponential is almost exclusively used for prices, as it bounds both linear and polynomial, and it ensures that player progress will slow down with time.

███

**The growth zoo.**

Beyond the three growth functions that we have seen, **there is a lot of other functions both slower and faster**. Most of these functions are little know, and although some are not very useful for incremental games, others have a lot of potentials to implement interesting gameplay mechanics.

In the following sections we are going to describe different growth speeds from slower to faster.

█

**Subpolynomial.**

█

**Iterated logarithmic.**

**Description:** Growths like an [Iterated Logarithm](http://en.wikipedia.org/wiki/Iterated_logarithm), log\*

**Example function:** log\* x

**Example sequence**: log\* 2 = 1, log\* 4 = 2, log\* 16 = 3, log\* 65536 = 4, log\* 265536 = 5

**Explanation:** The iterated logarithm function means "how many times do we need to apply log to this number to make it <= 1?", and it grows very, VERY slowly. How slowly? look at the sequence. For 265536 its value is only 5. For all practical purposes, we could consider the value of this function to be <= 6.

**Possible uses:** The only possible use I can imagine for this function is for a value that we want to keep almost constant.

█

**Logarithmic.**

**Description:** Grows like a logarithm

**Example function:** log x

**Example sequence:** 1, 1, 1, 2, 2, 2, 2, 2, 2, 2, 2, 3, 3...

[Plot](http://bit.ly/1EDkqT6)

**Explanation:** The inverse of an exponential, this function grows slower with time. At some point it becomes very hard for it to grow anymore.

**Possible uses:** This function could be uses to implement diminishing returns in generators or upgrades, such that the benefit you get from buying more and more of the same get reduced the more you have.

█

**Polynomial.**

█

**Sublinear.**

**Description:** Grows at a polynomial rate, but slower than linear.

**Example function:** sqrt(x)

**Example sequence:** 1, 1, 1, 2, 2, 2, 2, 2, 3, 3, 3, 3...

[Plot](http://bit.ly/1MYp7Jb)

**Explanation:** Square root of x is x1/2. If we imagine linear as x1, then it makes sense that the square root grows slower than linear. Also, although it grows slower than linear, is not as unforgiving than log, and still manages to make some slow progress. This grow can also be generalize for the cubic root, 4-root, etc., each one growing slower.

**Possible uses:** Some games use the technique of imposing penalties on resource production in order to slow down player progress. A sqrt curve could be used for such penalty. Since linear bounds sqrt, we would slow down production without the risk of completely stopping it.

█

**Superlinear but subquadratic.**

**Description:** Grows faster than linear but slower than quadratic.

**Example function:** x\*log x

**Example sequence:** 200,202.43,204.87,207.32,209.77,212.22,214.68,217.14,219.60,222.07

[Plot](http://bit.ly/1bkSxFK)

**Explanation:** It grows slightly faster than a linear, and significantly slower than a quadratic. It can be generalized for higher degrees polynomials e.g. x2 \* log x.

**Possible uses:** It can be used to slightly boost production, for instance providing a generation bonus based on the current amount of resources.

█

**Superpolynomial but subexponential.**

**Description:** Grows faster than any polynomial, but slower than any exponential.

**Example function:** xlogx

**Example sequence:** 1, 3, 6, 13, 24, 44, 75, 124, 200...

[Plot](http://bit.ly/1CHqomR)

**Explanation:** Its behaviour is closer to an exponential than a polynomial, but still is bounded by it.

**Possible uses:** Now this is a very interesting function. People usually use exponential growth for prices to slow down progression. Using this function, we would achieve the same slow down in the long run, but the process would take longer, increasing the progression curve of players.

█

**Superexponential but sub iterated exponential.**

█

**Exponential polynomial.**

**Description:** An exponential where the exponent is a polynomial.

**Example function:** 2x2

**Example sequence:** 2,16,512,65536,33554432,68719476736,5.6295E+14,1.84467E+19

[Plot](http://bit.ly/1BFKU1J)

**Explanation:** A faster version of an exponential.

**Possible uses:** If resources grow exponentially, this function can be used for the prices to bound production. It can also be used when regular exponential growth is not enough.

█

**Doubly exponential.**

**Description:** An exponential where the exponent is an exponential.

**Example function:** 22x

**Example sequence:** 4,16,256,65536,4294967296,1.84467E+19,3.40282E+38,1.15792E+77

[Plot](http://bit.ly/1EDkx12)

**Explanation:** This is a sequence where the exponent of the numbers grow exponentially. It is also a hard one to display. In the plot we can barely see it, but the red line grows faster than the green one. You see that tiny blue line at the bottom? That is a regular exponential.

**Possible uses:** This sequence grows so fast that is pretty much at the limit of how much we can handle, even with large numbers libraries.

█

**Super doubly exponential but sub iterated exponential.**

**Description:** Defines [power towers](http://mathworld.wolfram.com/PowerTower.html) of a fixed height.

**Example functions:** xxx, 222x

**Explanation:** We call a power tower to a set of nested powers. The height of the tower is the number of powers that there are, e.g. xxxx is a power tower of height 4.

█

**Iterated exponential.**

█

**Tetrational.**

**Description:** Grows in the order of a [tetration](http://en.wikipedia.org/wiki/Tetration) function.

**Example function:** 2↑↑x, using [Knuth up-arrow notation](http://en.wikipedia.org/wiki/Knuth%27s_up-arrow_notation).

**Example sequence:** 1, 2, 4, 16, 65536, 265536, 2number with ~19000 digits

**Explanation:** Have you ever wondered what comes after exponentiation? the answer is tetration. Tetration is an operation that defines how many times a number is raised to the power of itself. On this case, the x defined the height of the power tower. And it grows incredibly fast.

How fast? Look at the sequence. In 6 steps we already have 265536. But on the next step we have 2 to the power of a number with about 19000 digits. Can you picture it? Well, [here](http://pastebin.com/Wp1BCe6P) you have what a number with 19000 digits looks like. And that is the exponent of 2.

**Possible uses:** This function grows so ridiculously fast that no current number library can contain it.

█

**Supertetrational, other hyper-operators.**

**Description:** What comes after tetration? Pentation. And after that? Hexation. We can define growth speeds for each hyper operator beyond tetration.

█

**Non primitive recursive, non recursive, non computable.**

**Description:** Last stop. End of the line. We have seen functions that grow ridiculously fast. What can top that? What about functions that we can´t even compute? I don't mean that we don't know how to do it, but it has been mathematically demonstrated to be impossible. One of the most famous is the [Busy Beaver](http://en.wikipedia.org/wiki/Busy_beaver).

**Example function:** Busy Beaver.

**Example sequence:** 4,6,13,???

**Explanation:** Since this function can't be computed, we only know exactly the first few values. However, it has been proved that this function grows faster than any computable function. That includes tetrational, pentational, etc.

**Possible uses:** There, something new to have nightmares about.
