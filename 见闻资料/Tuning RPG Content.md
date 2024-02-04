_This article primarily focuses on PvE combat in RPGs, though its methods can be applied to PvP or other types of games. It was originally posted on [AltDevBlogADay](http://altdevblogaday.com/2012/02/17/the-craft-of-game-systems-tuning-rpg-content/) on February 17, 2012._

Role playing games have a tremendous amount of content, each piece with multiple parameters that define what they do in combat. Damage dealt by a sword, bonus granted by a skill, total health of a level 23 bandit, etc. It’s not too hard to tune content when you look at a single game zone or a fixed character level – you can playtest that area and tweak values until the game feels right. However, trying to tune values for a giant world with 100 levels of content and multiple classes is much more complicated. **How do you choose values for RPG content without playtesting and brute force tuning every type of character at every level?**

[![](https://craftofgamesystems.files.wordpress.com/2012/04/diablo-iii-demon-hunter-progression.jpg?w=620&h=229 "Diablo III Demon Hunter Progression")](https://craftofgamesystems.files.wordpress.com/2012/04/diablo-iii-demon-hunter-progression.jpg)

_Many factors increase character power as they level up in games like Blizzard’s Diablo III._

A computational approach can help you quickly generate first pass values for these massive amounts of content. The method is to calculate how each piece of content affects a character’s effectiveness in combat and express that “power” in terms of a universal unit. That allows you to compare very different types of content in a mostly apples-to-apples way, enabling you to do a variety of powerful things:

*   Compare different classes and tune them relative to each other.
*   Identify items or abilities that are likely to be unbalanced.
*   Determine what stats enemies need to be a good challenges for characters.
*   Solve for the parameter values of a skill or item to make it as powerful as it should be.

That last one is especially important. Not guessing. **Solving.** (then tweaking)

It’s not an exact process. It requires a lot of estimating and approximating, and it can’t be done for certain types of content. However, where it does work, you can use it to rapidly generate parameter values that will be about 80% right.

The Method
----------

Here are the steps:

1.  **Implement your core minute-to-minute gameplay.** Creating a progression of content won’t help If the game doesn’t play the way you want it to, and you’ll have to redo the work after you fix your core gameplay. Create a vertical slice of your game that plays the way you want.
2.  **Design the stats that define the “base power” of a character of level X.** “Base power” is defined by the stats that improve steadily as a character levels up and which are not influenced by player choice, such as health, base damage, expected armor, or THAC0.
3.  **Identify other game content that magnifies a character’s combat effectiveness as he levels up.** This can include systems like item modifiers, skills, WoW’s ability glyphs, or LoL’s runes. These combine to give the character’s “total power”.
4.  **For each piece of content, determine how to express its value as a percentage modifier to a character’s base power.** For instance, a 2% damage bonus increases a character’s power by 2%. “Percentage bonus to base power” is the universal unit you’ll use to compare different types of content.
5.  **Choose what impact you would like each type of content to have on total character power as the character levels up.** Should each skill point increase a character’s base power by 5%, so they’re twice as powerful after spending 20 points?
6.  **Given each piece of content’s intended effectiveness, solve for its parameters.** If you know the intended bonus to base power you want a piece of content to grant, and you know how to calculate its power from its parameters, you can work backward to solve for its parameters.

Base Power
----------

Defining base power is something I struggle with because it’s so specific to each game. The best definition I’ve found is that it’s the combination of all character stats that increase automatically as a character levels up, without involving any choice by a player. Examples include things like character health or THAC0 in D&D. WoW characters get a fixed set of stat points when they level up, and skills increase steadily in effectiveness.

Expected damage per second and armor are also part of base power. Though these don’t increase automatically (the player has to find new gear), game content tends to be designed with the expectation that players are maintaining up-to-date gear. Games like WoW assume that players are using items with [base stats that are](http://www.wowwiki.com/Item_level#Weapon_DPS) [appropriate for their level](http://www.wowwiki.com/Item_level#Armor_values), so unmodified item stats are part of base power.

Power Magnifiers
----------------

Power magnifiers are pieces of content that modify a character’s base power in combat. Their significance to his overall power generally grows as he levels up. Here are some examples:

*   Skill Points or Talent Points. Each point increases character power by a percentage.
*   Item Modifiers in tons of RPGS. They get more numerous / significant at higher levels.
*   Materia in Final Fantasy VII. Players get more powerful Materia and can use more at once as they progress through the game.

[![](https://craftofgamesystems.files.wordpress.com/2012/04/blog_04_materia.png?w=620&h=189 "Final Fantasy VII Materia")](https://craftofgamesystems.files.wordpress.com/2012/04/blog_04_materia.png)

_The impact of Materia on FFVII character power increases as they gain more slots and more powerful Materia._

Players generally get to choose which power magnifiers they want to take to customize their character, and different classes use different power magnifiers. They key to balancing classes against each other is to ensure their available power magnifiers have equivalent effectiveness.

Power Magnifier Value as a Percentage of Base Power
---------------------------------------------------

**Express the value of a power magnifier as a percentage of a character’s base power.** “Percentage bonus to base power” is the universal unit to use to compare different types of bonuses. Since all power modifiers are relative to base power, I like to define base power at any level as 1.0, for 100%. An unmodified level 1 character has a base power of 1.0, and so does an unmodified level 54 character. If a power magnifier increased a character’s effectiveness by 5%, it would have a value of 0.05.

**To translate a bonus to “effectiveness”, calculate how much it increases the damage a character does in a fight before he is killed.** So, a bonus that keeps him in a fight twice as long would double his effectiveness and have a value of 1.0 (because it is a bonus of 100%).

A particular power magnifier generally becomes available at a certain level, and is tuned to be appropriate for that level. For instance, see the “Affix Level” values in [this chart of Diablo II item affixes](http://diablo2.diablowiki.net/Suffixes). Determine its percentage value relative a character’s base stats at the level it is intended for. Some examples:

**Percentage Damage Bonus**

Imagine a skill that increases character melee damage by 1%. Since this is presumably a skill for melee characters, assume they always get its benefit; so it has a value of 0.01.

**Conditional Damage Bonus**

A sword has a modifier that gives it a 5% chance to deal 30 bonus damage on an attack. This is an average of 1.5 damage per attack. If base damage per attack is 100, then its value is 0.015.

**Percentage Health Bonus**

A 10% bonus to health increases the time that a character stays alive by 10%, thus increasing the damage he does in a fight by 10%, so it has a value of 0.1.

**Armor Bonus**

Say an armor bonus would improve a character’s damage resistance from taking 75% damage from an attack to taking 72%. This means he is taking 72 / 75 = 96% as much damage as he was before, multiplying his survival time by 1 / 0.96 = 1.04 times. Thus, the bonus value is 0.04.

Total Power
-----------

Each power magnifier that a character gets adds to his base effectiveness in combat. His total power is equal to the sum of his base power and all those magnifiers:

> Total Power = Base Power + All Power Magnifiers

Power is relative to character level, so it’s more precise to write:

> Total Power at Level X = Base Power at Level X + All Power Magnifiers at Level X

Remember, base power at any level is defined as 1.0. Thus, a level X character’s total power is the number of times more powerful he is than an unmodified level X character.

### Planning a Progression of Total Power

Total power is what designers care about when tuning stats for content that opposes players, like monsters. As a designer, choose what value you want your game’s various power magnifiers to add to character effectiveness over the course of the game.

Systems can add power at different rates. A skill system might add 1% to total power each level. Unlocking a new ability might add a big chunk at a specific milestone. **Players will focus most on content that has the biggest impact on their power, so assign systems value based on how central they are to your game design.**

Here’s an example of how a total power progression could look. At level 1, no power magnifiers are in effect, so total power is equal to base power:

> Total Power at Level 1 = 1.0

At level 10, the player has 9 skill points, each worth 0.01. He also has bonuses from item modifiers that increase his power by a total of 5%.

> Total Power at Level 10 = 1.0 + 0.09 + 0.05 = 1.14

At level 25, the player now has 24 skill points, his item modifiers are now worth about 27%, and he’s unlocked a super power that increases power by another 20%:

> Total Power at Level 25 = 1.0 + 0.24 + 0.27 + 0.2 = 1.71

In other words, a normal level 30 character is 1.71 times as powerful as a level 30 character with unmodified gear, no skill points spent, and who doesn’t use his super power. We can even chart out his total power over time:  
[![](https://craftofgamesystems.files.wordpress.com/2012/04/blog_04_power_progression.png?w=620&h=380 "Power Progression Chart")](https://craftofgamesystems.files.wordpress.com/2012/04/blog_04_power_progression.png)

In this chart, skills add a linear bonus to power, item modifiers add a gradual quadratic bonus, and ability unlocks add chunks of power every few levels. The purple line shows the total power of a character at each level, and that’s what monsters should be tuned against.

Solving for the Value of a Power Magnifier
------------------------------------------

Now that you’ve defined the expected power progression for characters in your game, you can look up the intended power value of any particular piece of content. For instance, if a level X character should get a 0.05 \* X bonus in power from item modifiers, and is likely to have 10 modifiers on his equipment, then a level X modifier should increase power by 0.005 \* X.

Once you know the intended power of a piece of content, do the math backwards to solve for parameter values that will give the content the intended power. Here are two examples:

**Conditional Damage Bonus**

A level 10 sword has a modifier that gives it a 5% chance to deal X bonus damage on an attack. Say the intended power of a level 10 modifier is 0.06, and the base damage per attack is 100. Thus, it should deal an average of 0.06 \* 100 = 6 bonus damage per attack. Divide by the chance of dealing damage to find X. X = 6 / 0.05 = 120 damage.

**Armor Bonus**

A level 10 helmet has a modifier that increases armor. The intended power of a level 10 modifier is 0.06. For an armor bonus, this means the character should survive 1.06 times as long. Therefore, he should take 1 / 1.06 = 0.94 times as much damage with the modifier as without. Assuming a base character takes 75% damage from an attack, the modifier should be high enough to reduce damage taken to 0.94 \* 75 = 70.5%.

Caveats / Where Doesn’t This Method Work?
-----------------------------------------

This method is best suited for PvE combat in RPGs. Though it can be applied to other types of games, there are some game designs for which it’s simply not a good fit. For example, it would be difficult to apply to action games where damage taken and received vary dramatically with player skill. Imagine an RPG where combat is based on regularly stunning or knocking away foes. It may not be possible to make sufficiently accurate value estimations in those games.

It can also be difficult to apply this method to game content whose value is not easily enumerated. Examples include bonuses to:

*   Projectile weapon or spell range
*   Movement speed
*   Healing power
*   Total mana.

In the case of bonuses like the above, you can either make a sophisticated mathematical model to get an accurate value estimate, or just guess and test, and go with what feels right. Either method can work great.

Good luck and have fun! As always, feel free to post questions in the comments, or comment me at [@DanielAchterman](https://twitter.com/#!/DanielAchterman) or danielachterman@gmail.com.

This entry was posted on April 1, 2012, 5:15 pm and is filed under [Uncategorized](https://craftofgamesystems.wordpress.com/category/uncategorized/). You can follow any responses to this entry through [RSS 2.0](https://craftofgamesystems.wordpress.com/2012/04/01/tuning-rpg-content/feed/ "RSS 2.0"). You can [leave a response](https://craftofgamesystems.wordpress.com/2012/04/01/tuning-rpg-content/#respond), or [trackback](https://craftofgamesystems.wordpress.com/2012/04/01/tuning-rpg-content/trackback/) from your own site.