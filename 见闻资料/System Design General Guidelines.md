_Originally published on [AltDevBlogADay](http://altdevblogaday.com/2011/11/12/the-craft-of-game-systems-part-1/) on November 12th, 2011_

Since this is my first post, I’d like to start with a quick introduction. My name is Daniel Achterman, and I’m a game designer. I’ve been doing gameplay and system design in a variety of genres for about 8 years, mostly RPGs, at companies like Gas Powered Games and ArenaNet. My intention with these pieces is to share specific, practical advice and techniques that game designers can use to create systems, tune content, and simplify their lives.This first piece shares some general guidelines and best practices that I’ve found useful. Future articles will cover topics like experience curves, calculating values for content like item stats and ability damage, and managing large amounts of game data.

If you ever have a question or want to start a conversation, you can reach me in several ways:

*   Add a comment to this post.
*   Send me a message on Twitter: @DanielAchterman
*   Send me an e-mail at DanielAchterman@gmail.com

### What Games Is This Best For?

The approach to game design in these articles is analytical and methodical. It’s best suited to games with a lot of content, like RPGs or strategy games. These articles are more about the hour-to-hour experience than the minute-to-minute experience, so they won’t apply to many types of games. My apologies if this material doesn’t directly translate to your work – I hope you can still find them valuable.

The Hallmarks of Good Systems
-----------------------------

RPG and strategy games tend to have a ton of content – more than any one person can keep in their head at once. Game systems don’t just define how that content works – they are a tool that designers use to generate, tweak, tune, and manage that content.

From a designer’s perspective, good systems should be five things: comprehensible, consistent, predictable, extensible, and elegant.

![](https://lh3.googleusercontent.com/ho-XS3mQXnV3m_NMaW_ADkcNH8hF_MolMKSiKe0-1agFwpB8DGSqpreKnIbvbiTAt1e40x3npYqRtj51UM3_u36zkH9jpIWSzNJeDapMTa40W7Ainh4)  
_This is the Vagrant Story weapon crafting chart. Fun game, but weapon crafting was incredibly obtuse and over-complicated._

**Comprehensible.**You, the designer, should understand all the parts of your system. You should know how you choose various values in your game, why you do it that way, and what other rules and content those values impact. If you want to adjust your gameplay in a specific way, you should know what to change to get that result.

**Consistent.**Your game rules and content should function the same in all areas of your game. Armor shouldn’t work differently for flying units, and the formula for gold value of items shouldn’t change at high levels. This is a big part of making your game comprehensible to you.

**Predictable**. You should be able to determine how your systems will behave in new circumstances. If you multiply experience gained by 2 in some situation, or introduce a monster with double the normal armor, you should be able to predict the results. Using simple progressions and formulas helps make predictable systems.

**Extensible**. When you create new types of content for your game, you should be able to easily extend your existing systems to include it. Maybe you decide what your game really needs is randomly generated minibosses. You should be able to extend your existing monster content to include them easily. Extensibility makes it easier to design your game iteratively, adding new systems and content types as they are needed.

**Elegant.** Elegant systems have a certain … je ne sais quoi. They create extremely rich situations from a small number of moving parts. Some of my favorite examples of elegant system design are 4th Edition D&D, Magic: the Gathering, and Settlers of Catan.

Getting Started: Game Systems Follow Gameplay
---------------------------------------------

Creating a game’s systems and content is an intimidating task. It can seem like there will be a million variables in the game, and before you can start figuring out how they’ll relate to each other, you have to choose which ones your game will have in the first place. What stats will your game characters have? What will increase on level up? What types of upgrades can characters get? Items? Resources? Experience values? Gold costs? It’s overwhelming.

> _“Begin with the end in mind.” – Stephen Covey_

The first step is to clarify the game you’re making. While systems are the foundation of how a game works, they shouldn’t be the starting point of its design. You might have a great idea for how mana regeneration will work in your game, or how leveling will be affected by weapon types. Leave those ideas aside for now, and instead ask yourself: What is the core game loop? What interesting decisions will players be making? What are the appeals you intend your game to have?

Those are the aspects of your game that players engage with most immediately, so your goal when designing systems should be to support the game experience you intend. Form follows function, and systems follow gameplay.

Case Study: Dungeons and Dragons

![](https://lh5.googleusercontent.com/AGw3bYnCLYxgr7JHUL12M_xx0ey1xpsurDEO4d6R_PndYsGSj4fFzdY3uxNW17u2RPsKMYQ7d9B6wRZ75yJP0869YLxv-N6ET7qQK0xCwJA_SwmpgRo)

Dungeons and Dragons is about role-playing characters in a fantasy setting and going on adventures with your friends. Teamwork and cooperation are an important part of the experience. Characters perform actions in turn, with the chance of success and results of those actions defined by systems. To make cooperation matter, there are a variety of types of challenges (combat, disarming traps, social interactions) and combat roles (defender, striker, support) that characters can be strong or weak in.

As a systems designer, the above description would direct my work in several ways:

*   To encourage teamwork, systems should allow characters to excel in certain types of challenges and combat roles, but not others.
*   Role-playing and non-combat play is important, so social statistics should be meaningful.
*   Since immersion and role-playing are important, the content of the game should be flavorful and exciting in a fantasy setting.
*   The math to determine the results of actions should be comprehensible and uncomplicated.

The Components of Game Systems
------------------------------

“Game Systems” or “Mechanics” can be broken down into three components: Parameters, Rules, and Content.

*   **Parameters:** Parameters are the values that your game systems use to simulate your game, such as health, movement speed, weight, mana cost, critical hit chance, etc.
*   **Rules:** Rules are the functions and formulas that determine the results of actions and events in your game. Rules include things like how combat damage is calculated, how character statistics change when they level up, and how random loot is determined.
*   **Content:** Content is all things in your game, including characters, items, monsters, spells, talents, etc. Each type of content has parameters that define it, like damage for a weapon, or  attributes for a character.

![](https://lh4.googleusercontent.com/uEllym2VNLeR_U-nJjrOohiYFTdMY3ul5lnOYxVTBcSZtNugmZqF78d8eT6fkCtw5sCWHnuZtmT8SElGkQwbjKwLoruUb_Z1bT4tuLdqShTmjbj2Foo)

In this screenshot of Final Fantasy XIII, the content is the monsters, characters, and the weapons they’re using. The parameters are the values for all of their stats that affect combat, such as their health. The damage values when the hero strikes a monster are determined by rules, using the character parameters and some randomization.

![](https://lh5.googleusercontent.com/zwq2HJcAWz8rEKt1s71TOdjv-3tZ8Usun_6aEDd85c2hPNC9sUQez0DQ1EI24PA5xBkqi7w9JGMgQ_b0YwQjblG_8RuzJZzUx-J8f2-dmqm27gi3YYw)

For a different kind of example, the content in Magic: the Gathering is the cards. Each card in the game represents a noun that players can summon, like a creature or land, or an action that players can perform, like casting a spell. The rules define the different types of cards and how they function. This creature’s special abilities also fall under rules, as does its “Creature” type, as that defines its functionality in the game’s rules. The creature type, costs, stats, and ability values are all parameters.

Designing a Game System in Five Steps
-------------------------------------

Once you’re ready, break the task down into pieces and tackle one at a time. This is the process that I use to design and iterate game systems:

1.  Choose the parameters that your game uses.
2.  Design rules that are no more complex than necessary to implement your game vision.
3.  Define the progressions for how parameters change throughout the game.
4.  Design content types that are as complex and interesting as you can manage.
5.  Add new parameters, systems, and content types in layers as needed.

Parameters are the first step because choosing them helps focus what aspects of gameplay need to be reflected in your systems. While parameters are closely related to content, if you start by thinking of all the types of content your game will include, it’s easy to bloat your parameter list. Starting with parameters and then rules for how they interact helps you make the hard cuts up front and keep your content and rules lean.

My next article will cover this process in more detail and offer guidelines for how to choose parameters, design rules, and design content types that will result in a system that is powerful and flexible.

Conclusion
----------

Much of game design is an art. The quality of content and the appeal of various design choices are subjective and vary from player to player. Good system design is more of a craft. Game systems are a tool that designers use for creating and tweaking content. In terms of ease of tweaking and resistance to degenerate cases in games, some system designs are objectively superior to others.

I adore investigating game systems. I love seeing how designers organize their data, reverse engineering their content progressions, and trying to figure out why they used the formulas they did. I hope you enjoyed this introduction, and I’m looking forward to sharing more techniques and examples soon. Please let me know what you think in the comments!

This entry was posted on December 30, 2011, 6:18 pm and is filed under [Uncategorized](https://craftofgamesystems.wordpress.com/category/uncategorized/). You can follow any responses to this entry through [RSS 2.0](https://craftofgamesystems.wordpress.com/2011/12/30/system-design-general-guidelines/feed/ "RSS 2.0"). You can [leave a response](https://craftofgamesystems.wordpress.com/2011/12/30/system-design-general-guidelines/#respond), or [trackback](https://craftofgamesystems.wordpress.com/2011/12/30/system-design-general-guidelines/trackback/) from your own site.

---


由于这是我的第一篇文章，我想先简单介绍一下。我的名字是Daniel Achterman，我是一名游戏设计师。我从事各种类型的游戏和系统设计大约有8年时间，主要是RPG游戏，在Gas Powered Games和ArenaNet等公司工作。我写这些文章的目的是为了分享具体的、实用的建议和技术，让游戏设计师可以用来创建系统、调整内容和简化他们的生活。这第一篇文章分享了我发现的一些一般准则和最佳做法。未来的文章将涵盖经验曲线、计算物品属性和能力伤害等内容的数值，以及管理大量的游戏数据等主题。

如果你有问题或想开始对话，你可以通过几种方式联系我。

* 在这篇文章中添加评论。
* 在Twitter上给我发消息。@DanielAchterman
* 给我发电子邮件：DanielAchterman@gmail.com

###这最适合什么游戏？

这些文章中的游戏设计方法是分析性和方法性的。它最适合于有大量内容的游戏，如RPG或战略游戏。这些文章更多的是关于每小时的体验，而不是每分钟的体验，所以它们不适用于许多类型的游戏。如果这些材料不能直接转化为你的工作，我深表歉意--我希望你仍然能发现它们的价值。

优秀系统的标志
-----------------------------

RPG和策略游戏往往有大量的内容--比任何一个人都能同时记住的内容多。游戏系统不仅定义了这些内容如何运作--它们是设计者用来生成、调整、调节和管理这些内容的一种工具。

从设计师的角度来看，好的系统应该有五点：可理解、一致、可预测、可扩展和优雅。

![](https://lh3.googleusercontent.com/ho-XS3mQXnV3m_NMaW_ADkcNH8hF_MolMKSiKe0-1agFwpB8DGSqpreKnIbvbiTAt1e40x3npYqRtj51UM3_u36zkH9jpIWSzNJeDapMTa40W7Ainh4)  
这是《流浪者故事》的武器制作图。有趣的游戏，但武器制作是令人难以置信的愚昧和过度复杂的。

**易懂。**你，设计师，应该了解你系统的所有部分。你应该知道你在游戏中如何选择各种数值，为什么这样做，以及这些数值会影响哪些其他的规则和内容。如果你想以一种特定的方式来调整你的游戏，你应该知道要改变什么来获得这种结果。

**你的游戏规则和内容应该在你的游戏中的所有领域发挥同样的作用。盔甲不应该对飞行单位有不同的作用，物品的金币价值公式在高等级时不应该改变。这是使你的游戏能够被理解的一个重要部分。

**可预测**。你应该能够确定你的系统在新的情况下会有怎样的表现。如果你在某些情况下将获得的经验乘以2，或者引入一个具有双倍于正常装甲的怪物，你应该能够预测结果。使用简单的进阶和公式有助于制造可预测的系统。

**可扩展的**。当你为你的游戏创造新类型的内容时，你应该能够很容易地扩展你现有的系统以包括它。也许你决定你的游戏真正需要的是随机生成的小怪兽。你应该能够轻松地扩展你现有的怪物内容以包括它们。可扩展性使你更容易反复设计你的游戏，在需要时增加新的系统和内容类型。

**优雅。优雅的系统有某种......je ne sais quoi。他们用少量的活动部件创造出极其丰富的情况。我最喜欢的一些优雅系统设计的例子是第四版D&D、《魔法：聚集》和《卡坦岛的居民》。

入门。游戏系统遵循游戏规则
---------------------------------------------

创建一个游戏的系统和内容是一项令人生畏的任务。在游戏中似乎会有一百万个变量，在你开始弄清它们之间的关系之前，你必须首先选择你的游戏将有哪些变量。你的游戏角色会有哪些属性？级别提高后会增加什么？角色可以得到什么类型的升级？物品？资源？经验值？金币成本？这让人目不暇接。

> _"开始时要考虑到目的。" - 斯蒂芬-柯维_

第一步是明确你要做的游戏。虽然系统是游戏运作的基础，但它们不应该是游戏设计的起点。你可能对法力再生在你的游戏中如何运作有很好的想法，或者等级如何受武器类型的影响。现在先把这些想法放在一边，而是问问自己。游戏的核心循环是什么？玩家将做出哪些有趣的决定？你希望你的游戏有哪些吸引力？

这些都是玩家在游戏中最直接接触到的方面，所以在设计系统时，你的目标应该是支持你打算的游戏体验。形式服从功能，系统服从游戏性。

案例研究。龙与地下城

![](https://lh5.googleusercontent.com/AGw3bYnCLYxgr7JHUL12M_xx0ey1xpsurDEO4d6R_PndYsGSj4fFzdY3uxNW17u2RPsKMYQ7d9B6wRZ75yJP0869YLxv-N6ET7qQK0xCwJA_SwmpgRo)

龙与地下城是关于在一个幻想的环境中扮演角色，和你的朋友一起去冒险。团队精神和合作是这种体验的重要组成部分。角色依次进行行动，这些行动的成功机会和结果由系统定义。为了使合作变得重要，有各种类型的挑战（战斗、解除陷阱、社会互动）和战斗角色（防御者、前锋、支持），角色可以在这些方面表现得很强或很弱。

作为一个系统设计师，上述描述会在几个方面指导我的工作。

* 为了鼓励团队合作，系统应该允许角色在某些类型的挑战和战斗角色中表现出色，而不是其他。
* 角色扮演和非战斗游戏是很重要的，所以社会统计数据应该是有意义的。
* 因为沉浸感和角色扮演很重要，所以游戏的内容应该是有味道的，在幻想的环境中是令人兴奋的。
* 决定行动结果的数学应该是可理解的和不复杂的。

游戏系统的组成部分
------------------------------

"游戏系统 "或 "机制 "可以被分解为三个组成部分。参数、规则和内容。

**参数：**参数是你的游戏系统用来模拟你的游戏的数值，如健康状况、移动速度、重量、法力值、关键打击机会等。
**规则：**规则是决定你游戏中行动和事件结果的函数和公式。规则包括诸如战斗伤害是如何计算的，角色的统计数据在他们升级时如何变化，以及随机战利品是如何确定的。
**内容：**内容是你游戏中的所有东西，包括人物、物品、怪物、法术、天赋等等。每种类型的内容都有定义它的参数，如武器的伤害，或角色的属性。

![](https://lh4.googleusercontent.com/uEllym2VNLeR_U-nJjrOohiYFTdMY3ul5lnOYxVTBcSZtNugmZqF78d8eT6fkCtw5sCWHnuZtmT8SElGkQwbjKwLoruUb_Z1bT4tuLdqShTmjbj2Foo)

在这张《最终幻想13》的截图中，内容是怪物、角色和他们所使用的武器。参数是他们所有影响战斗的属性值，例如他们的健康状况。英雄打击怪物时的伤害值由规则决定，使用角色参数和一些随机化。

![](https://lh5.googleusercontent.com/zwq2HJcAWz8rEKt1s71TOdjv-3tZ8Usun_6aEDd85c2hPNC9sUQez0DQ1EI24PA5xBkqi7w9JGMgQ_b0YwQjblG_8RuzJZzUx-J8f2-dmqm27gi3YYw)

对于一个不同的例子，《魔术：集会》的内容是卡片。游戏中的每张卡都代表了玩家可以召唤的名词，如生物或土地，或者玩家可以执行的行动，如施法。规则定义了不同类型的卡牌以及它们的功能。这个生物的特殊能力也属于规则范畴，它的 "生物 "类型也属于规则范畴，因为这在游戏规则中定义了它的功能。生物的类型、费用、统计资料和能力值都是参数。

设计一个游戏系统的五个步骤
-------------------------------------

一旦你准备好了，就把任务分解成几块，一次解决一个。这是我用来设计和迭代游戏系统的过程。

1.  选择你的游戏所使用的参数。
2.  设计规则，其复杂程度不超过实现你的游戏愿景所需。
3.  定义参数在整个游戏中如何变化的进程。
4.  设计尽可能复杂和有趣的内容类型，这是你可以管理的。
5.  根据需要分层添加新的参数、系统和内容类型。

参数是第一步，因为选择参数有助于集中游戏性的哪些方面需要反映在你的系统中。虽然参数与内容密切相关，但如果你一开始就想到你的游戏将包括的所有内容类型，就很容易使你的参数列表膨胀。 从参数开始，然后为它们之间的互动制定规则，可以帮助你在前面做出艰难的削减，并保持内容和规则的精简。

我的下一篇文章将更详细地介绍这个过程，并提供如何选择参数、设计规则和设计内容类型的指南，从而形成一个强大而灵活的系统。

结论
----------

游戏设计的大部分内容都是一种艺术。内容的质量和各种设计选择的吸引力是主观的，并且因玩家而异。好的系统设计则更像是一门手艺。游戏系统是设计师用来创造和调整内容的工具。就调整的难易程度和对游戏中变质情况的抵抗力而言，一些系统设计客观上优于其他。

我很喜欢研究游戏系统。我喜欢看设计师如何组织他们的数据，逆向工程他们的内容进展，并试图弄清楚他们为什么使用他们所做的公式。我希望你喜欢这个介绍，我期待着尽快分享更多的技术和例子。请在评论中告诉我你的想法!