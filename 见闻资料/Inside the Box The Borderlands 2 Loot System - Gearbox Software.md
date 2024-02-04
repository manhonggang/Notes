---
created: 2023-02-14T22:54:02 (UTC +08:00)
tags: []
source: https://www.gearboxsoftware.com/2013/09/inside-the-box-the-borderlands-2-loot-system/
author: Gearbox Staff
---

# Inside the Box: The Borderlands 2 Loot System - Gearbox Software

> ## Excerpt
> Inside the Box serves as a forum for individuals involved in the production of Gearbox Software content to share personal motives, methods, process and results. Gearbox Software projects are created by a diverse range of individuals spanning a spectrum of different backgrounds, interests, objectives and world views. The views and opinions expressed in this article […]

---
> _Inside the Box serves as a forum for individuals involved in the production of Gearbox Software content to share personal motives, methods, process and results. Gearbox Software projects are created by a diverse range of individuals spanning a spectrum of different backgrounds, interests, objectives and world views. The views and opinions expressed in this article are those of the author and do not necessarily reflect the official policy or position of Gearbox Software or any of its individual members outside of the author._

Hello all. It’s Paul Hellquist, creative and design director for Borderlands 2 here again. I have previously written all of the [articles about the design of Krieg](https://www.gearboxsoftware.com/community/articles/1045). Today I’d like to spend some time demystifying how the Borderlands 2 loot system works. There has been a lot of speculation based on people’s play experiences and I felt it would be interesting and valuable for everyone to get the true story straight from the horse’s mouth.

**Where My Lootz?**

There are a few different places to get loot from. How the loot is dropped from each of them is slightly different. The two main sources are enemies and treasure chests. For the purposes of today’s article I will mainly be focusing on enemies.

Enemies are broken down into multiple categories. They are:

-   Chumps
-   Badasses
-   Super Badasses
-   Chubbies
-   Raid Bosses
-   Named Bosses

Chumps are any enemy that doesn’t have the word “badass” in their name. The other categories are fairly self-explanatory and map to those classes of enemies in the game.

To really understand how loot drops work I’m going to go through the process, following the thread of how the game makes a choice. We’ll go through the most common loot drop event; killing a basic bandit.

[](https://www.gearboxsoftware.com/wp-content/uploads/2013/09/b9f101968e3fa048b0ec5f0476e3d1335a5169a0.jpg)

**List Definitions: The Structural Foundation**

When you kill an enemy the game looks at a property in the enemy that defines the loot that it drops. What loot drops is determined by a two types of data. The first is called a List definition. A list definition is simply a collection of the second type of data; item pools. The List definition is a data structure invented to allow designers a more easy way to assign gear without needing to list the same 5-7 item pools over and over again for every enemy. Instead we could just point to the list definition. By adjusting the list definition we could change the loot drops for a huge number of enemies at one time making it a significant time saver. Below is the list definition called “StandardEnemyGunsAndGear” that is used by pretty much all of the chump level enemies.

[](https://www.gearboxsoftware.com/wp-content/uploads/2013/09/9dd67a369be2dc37ab5a3bcd18ad07f8fc264492.png)

As you can see it is a list of all of the stuff that might be dropped by a chump enemy; guns and gear, vehicle skins, eridium, etc. The “DropODDS” or numbers after the Item pool definitions are the chances that these things will drop. The DropODDS numbers are predefined numbers in another definition so that we can change the global odds for any of these things by changing a single number.

When our bandit is killed the game makes a random die roll for each of the item pool definitions in this list to determine if it will drop something from that pool. For example, the DropODDS for Pool\_GunsAndGear evaluates to 0.085 in a single player game. When you kill an enemy the game picks a random number between 0 and 1. If the number chosen is less than 0.085 the game will drop an item from the Pool\_GunsAndGear item pool. If the number chosen is greater than 0.085 it will not drop an item from that pool. (0.085 works out to about 1 in every 11.76 enemies will drop a gun or gear.)

The game then does the same die roll for each item pool in the list definition using its probability odds to determine which ones will drop.

**The More the Merrier**

Now for a quick aside based on some information hidden in that List definition image. You know that cryptic tooltip you get when loading a map about how the more players you have the better your loot? What this tip actually means is a question I have heard multiple times from fans and now is a great time to shed some light on it. The number of players in the game has an impact on the amount of loot that you receive while playing Borderlands. In a multiplayer game there are some values in the game that change based on the player count. You can see an example of this in the image above where it says “AmmoDrops\_PerPlayer\*0.2” next to the ammo item pool entry. That formula increases the amount of ammo based on the number of players in the game.

How does this relate to the cryptic tooltip? Well, believe it or not there is such a thing as too much loot! There was a time late in development where the design team spent the majority of a day just playing the game in 4 player groups. We often don’t get a chance to play big coop sessions during a normal day so we set aside a time for it so we could feel for ourselves how the game played and was balanced for 4 players. The most interesting thing that came from that day was the unanimous realization that the game was dropping way too much loot! There was so much loot on the battlefield after a battle that the game became incredibly tedious to play because there was so much loot to collect and sort out.

This overabundance of loot was due to the fact that the game was using the same drop rates regardless of how many players were in the game combined with the fact that the game spawns a lot more enemies the more players you have. In order to solve the problem we actually made the chances of loot dropping from any individual enemy go down the more players you have. This solution worked because the reduction was still less than the increase in the number enemies that are spawned. So despite reducing the drop rate per enemy your chances of getting loot still goes up the more players you have in a session. So in this case less is actually more.

**Item Pools: The Workhorse of Loot**

Back to the nuts and bolts! So what is an item pool? An item pool is a list of item definitions that the game understands and then generates the items at runtime. An item pool can also reference other item pools creating a cascading list until eventually one of them references a weapon or item definition.

Let’s assume that the StandardGunsAndGear list definition chose to drop an item from the first pool in the list: Pool\_GunsAndGear. That item pool looks like this:

[](https://www.gearboxsoftware.com/wp-content/uploads/2013/09/fd25e505d857640a35add80010a61c2f43d3978d.JPG)

This pool is at the top of the chain and references additional pools for the 5 main types of gear. Also note that it references the “\_All” pools for these items meaning that those pools have the possibility to drop every item of that type. On important not is that where a list definition rolls on everything in the list to see if it will be dropped at all, an item pool will only drop 1 item from its list ([1](https://www.gearboxsoftware.com/community/articles/1087/inside-the-box-the-borderlands-2-loot-system#footnote1)).

**Come on Down!**

The game now rolls another random number to determine which one of the item pools will be dropped. So from the above item pool you will only get one of those item types and the probability shown is the chance that pool will drop. You can see by the probabilities that you are much more likely to get a weapon than you are to get a Relic (whose item pool is called “artifacts” above).

The probability is calculated a bit differently here in the item pool than at the list definition level. Here the probability is determined by the “weight” numbers. Weights are predefined numbers that again allow us to completely change game balance and drop rates in one location instead of changing individual numbers in thousands of places. In the above example “Common” equals a value of 100. Uncommon equals a value of 10. Some of the weights are then multiplied by arbitrary values that I came up with so that the relative probabilities for each gear type matched my design for the relative rarity of the items to each other. So the actual numbers in the above image equate to:

> \[0\] = 100  
> \[1\] = 45 = 100\*0.45  
> \[2\] = 30 = 10\*3  
> \[3\] = 22 = 10\*2.2  
> \[4\] = 10

So there are some weights but how does that result in those probability numbers in the image? You can think of the weights and how the game picks from the item pools in terms of a raffle. This is the type of raffle where you have a certain number of tickets to put into jars. The more tickets you put into a certain jar, the better your chances of winning that item. Our raffle contestants are Weapons, Shields, GrenadeMods, ClassMods, and Relics. The weights are how many tickets each item pool contestant put into the jar to win the “I want to get dropped!” raffle. Weapons has 100 tickets, Shields has 45 tickets, Grenade Mods have 30 tickets and so on. The game then pulls out one ticket and announces the winner ([2](https://www.gearboxsoftware.com/community/articles/1087/inside-the-box-the-borderlands-2-loot-system#footnote2)). The winner then runs down onto the stage in a homemade t-shirt and kisses …I guess it’s Drew Carey hosting The Price Is Right now? (I still miss Bob Barker.)

Above is a graph showing the relative chances of each item pool being chosen from our raffle. The entire bar represents all of the tickets in our jar. Each colored segment is equal to the number of tickets each pool has and therefore their relative chances of being chosen.

[](https://www.gearboxsoftware.com/wp-content/uploads/2013/09/9b3b3321d8faad09c526f1c1e9a3bf50ae97252d.png)

**Common Sure is Common**

Let’s continue following the path of a drop from our standard enemy. The game has chosen to drop something from the Pool\_GunsAndGear item pool; it pulled out a ticket and “Guns” won the raffle. We now drill down into the Pool\_Weapons\_All item pool. It looks like this:

[](https://www.gearboxsoftware.com/wp-content/uploads/2013/09/60af85ef3643a12f6c0c968338a802cb6b84dc6c.png)

As you can see this pool references another list of pools. In this case it references all of the different rarities of weapons and you can see how they break down. Unfortunately the editor is lying to us in this image! The common pool’s weight is a formula which the editor can’t do the math on unless the simulation is running so it is returning zero and skewing those probabilities dramatically. In truth the probabilities are thus:

<table><tbody><tr><td>Rarity</td><td>Probability (rounded)</td><td>Chances (approximately)</td></tr><tr><td>Common</td><td>89.92%</td><td>9 of 10</td></tr><tr><td>Uncommon</td><td>8.99%</td><td>1 in 10</td></tr><tr><td>Rare</td><td>0.89%</td><td>1 in 100</td></tr><tr><td>Very Rare</td><td>0.09%</td><td>1 in 1000</td></tr><tr><td>Very Rare (E-Tech)</td><td>0.09%</td><td>1 in 1000</td></tr><tr><td>Legendary</td><td>0.009%</td><td>1 in 10000</td></tr></tbody></table>

So what is that formula that is lying to us doing? That formula is what makes the Vault Hunter Relic work. The Vault Hunter Relic makes all higher rarities in the game more likely to occur by simply reducing the weight of the common pool. Using our raffle analogy the Vault Hunter Relic removes some of Common’s tickets from the jar so it is less likely to win.

**Come on Pistol! Give Me a Pistol!**

Despite Vault Hunter Relic stealing tickets let’s assume that the Common\_All pool still won the raffle. The next step of the process looks like this:

[](https://www.gearboxsoftware.com/wp-content/uploads/2013/09/350dafb8975a38311df077ce209e5141ac987f5b.png)

Now the game is choosing what kind of weapon you will receive. This one is super straight forward and doesn’t even use predefined weights but just uses hand entered numbers ([3](https://www.gearboxsoftware.com/community/articles/1087/inside-the-box-the-borderlands-2-loot-system#footnote3)). As you can see the pistols are the most commonly found weapons and the launchers are the rarest.

**Woo Hoo! Pistol!**

Let’s assume from we got our pistol! Now we are finally down to the item pool referencing a definition that results in an actual gun:

[](https://www.gearboxsoftware.com/wp-content/uploads/2013/09/621852ff5d997e5dc5f72b293368778092db5c5c.png)

In this item pool we have the actual references to the definitions for each manufacturer of pistols and as you can see each manufacturer is exactly equally weighted so no manufacturer of pistol should be more common than another if this path to choosing an item was taken. The game makes one final die roll to choose the exact weapon and we finally get our Tediore pistol flying out of the bandit.

**Gamestage for Beginners**

Another interesting thing to note in the data above is that there is something listed in the “Min Game Stage Requirement” field. This field is a reference to a piece of data called “gamestage.” Gamestage is referenced by the enemy spawners, treasure chests, and a bunch of other systems to tell the game what level the actors that spawn from them should be. Gamestage is what determines that the enemy you are fighting is level 5 instead of 15. It is also what determines that the pistol our bandit dropped is level 8 instead of 43. Gamestage is how we keep the game balanced as you grow your character and is an integral part of how the game functions.

In terms of our loot dropping exercise the “Min Game Stage Requirement” field in the above image says “Gamestage\_02” which means that this item pool can only be considered if the gamestage of the enemy was at least level 2.

**Limiting Loot**

We use this the Minimum Gamestage field mainly to limit the drops of certain items during the course of play. You may be wondering why we would want to limit the loot in this way. Wouldn’t it be better to just have everything have a chance to drop at any time? For the majority of the game experience, especially the late game this notion is exactly correct, it is good to potentially find anything. The early game is an entirely different situation though. Early in the game is when you have players who have never played Borderlands before. When you are presented with too many new things all at once it can become overwhelming, preventing you from fully understanding any of them. Restricting when certain items are allowed to drop can allow each new type of gear to have its time to sink in and be fully understood before adding a new element to understand. This is the experience we want a new to Borderlands player to have.

The second big value in restricting gear drops is that the restrictions are important for making the early game feel like you are finding new and interesting gear for an extended period. Imagine if you found and filled all of your equippable slots in Borderlands the first 10 minutes. It would not feel like an exciting moment to find any of them because you will have barely found one new thing before finding another. You need time appreciate the new item before you get the next. Also, it feels good in a long game like Borderlands to find something new and interesting many hours into the experience.

Below is a snippet from the spreadsheet that I used to plan out when the different loot in the game is introduced. This only shows the weapons:

[](https://www.gearboxsoftware.com/wp-content/uploads/2013/09/d9fcd4cdd9f12dc9afe6b3bb97737ea1dcf73999.JPG)

As you can see we don’t even drop any weapons until you reach level 2. This anomaly is so that you don’t already have a better weapon than the one you get from the cabinet in Claptrap’s igloo. Assault rifles are next because of their basic utility and the major promise of automatic weapons in a shooter. Then we let that sit for a bit so the missions can introduce the first Shotgun and Sniper rifle which then start dropping around the same time. SMGs are next because they are more utility and we want players to understand the limitations of assault rifles better so they appreciate the SMGs more when they arrive. Finally the last weapon type to be introduced in Launchers at gamestage 10 because they are the most powerful, most exciting to find the for the first time, and the limited ammo makes them something you can only use occasionally so we want players to have plenty of other options available when they get one.

**How Random is Random?**

I’m sure some of you have experienced times in Borderlands when you feel like you are on “hot streaks” and “cold streaks” where you are getting a ton of (or none of) what you want. The game must be skewing the rolls in or out of your favor! Let me assure you: This is not the case!

Random number generators that are used in software like Borderlands are technically [“pseudo-random”](https://www.gearboxsoftware.com/wp-content/uploads/2013/09/Pseudorandomness) and not true random due to limitations of hardware, operating systems, and other factors. Also there is limited value that the gamer can perceive by going the many extra miles to gain true random results. True random vs. pseudo-random is a whole debate and academic discussion that I will not pretend to be an expert on.

For the purposes of Borderlands 2, all you need to know is that whenever the game rolls these imaginary dice to determine what to drop it has absolutely no knowledge of the previous roll or the previous results and every number has an equal chance of being rolled every time the die is cast. For all intents and purposes it is “random” as laymen use the term.

What this means is that every time an item drops there in an equal chance for every number to be rolled. There is no secret re-weighting based on how long since the last legendary, or since the last sniper rifle dropped or anything like that. This fact means you can get on “hot streaks” and “cold streaks” where it feels like the game is skewing the rolls.

It is important to remember that probability is only accurate over huge sample sizes. Using the example of the probability of getting a legendary drop from any old bandit the chart earlier in the article says you have a 1 in 10000 chance. That does not mean that if you get 9999 drops and have not gotten a legendary yet that the next drop will be legendary. In fact you might not get one until roll 19998 and then get two in a row! Or you might go 50000 rolls without getting one and then get 5 in a row. If these strange cases occurred your results would be at the expected 1 in 10000 rate but it might feel to you like the game is doing something strange or odd behind the scenes. In fact, that’s just how math works.

**Exceptions to the Rules**

There are a couple of minor exceptions to the randomness rules I just mentioned. They are minor and relate to very specific items. Class mods are more heavily weighted towards the character classes that are in the game at the time of the drop, although it is still possible to get drops for classes that aren’t playing. This exception was added because it really sucked to be playing solo and only have a 25% chance of ever seeing a mod for your class.

The only other non-random shenanigans are played with ammo and health drops. You may have noticed in the very first image of the article this little tidbit:

[](https://www.gearboxsoftware.com/wp-content/uploads/2013/09/314e8699afde65f397088488935647d2a5150c4f.png)

These are the “need” and “emergency” item pools for ammo. These pools, if they are chosen, have a bit more logic that occurs before the items are dropped. Specifically, the game checks to see if you need the item chosen before dropping it. The rules for allowing the drop are based on how much ammo you have. If you are low you will probably get the “need” but not “emergency” ammo. If you are super low you will probably get two extra ammo drops, one from each of these pools. Health works in a similar way that you are more likely to find health when you are low. There are actually some specific lootables that almost always have health when you are low. Have you figured out which ones?

**That’s Not the Whole Story…**

The topic of loot is, of course, much larger than this and I certainly didn’t cover everything but hopefully you now have a stronger understanding of how loot drops from an enemy. With a few small exceptions Borderlands 2 basically uses a RNG FTW philosophy!

I’d love to know what else you want to know about loot so here’s what I’ll do. Send questions about loot to [insidethebox@gearboxsoftware.com](mailto:%20insidethebox@gearboxsoftware.com), post them in [our forums](https://www.gearboxsoftware.com/wp-content/uploads/2013/09/forums.gearboxsoftware.com), or tweet me [@TheElfquist](https://www.gearboxsoftware.com/wp-content/uploads/2013/09/TheElfquist). I’ll do another article at a later date that will be a FAQ with the more interesting or common questions. The more general your questions are the better. Things like, “Why is the damage on the Unkempt Harold 1045 and not 1086?” will probably not get chosen because it is much too specific and a very minor point. The goal is to answer broader high level questions that will be of interest to a wide range of Borderlands fans. As always any other feedback about the article or Inside the Box in general is also welcome. Until next time!

> _(1) If the “Quantity” value is greater than 1 a pool will drop more. Quantity is only very rarely changed from its default value of 1._
> 
> _(2) If you are interested in the gory details how this actually functions: the code adds all of the weights together getting a total of 207. It then divides that 1-207 range up into chunks based on the weights. If the number rolled falls within the range allocated to a particular entry in the list, that item pool will drop an item. The diagram depicted shows how it creates chunks related to each pool. A random number between 0 and 100 will drop a gun. A die roll between 100 and 145 will drop a class mod and so on._
> 
> _(3) Why not use predefined weights in this case? Because I’m an idiot that’s why. I really should have used the weights._
