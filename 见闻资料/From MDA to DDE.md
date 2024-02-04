---
created: 2022-05-22T23:05:36 (UTC +08:00)
tags: []
source: https://www.gamedeveloper.com/design/from-mda-to-dde
author: Wolfgang Walk
---

# From MDA to DDE

> ## Excerpt
> Thinking about the MDA framework I realized there is currently no way to implement narrative design structures into MDA, and for that reason alone (there are others) I believe it’s time to update the MDA framework.

---
## From MDA to DDE

### **Necessary enhancements on a commendable design framework**

by Wolfgang Walk

**After decades in game development, and after deciding to write a book about the role and rules of narrative design within the greater game design process, I recently found myself thinking intensively about the MDA framework. In doing so I realized there is currently no way to implement narrative design structures into MDA, and for that reason alone (there are others) I believe it’s time to update the MDA framework. Not because it’s useless, but because it is not the optimal tool it could be.**

In 2004 I watched a GDC talk by Marc LeBlanc, who worked on Ultima Underworld 2, System Shock and Thief. The talk was about a formal approach to game design – and the noise you could hear during the talk came from dropping jaws hitting the floor. Here was someone who had delved deeply into the structures behind the design process. We all knew there must be a structure behind game creation – or at least we hoped there was -- and suddenly someone was showing us that structure.

Yet maybe the most important takeaway for me back then was: yes -- we could do it. We could understand what a game was on an intellectual level instead of finding our way by feel.

An accompanying paper, published the same year by Hunicke, LeBlanc and Zubeck, made the approach officially academic. \[1\]

**The MDA Model in a nutshell**

    

Pic 1: Goal of the MDA paper by Hunicke, LeBlanc & Zubek, 2004

The authors of the paper defined the eponymous parts of the MDA framework - Mechanics, Dynamics and Aesthetics - as follows:

Mechanics describes the particular components of the game, at the level of data representation and algorithms

Dynamics describes the run-time behavior of the mechanics acting on player inputs and each other’s outputs over time.

Aesthetics describes the desirable emotional responses evoked in the player, when she interacts with the game system**\[2\]**

As far as I know, MDA was the first design framework that was adopted by both computer science and also at least a faction of the industry. Some developers really took to it, but it became a real hit in design schools and universities, where it is taught and welcomed by students to this day.

Part of that academic continuity, however, is predicated on the fact that the MDA model still stands exactly as it was erected by LeBlanc and his colleagues. And yet I’m pretty sure that’s not what they intended when they first published the model. Instead, I believe they wanted to start a discussion -- to put the MDA model to the test, to fix it when it broke, to enhance it where necessary and ultimately to build a practical tool for the creation of games as _well_ as an academic tool for criticism.

In the modern development environment, MDA not only fails to provide a framework for narrative design, there is no coherent interface. Is narrative design a component of mechanics? In part, yes, but hardly as a whole. It certainly doesn’t belong to dynamics – and also not to aesthetics as defined by Hunicke and colleagues. Every attempt to apply MDA to narrative design rules stretches MDA to the breaking point.

The MDA model now is more than 11 years old, which is quite an achievement in an industry that reinvents itself every 2-3 years. Only recently, during the past few months, have we seen articles in which the model has been deeply analyzed, criticized and challenged. The model has been discussed on Gamasutra by Luis Claudio Silveira Duarte\[3\], and an article by Lana Polansky\[4\] was followed by another by Frank Lantz\[5\], both making good comments on the topic. All of those voices in turn helped focus my own mind about MDA, and enabled me to better understand the sub-structures of game narratives.

I have nothing but the greatest respect for the pioneering work of Hunicke, LeBlanc and Zubek. But just like a Mercedes of today hardly resembles the first Benz motor car, we have to progress. There are problems with the MDA model – and the articles by Polansky and Lantz show that I am not the only one who wants to work _on_ the framework so we can again work _with_ it. We need such a model, and those articles do not discredit MDA or argue that a design framework is worthless. They show where MDA has weaknesses, and how we can overcome those weaknesses by fixing and enhancing the model.

Unfortunately, MDA will probably lose its acronym in the process because some of the biggest problems have to do with how the basic categories of MDA have been shaped. For reasons that will be made clear, in my own opinion MDA should evolve into DDE: Design/Dynamics/Experience.

**90 % of MDA “mechanics” are not actually mechanical …**

In MDA, **Mechanics** describes the particular components of the game at the level of data representation and algorithms. One obvious problem with that approach is that’s it’s like describing an assembled car as “motor, gearbox and wheels“, when a car is obviously much more. To the extent that “data representation“ is mentioned it is only to a small degree “mechanical“. To a much greater degree it is “aesthetical“, because the data represented often consists of graphics or sound assets.

Worse, MDA terminology now begins to conflict with itself. Wasn‘t “aesthetics” meant to be the emotional player response, which is something completely different from data representation? As Frank Lantz explained in his article, “mechanics” in the MDA model basically means everything that is directly designed by the designer under no direct influence by the player: _“But even more problematic is the term “mechanics”. Again, MDA wants to use this word broadly to refer to _all_ of the stuff that the designer has control over – not just the rules of the game but the materials as well, the recipe _and_ the ingredients.“**\[6\]**_ I agree with Lantz’s interpretation.

To drive the point home that the term _mechanics_ doesn’t really fit as a description, here is an incomplete list of things that the designer has full control over, which thus belong to the MDA category of “mechanics”:

-   GAME CODE: Game Architecture, I/O, Game Objects, Game Rules (code level), Interface (code level), Interaction Design (code level) …
-   GAME RULES (documentation): Structure, Balancing, Timing, Space, Plot Branching, …
-   WORLD DESCRIPTION (documentation): World & Game Rules, Flora & Fauna, Societies, Characters, Religions, Laws, Physics …
-   STYLE (documentation): Graphics, Sound, Narrative, …
-   FUNCTIONAL INTERFACE (data representation): diegetic, non-diegetic, spatial, meta
-   CONTENT INTERFACE (data representation): Interaction Design (interface level), Graphics & Sound, Narratives, …\[7\]

As you can see, for a number of items on the list it‘s problematic to summarize them under the “mechanics” label. Some of the items aren’t mechanical at all, like graphics style, which is clearly an aspect of aesthetics, yet is also under direct control of the designer before it becomes part of the final game experience. If we further argue that a graphical style guide is not represented on the level of data representation or algorithms, then the MDA model leaves no place for that crucial design decision – proving MDA to be incomplete as a framework.

**… but all of it is directly designed by the designers!**

When I began trying to re-frame the MDA model I adopted two lenses. First, I wanted to focus on the production process of a game, especially with regard to its iterative nature. My version of the model needed to allow for that. The second lens came from a seemingly different angle that is in fact closely related. Why do game stories so often suck? I wanted a better understanding of narrative as an entity inside the MDA model – but it wasn’t where I thought (and still think) it should be.

I am a producer and narrative designer by profession, so both of those lenses came naturally to me. As noted above I am writing a book about narrative design, and those two lenses also form the foundation of that book. But in order to actually build games on that foundation I need a functional design framework in which narrative design can fulfil both its potential and obligations. My goal is thus to re-build the MDA framework so it will better support the notion of a journey for both lenses: the actual production of a game, and the eventual perceptive journey by the player. Yet no matter where I look, neither of those journeys are anywhere to be found in the MDA model.

While thinking about a re-framed “mechanics“ category I came up with three sub-categories that allowed me to make clear distinctions without leaving blurry concepts lurking in-between.

    

Pic 2: The "Design" part of the DDE model

The above graph shows my take on what Zunicke and colleagues called “mechanics”, and what I would rather call “design”. Everything in that graph is directly designed by the designers, who have full control over that stage of the process. (The term “design” was also proposed by Jesper Juul in an online discussion following Frank Lantz‘s article, but I don‘t know if Jesper would agree with my sub-structures.)

**“Design” still has three important sub-categories, one of which is “Mechanics”**

The subcategories under Design are:

**BLUEPRINT:** Blueprint is manifested by that part of the design that deals with the game world _in concept:_ its cultures, religions, physics and other rule sets; the free form notation of the game mechanics; and the developed styles of art design, narrative design, character design, and sound design. It is what the common understanding of “design” means: laying out ideas, painting, writing, inventing a world and its functionality, documenting it all in a Wiki and launching it into the iterative process necessary to become a solid foundation of the game itself. (For a while I used the term “setting” for this sub-structure, but blueprint now seems much clearer to me, since it reflects the dominance of planning and documentation throughout this development stage.)

**MECHANICS:** Mechanics remain in the framework, but are now much more specific. They include everything that will finally create the physical game _in the abstract_, meaning: in code. Mechanics are about the code architecture, the input/output handling, the object handling, the implementation of the game rules and object interaction, and other code-related stuff. It is what the player does not directly see or hear during play. Code remains invisible, makes no noise, and can only be experienced via the interface.

**INTERFACE:** Interface contains the design and production of everything that will finally create the physical game _in the concrete_, meaning: everything that serves to communicate the game world to the player -- how it looks, how it sounds, how it reacts and interacts with the player and the game’s feedback loops. Interface also contains the report system that every game needs, be it diegetic or non-diegetic, spatial or meta.\[8\] Thus every graphic asset, sound asset, cutscene or piece of text is part of the interface as long as it is also part of the game data. It is everything the player hears and sees, every piece of data that doesn’t belong to the executable or configurative code level of the game.

**One of the big achievements of the MDA framework: Recognizing the function of dynamics!**

Building on the “design” category there were considerably fewer problems with the category of ”Dynamics“, though in practice we‘re still waiting for tools that will help us gain more control over that part of the creative process, thus saving us expensive design iterations. As Frank Lantz correctly noted: _“For me, the greatest strength of MDA is that it emphasizes the “second order” nature of game design. _Mechanics_ is used to refer to the parts of the game that the designer has direct control over, _aesthetics_ refers to the qualities of player experience that the game ultimately generates, and in between, linking the two, are the _dynamics_ of the game in action – the behavior of the game’s different parts interacting with each other and the player while the game is being played.” **\[9\]**_

In the DDE version of the framework I extrapolate a bit on dynamics in order to add a little more detail, especially with regard to the different perspectives that designers and players have.

    

Pic 3: The "Dynamics" part of the DDE model

Returning to the Mercedes metaphor above, if “design” contains the planning for all of the parts of the assembled car, as well as the assembled parts themselves, “dynamics” defines what happens when you start the engine and all the assembled pieces work together: the pistons, crank shaft and valves of the motor, the gear box, suspension, the springing of the seats, the street, the weather, the driving style, the tremor of the steering wheel, the noises, even the song on the car stereo.

Note that this part of the design framework is _still_ under full control by the designer – at least in theory, assuming an iterative design process. In practice there will always be too many different players to predict every behavior that each player might engage in. Thus the control of the designer is indirect, because all the designer can change throughout the iterative creation process falls into the category of “design” – where “dynamics” always adds a layer of emergence and unpredictability.

While the _player_ is confronted with the dynamics of a game, that confrontation also is indirect. As Miguel Sicart has shown, the indirect nature of interaction happens via the creation of the player-subject.\[10\] Because that term will become important later, we will introduce it in some detail here:

The player-subject is based on the theory that it is not really _us_ who are playing games, but subsets of ourselves. One can imagine the player-subject as similar to a mental avatar, a character existing solely in the mind that is able to make decisions we would never be able to make in real life. This is a character with a different set of abilities than we have – and a different set of ethics. In a lot of ways we put the player-subject into mentally dangerous situations in games to experience that danger without our real selves getting in harm’s way. Thus we can experience and explore ethically and mentally challenging situations from a safe place. We can rake in all the benefits and rewards without risking the trauma that such real-life situations could cause.

In the context of dynamics, as well as the greater framework, the designer and the design thus do not deal with the player directly, but with the player-subject. It is that instance or aspect of the player that makes decisions while playing.

**The term “Aesthetics” leaves out what game design really is: experience design**

“Dynamics” is all the parts of a car in unified action, plus any external influences, but it is NOT the driving experience! Inside the original MDA framework that would be referred to as “aesthetics”, but there are a lot of reasons why “aesthetics” is an even worse term than “mechanics” – and why I believe that “experience” would be better.

I have already pointed out that a lot of the stuff the MDA framework files under “mechanics” results from working on deeply aesthetical design questions. Thus calling a completely different category “aesthetics” would be questionable in itself. But the problem runs deeper:

“Aesthetics” is a term used in philosophy in at least two ways:

1.  It‘s used in phenomenology, in trying to answer the question of HOW we perceive things. Kant for instance claimed that we cannot perceive anything independent from time and space, because these are two a priori intuitions we can‘t help but have.
2.  Aesthetical theory tries to answer the question of WHY we perceive something as beautiful or ugly, as art or non-art. What is it that creates beauty or art in our eyes and mind?

But “aesthetics” is also a psychological term, having to do with how different people perceive the same color, sound, melody, picture or text in completely different ways, as well as trying to understand the reasons and implications behind those differences. What is it in our mind that determines the volatility of our perception? And if that’s not confusing enough, “aesthetical” is also an everyday synonym for “beautiful” or “well-shaped”.

You can see how “aesthetics” as a term can easily become mixed up with the aesthetical side of the MDA design process. Even worse, the term is controversial even among philosophers, and its use among artists was famously denounced - not entirely without reason - by Barnett Newman, who quipped: “Aesthetics is for the artist as ornithology is for the birds.”

    

Pic 4: The "Experience" part of the DDE model

Any practical game design framework should have at its core the goal of helping game designers understand how to approach their daily work. It should help frame the development process, while also accurately representing the underlying art form. A framework loaded with philosophical terms that are only useful for assessing art _after_ it has been created is by definition of no practical use. If the DDE model can help the critics (and I’m sure it can), that’s a bonus, but first and foremost DDE is for the artists.

In theory, of course, what we know from the various fields of aesthetics can help us make design decisions. In practice, a game often turns out to be too complex to plan detailed aesthetic effects in advance. But even the fact that knowledge of aesthetics can help us make design decisions is hardly sufficient for naming an entire sub-structure of a design framework after that murky word, particularly when the designer does not have full control over its effect. Even worse: calling it “aesthetics” neglects everything that really IS central to that design category, which is “experience.”

Let’s recall the definition given by the MDA paper: _“**Aesthetics** describes the desirable emotional responses evoked in the player, when she interacts with the game system.”_ Any reading of that definition involves time and space, in most cases over hours and hours of play. But for the participants something that is happening over time and in space is necessarily a journey, an experience. Game design is (or should be) experience design – and in fact that _is_ mentioned in the MDA-paper: _“In addition, thinking about the player encourages experience-driven (as opposed to feature-driven) design.”_

**As soon as there are dynamics, those dynamics can be experienced**

That‘s why I, in line with Jesper Juul, suggest changing the MDA category of “aesthetics” to “experience”. Experience starts as soon as the player plays the game. It is not separated in time from the dynamics, because dynamics also need time and space as _a priori intuitions_. When there are game dynamics, the player-subject can experience those dynamics. If the dynamics are sophisticated enough to create an antagonist for the player-subject, the game becomes a worthy opponent. As a result, playing the game over time will create a journey that works on many different levels:

**Senses:** The organoleptic journey consists of all the sensory experiences the player has from start to finish. It’s the totality of what the player sees, hears and senses through the available output devices.

**Cerebellum:** The emotional journey consists of all the emotions the player experiences while playing the game. It’s the emotional ride the player experiences, the fears and horrors, sadness, guilt and anger, and whatever other emotions the game evokes.

**Cerebrum:** The intellectual journey consists of all the challenges and decisions the player experiences and contemplates with the conscious mind.

Together the three journeys will be formative for the player’s _perception_ of the game. This perception has many names and sub-concepts, and whatever the game experience is worth in various parts of the perceptive universe is a matter of personal taste and bias.

If we look at the role of the player we see that perception is the level of immediate confrontation. That is where all of the senses, emotions and intellectual capabilities are confronted directly – or would be if the player did not create the protective layer of a player-subject.

From the perspective of the designers, that is also the level where we will lose full control over the work (even indirectly), because that is where the individual perception of the player takes over. During the player’s experience of the game, the player is no longer restricted by the code. The player can sense, feel and think whatever they want about the experience. They can like it or hate it, enjoy it or find it boring, get what they wanted or didn’t expect, be challenged or taken to the emotional brink.

The better the designer knows the target audience, and the better the game targets that audience, the better the game will be received. That is why objective criteria can only take design so far – and why knowing the expectations of your audience is critical to all measures of success.

    

Pic 5: The whole DDE Model

With the DDE subcategories in place, it’s time to define the relationship between the different parts.

From the original MDA framework: _“Each component of the MDA framework can be thought of as a ‘lens’ or a ’view’ of the game - separate, but causally linked. \[LeBlanc, 2004b\]. From the designer’s perspective, the mechanics give rise to dynamic system behavior, which in turn leads to particular aesthetic experiences. From the player’s perspective, aesthetics set the tone, which is born out in observable dynamics and eventually, operable mechanics.”**\[11\]**_

Apart from the terminology used the sequencing is obviously correct, and the DDE system supports that explanation if we simply replace the old terms with the new ones. But there is a danger of misconception underlying the entire premise, because that sequencing does _not_ describe a timeline. Instead, everything in that design sequence can happen at the same moment.

For designers that is the description of an iterative process, where every decision on every level can change the whole game. For the player that is what they are doing and experience when playing a game. The player senses the world _and_ analyzes the underlying mechanics at the same time, from start to finish, confronting and experiencing every aspect of the design. (In practice designers are also the first players – or at least should be.) And that’s why we need to add one more term in order to strengthen a specific perspective: the _game as a_ _confrontation_ over time and space; a set of challenges that can create a wide range of perception journeys, depending on what the designer has created and how the player understands it.

**A good game must be a good antagonist for the player-subject**

Since we renamed the last category “experience”, at this juncture it makes sense to describe the entire framework more from the player’s angle than from the designer’s point of view. Ultimately the designer has to understand the perspective of the gamer to make a great game, and at the risk of repeating myself, game design IS experience design!

That’s where the concept of the “antagonist” comes into play. The antagonist is well-known from storytelling and other narrative art forms. In different guises the antagonist exists in basically every art form, be it counterpoint in music or complementary colors in painting. And the reason is obvious: it is through conflict, or contrast, or tension, that almost all art generates interest at differing levels of awareness.

If a designer thinks of the dynamics of a game system as the antagonist of the player-subject, that perspective allows the designer to comprehend the whole experience of playing a game as a narrative. Yes, there are certain expectations we have about narratives, and good designers will anticipate those expectations when creating a great narrative experience. If the antagonist of a narrative doesn’t fulfil that role, the narrative will be boring, or at least less interesting than it might have been, and it may even fall apart.

In talking about narrative we do not only mean any embedded story that the designer creates for the game.\[12\] Of course any embedded narrative (including deciding whether one should be included at all) should support and reinforce the complete experience. If the perception journey and the embedded narrative don’t match we get what Clint Hocking has called the “ludo-narrative disconnect”\[13\].

When played, every game creates an over-arching meta-story, an emergent story. But in order to do that successfully the game must become the worthy antagonist of the player-subject. And just like the antagonist of every story is responsible for the set of challenges the hero has to overcome, the antagonist that is the game system is responsible for the obstacles the player will encounter and overcome (or not) while playing.

Even if you prefer different terminology, I think we can all agree that a well-defined design framework should show that connection. If the game is not the right challenge for the gamer -- if it’s not a worthy antagonist -- the player will stop playing, or continue playing but be underwhelmed or even bored. The DDE framework supports the notion of conflict from abstract to literal; MDA doesn’t mention it at all.

**Design, dynamics and experience are not production stages**

Returning to the designer’s (or producer’s) point of view, again, the three sub-structures of the DDE framework are not to be interpreted as production stages. They are, rather, what one must understand in order to set up an effective iterative process for creating a game. As noted above, the first players of any game will usually be the developers themselves. They iterate the design through change after change until the dynamics begin to produce the desired effects. They are the first ones to perceive the game and to get an idea of the journey it will produce for the audience. With each iteration, every single line of code and every single asset, whether it be graphics, sound or narrative, can be adjusted to alter the effect that the game has _as_ an experience.

Iterative production cycles today should be a given, but in my experience they are the first thing to go when time and money are running out. Unfortunately, without them you _cannot_ develop a good game. A thousand-piece jigsaw puzzle thrown in the air is never going to put itself together. And games usually have considerably more than a thousand pieces.

The DDE model allows designers to assess and re-assess the value of story within the overall framework of game development. Look again at the entries in the blueprint substructure and you’ll see that nearly all of them have a narrative connotation. And as a first consequence of that, it is long past time that narrative design be considered an integral part of any design process from day 1. (The persistent disregard for narrative design is an artifact of commercial conventions and power dynamics which have nothing to do with MDA or academic criticism.)

The DDE framework is obviously not finished. So far it serves the purpose it was created for, which is laying out a stable foundation for the things I want to talk about in my book. As time passes and I think about it more deeply the framework will inevitably undergo more changes Some of the terminology may change, some definitions will get more attention, and there are still a few areas I have yet to fully explore.

Still, it has become sufficiently stable that I am now looking for feedback from any quarter, because I know I can’t finish it on my own. There are too many fields involved where I simply don’t have the expertise. So it’s time for other voices and other lenses to come into play. It’s time we try to rip this and every other framework to pieces to see if there’s anything of worth.

Let’s not wait another eleven years.

(Since I'm not a native speaker this blog post has been edited for correct English by Mark L. Barrett, a long-time friend and brother in arms. I owe you, Mark! Please visit Mark's blog "The Ditchwalk", where you can find lots of insightful posts about interactive storytelling: http://www.ditchwalk.com/category/interactive/ )

___

\[2\] l.c., p2.

\[6\] l.c.

\[7\] For me everything that is displayed on screen or can be heard through the speakers is part of the game’s interface, because it translates the abstract layer of code into something the player can understand more easily. This has certain implications as you will notice later in the article.

\[9\] l.c.

\[10\] Miguel Sicart: The Ethics of Computer Games, Cambridge/London, 2009.

\[11\] l.c., p. 2


在从事了几十年的游戏开发之后，在决定写一本关于叙事设计在更大的游戏设计过程中的作用和规则的书之后，我最近发现自己对MDA框架进行了深入思考。在这样做的过程中，我意识到目前还没有办法在MDA中实现叙事设计结构，仅仅因为这个原因（还有其他原因），我相信现在是更新MDA框架的时候。不是因为它没有用，而是因为它不是最佳的工具。

2004年，我观看了Marc LeBlanc在GDC的演讲，他曾参与过《Ultima Underworld 2》、《System Shock》和《Thief》。讲座的内容是关于游戏设计的形式化方法--在讲座中你能听到的声音来自于掉在地上的下巴。这是一个对设计过程背后的结构进行深入研究的人。我们都知道游戏创作背后一定有一个结构--或者至少我们希望有--而突然有人向我们展示了这个结构。

然而，对我来说，当时最重要的收获是：是的，我们可以做到这一点。我们可以在知识层面上理解游戏是什么，而不是靠感觉来寻找方向。

同年，Hunicke、LeBlanc和Zubeck发表了一篇附带的论文，使这种方法成为正式的学术。\[1\]

**MDA模型的简述**。
 

图1：Hunicke, LeBlanc & Zubek, 2004的MDA论文的目标

该论文的作者对MDA框架的同名部分--机制、动力学和美学--定义如下。

机制描述了游戏的特定组成部分，在数据表示和算法的层面上。

动力学描述了随着时间的推移作用于玩家输入和彼此输出的力学的运行时间行为。

美学描述了当玩家与游戏系统互动时引起的理想的情感反应**[2]**。

据我所知，MDA是第一个被计算机科学和至少是业界的一个派别采用的设计框架。一些开发者真正接受了它，但它在设计学校和大学里成为了真正的热门，直到今天它还在那里被教授并受到学生的欢迎。

然而，这种学术上的连续性的一部分是建立在MDA模型仍然与LeBlanc和他的同事们建立的模型一模一样的事实之上的。然而，我非常肯定这不是他们首次发表该模型时的意图。相反，我相信他们想开始一场讨论--对MDA模型进行测试，在它破损时进行修复，在必要时进行改进，最终建立一个实用的游戏创作工具，以及一个学术批评工具。

在现代开发环境中，MDA不仅没有为叙事设计提供一个框架，而且没有连贯的接口。叙事设计是机制的一个组成部分吗？部分是的，但很难作为一个整体。它当然不属于动力学--也不属于Hunicke及其同事所定义的美学。将MDA应用于叙事设计规则的每一次尝试都将MDA延伸到了崩溃的边缘。

MDA模型现在已经有11年多的历史了，这在一个每2-3年就会自我重塑的行业中是一个相当大的成就。只是最近，在过去的几个月里，我们才看到有文章对这个模型进行了深入的分析、批评和挑战。Luis Claudio Silveira Duarte\[3\]在Gamasutra上讨论了这个模式，Lana Polansky\[4\]的一篇文章后，Frank Lantz\[5\]也发表了一篇文章，都对这个话题进行了很好的评论。所有这些声音反过来帮助我集中了自己对MDA的思考，并使我能够更好地理解游戏叙事的子结构。

我对Hunicke、LeBlanc和Zubek的开创性工作只有最大的尊重。但是，就像今天的奔驰车与第一辆奔驰汽车几乎没有相似之处一样，我们必须要进步。MDA模式存在一些问题--Polansky和Lantz的文章表明，我不是唯一一个想在这个框架上工作的人，这样我们就可以再次与它一起工作。我们需要这样一个模型，这些文章并没有诋毁MDA，也没有论证设计框架是没有价值的。它们显示了MDA的弱点，以及我们如何通过修正和加强这个模型来克服这些弱点。

不幸的是，MDA可能会在这个过程中失去它的缩写，因为一些最大的问题与MDA的基本类别是如何被塑造的有关。由于将要明确的原因，在我自己看来，MDA应该演变成DDE：设计/动力学/经验。

**90%的MDA "机制 "实际上不是机制...**

在MDA中，**机制**在数据表示和算法层面上描述了游戏的特定组成部分。这种方法的一个明显问题是，这就像把一辆组装好的汽车描述为 "马达、变速箱和车轮"，而一辆汽车显然要多得多。在提到 "数据表示 "的时候，它只是在很小的程度上是 "机制的"。在更大的程度上，它是 "美学的"，因为所代表的数据往往由图形或声音资产组成。

更糟糕的是，MDA术语现在开始与自己冲突了。难道 "美学 "不是指玩家的情感反应，这与数据表现完全不同吗？正如Frank Lantz在他的文章中所解释的，MDA模型中的 "机制 "基本上是指在不受玩家直接影响的情况下由设计师直接设计的一切。_"但更有问题的是 "力学 "这个术语。同样，MDA想广义地使用这个词来指代设计者可以控制的所有东西--不仅仅是游戏规则，还有材料，配方_和配料。"**[6]**_我同意Lantz的解释。

为了说明 "机制 "一词并不适合作为一种描述，这里列出了一份不完整的设计者完全控制的东西，因此属于MDA中的 "机制 "类别。

- 游戏代码。游戏架构、I/O、游戏对象、游戏规则（代码级）、界面（代码级）、交互设计（代码级） ...
- 游戏规则（文件）。结构，平衡，时间，空间，剧情分支， ...
- 世界描述（文档）。世界和游戏规则，植物群和动物群，社会，人物，宗教，法律，物理 ...
- 风格（文件）。图形，声音，叙事，...
- 功能界面（数据表示）：视听的、非视听的、空间的、元的
- 内容界面（数据表现）。交互设计（界面层面），图形和声音，叙事，...[7]。

正如你所看到的，对于清单上的一些项目，在 "机制 "标签下进行总结是有问题的。有些项目根本不是机制的，比如图形风格，这显然是美学的一个方面，但在成为最终游戏体验的一部分之前，也是由设计师直接控制的。如果我们进一步论证，图形风格指南在数据表示或算法层面上没有体现，那么MDA模型就没有为这个关键的设计决策留下任何位置--证明MDA作为一个框架是不完整的。

**......但所有这些都是由设计师直接设计的！**。

当我开始尝试重新构建MDA模型时，我采用了两个视角。首先，我想关注游戏的生产过程，特别是其迭代的性质。我的模型版本需要考虑到这一点。第二个视角来自一个看似不同的角度，但实际上是密切相关的。为什么游戏故事常常很糟糕？我想更好地理解叙事作为MDA模型中的一个实体--但它并不是我认为（现在仍然认为）它应该存在的地方。

我的职业是制作人和叙事设计师，所以这两个镜头对我来说都很自然。如上所述，我正在写一本关于叙事设计的书，而这两个镜头也构成了这本书的基础。但是，为了在这个基础上真正地建立游戏，我需要一个功能性的设计框架，在这个框架中，叙事设计可以发挥其潜力和义务。因此，我的目标是重新建立MDA框架，以便它能更好地支持两个视角的旅程概念：游戏的实际制作和玩家的最终感知旅程。然而，无论我在哪里寻找，这些旅程在MDA模型中都找不到。

在思考重新构建的 "机制 "类别时，我想出了三个子类别，使我能够做出明确的区分，而不会让模糊的概念潜伏在中间。

    

图2：DDE模型的 "设计 "部分

上图显示了我对Zunicke和他的同事所称的 "机制"，以及我更愿意称之为 "设计 "的看法。该图中的所有东西都是由设计者直接设计的，他们对这个阶段的过程有充分的控制。("设计 "一词也是由Jesper Juul在Frank Lantz的文章之后的在线讨论中提出的，但我不知道Jesper是否会同意我的子结构)。

**"设计 "仍然有三个重要的子类别，其中一个是 "机制 "**。

设计下的子类别有

**蓝图（BLUEPRINT）：**蓝图体现在设计中涉及游戏世界的那一部分_概念：_它的文化、宗教、物理和其他规则集；游戏机制的自由形式符号；以及艺术设计、叙事设计、角色设计和声音设计的发达风格。这就是人们对 "设计 "的普遍理解：提出想法、绘画、写作、发明一个世界和它的功能，将其全部记录在Wiki中，并将其投入必要的迭代过程，以成为游戏本身的坚实基础。(有一段时间我用 "设定 "这个词来形容这个子结构，但现在蓝图对我来说似乎更清晰了，因为它反映了整个开发阶段的规划和文件的主导地位。）

**机制：**机制仍然在框架中，但现在更加具体。它们包括所有最终将在抽象中创建物理游戏的东西，也就是说：在代码中。机制是关于代码结构、输入/输出处理、对象处理、游戏规则和对象交互的实现，以及其他与代码有关的东西。它是玩家在游戏中不直接看到或听到的东西。代码仍然是不可见的，不发出任何声音，只能通过界面来体验。

**界面：**界面包含设计和制作一切最终将创建物理游戏的具体内容，也就是说：一切用于向玩家传达游戏世界的内容--它的外观、声音、反应和与玩家的互动以及游戏的反馈回路。界面也包含了每个游戏都需要的报告系统，不管是diegetic还是non-diegetic，空间还是meta.[8\]因此每个图形资产、声音资产、场景或文本都是界面的一部分，只要它也是游戏数据的一部分。它是玩家听到和看到的一切，是不属于游戏的可执行或配置代码级别的每一块数据。

**MDA框架的重大成就之一。认识到动态的功能！**。

在 "设计 "类别的基础上，"动态 "类别的问题要少得多，尽管在实践中我们仍在等待一些工具，以帮助我们对创作过程的这一部分获得更多的控制，从而节省昂贵的设计迭代。正如Frank Lantz所正确指出的。_"对我来说，MDA的最大优势在于它强调了游戏设计的 "二阶 "性质。机制指的是设计者可以直接控制的游戏部分，美学指的是游戏最终产生的玩家体验的质量，而在这两者之间，连接着的是游戏的动力学--在游戏进行时，游戏的不同部分与玩家之间相互作用的行为"。**\[9\]**_

在DDE版本的框架中，我对动态进行了一些推断，以便增加一些细节，特别是关于设计师和玩家的不同视角。

    

图3：DDE模型的 "动态 "部分

回到上面的梅赛德斯的比喻，如果 "设计 "包含了对组装好的汽车的所有部件的规划，以及组装好的部件本身，那么 "动力学 "定义了当你启动引擎，所有组装好的部件一起工作时会发生什么：马达的活塞、曲轴和阀门、齿轮箱、悬挂、座椅的弹簧、街道、天气、驾驶风格、方向盘的颤动、噪音，甚至是汽车音响中的歌曲。

请注意，设计框架的这一部分仍然是由设计师完全控制的--至少在理论上，假设有一个迭代的设计过程。在实践中，总是有太多不同的玩家来预测每个玩家可能从事的每一种行为。因此，设计者的控制是间接的，因为在整个迭代创造过程中，设计者所能改变的一切都属于 "设计 "的范畴--其中 "动态 "总是增加了一层出现和不可预测性。

虽然_玩家面对的是游戏的动态，但这种对抗也是间接的。正如米格尔-西卡特（Miguel Sicart）所表明的，互动的间接性是通过玩家主体的创造而发生的。[10/] 因为这个术语在后面会变得很重要，我们将在这里详细介绍它。

玩家-主体是基于这样一个理论：玩游戏的不是真正的我们，而是我们自己的子集。我们可以把玩家-主体想象成类似于精神化身，一个只存在于头脑中的角色，能够做出我们在现实生活中永远无法做出的决定。这是一个具有与我们不同的能力的角色--以及不同的道德观。在很多方面，我们在游戏中把玩家主体放到精神上的危险境地，以体验这种危险，而不使我们的真实自我受到伤害。因此，我们可以从一个安全的地方体验和探索道德和精神上的挑战。我们可以获得所有的好处和奖励，而不必冒着这种现实生活中的情况可能造成的创伤的风险。

在动态的背景下，以及在更大的框架内，设计师和设计因此不是直接与玩家打交道，而是与玩家-主体打交道。它是玩家的那个实例或方面，在游戏中做出决定。

**"美学 "一词忽略了游戏设计的真正内涵：体验设计**。

"动力学 "是汽车的所有部件的统一行动，加上任何外部的影响，但它不是驾驶的体验 在最初的MDA框架中，这将被称为 "美学"，但有很多理由说明 "美学 "是一个比 "力学 "更糟糕的术语--以及为什么我认为 "体验 "会更好。

我已经指出，MDA框架中归入 "力学 "的很多东西都来自于对深度美学设计问题的工作。因此，把一个完全不同的类别称为 "美学 "本身就有问题。但问题更深。

"美学 "是哲学中的一个术语，至少有两种用法。

1.  它用在现象学中，试图回答我们如何感知事物的问题。例如，康德声称，我们不能感知任何独立于时间和空间的东西，因为这是两个先验的直觉，我们不能不拥有。
2.  2.美学理论试图回答我们为什么会认为某物是美或丑，是艺术或非艺术的问题。是什么在我们的眼中和心中创造了美或艺术？

但 "美学 "也是一个心理学术语，与不同的人如何以完全不同的方式感知同样的颜色、声音、旋律、图片或文字有关，并试图理解这些差异背后的原因和影响。在我们的头脑中，是什么决定了我们感知的波动性？如果这还不够令人困惑，"美学 "也是 "美丽 "或 "形状良好 "的日常同义词。

你可以看到 "美学 "作为一个术语是多么容易与MDA设计过程中的美学方面混在一起。更糟糕的是，这个词甚至在哲学家中也是有争议的，它在艺术家中的使用被巴奈特-纽曼（Barnett Newman）著名地谴责过--并非完全没有理由--他打趣说 他说："美学对于艺术家来说，就像鸟类学对于鸟类一样"。

    

图4：DDE模型的 "体验 "部分

任何实用的游戏设计框架的核心目标都应该是帮助游戏设计师理解如何处理他们的日常工作。它应该帮助框定开发过程，同时也准确地表现出基本的艺术形式。一个满载哲学术语的框架，只对评估艺术_之后的创作有用，从定义上讲是没有实际用途的。如果DDE模型可以帮助批评家（我相信它可以），那是一种奖励，但首先DDE是为艺术家服务的。

当然，在理论上，我们从美学的各个领域所知道的东西可以帮助我们做出设计决定。在实践中，一个游戏往往被证明是太复杂了，无法事先计划详细的美学效果。但是，即使美学知识可以帮助我们做出设计决策，也很难足以用这个模糊的词来命名设计框架的整个子结构，特别是当设计者不能完全控制其效果时。更糟的是：称其为 "美学 "忽略了所有真正属于该设计类别的核心的东西，那就是 "体验"。

让我们回顾一下MDA论文中给出的定义。_"**美学**描述了当玩家与游戏系统互动时，在她身上唤起的理想的情感反应。"_对这个定义的任何解读都涉及到时间和空间，在大多数情况下是在数小时的游戏中。但是对于参与者来说，在时间和空间上发生的事情必然是一种旅程，一种体验。游戏设计是（或应该是）体验设计--事实上，这一点在MDA文件中也提到了。此外，对玩家的思考鼓励体验驱动的（而不是功能驱动的）设计。

**只要有动态，这些动态就可以被体验**。

这就是为什么我和Jesper Juul一致，建议将MDA中的 "美学 "类别改为 "体验"。体验从玩家玩游戏时就开始了。它在时间上并不与动态分离，因为动态也需要时间和空间作为_先验的直觉。当有游戏动态时，玩家-主体可以体验这些动态。如果动力学足够复杂，能够为玩家主体创造一个对立面，游戏就会成为一个有价值的对手。因此，随着时间的推移，玩游戏将创造一个在许多不同层面上发挥作用的旅程。

**感官：**感官旅程包括玩家从开始到结束的所有感官体验。它是玩家通过可用的输出设备所看到、听到和感觉到的全部内容。

**小脑：**情感之旅包括玩家在玩游戏时的所有情感体验。它是玩家经历的情感旅程，恐惧和恐怖，悲伤，内疚和愤怒，以及游戏唤起的任何其他情感。

**智力旅程：**智力旅程包括玩家经历的所有挑战和决定，并以有意识的方式进行思考。

这三个旅程将共同形成玩家对游戏的_感知。这种感知有许多名称和子概念，无论游戏体验在感知宇宙的各个部分有什么价值，都是个人品味和偏见的问题。

如果我们看一下玩家的角色，我们就会发现，感知是直接对抗的层面。这是所有感官、情感和智力直接面对的地方--或者说，如果玩家没有创造出玩家-主体的保护层，就会直接面对。

从设计师的角度来看，这也是我们将失去对作品完全控制的层面（即使是间接的），因为这就是玩家的个人感知所占据的地方。在玩家体验游戏的过程中，玩家不再受到代码的限制。玩家可以感知、感受和思考任何他们想要的体验。他们可以喜欢或讨厌它，享受它或觉得它无聊，得到他们想要的或不期望的东西，受到挑战或被带到情感的边缘。

设计师越是了解目标受众，游戏越是针对该受众，游戏就会得到更好的接受。这就是为什么客观的标准只能让设计走得更远--以及为什么了解你的观众的期望对所有的成功措施都至关重要。

    

图5：整个DDE模型

有了DDE的子类别，是时候定义不同部分之间的关系了。

从最初的MDA框架来看。_"MDA框架的每一个组成部分都可以被认为是游戏的一个'镜头'或'视图'--独立的，但有因果关系。\[LeBlanc, 2004b\]。从设计者的角度来看，机制产生了动态的系统行为，这反过来又导致了特殊的审美体验。从玩家的角度来看，美学设定了基调，而这一基调在可观察的动态中诞生，最终，可操作的机制。

除了使用的术语外，这个排序显然是正确的，如果我们简单地用新的术语替换旧的术语，DDE系统也支持这个解释。但是在整个前提下存在着误解的危险，因为那个排序并不描述一个时间线。相反，该设计序列中的一切都可以在同一时刻发生。

对于设计师来说，这就是对一个迭代过程的描述，每一个关卡的每一个决定都可以改变整个游戏。对于玩家来说，这就是他们在玩游戏时所做的和所经历的。玩家从头到尾同时感知世界_和分析基础机制，面对和体验设计的每一个方面。(实际上设计师也是第一个玩家--或者至少应该是。)这就是为什么我们需要增加一个术语，以加强一个特定的观点：游戏是对时间和空间的对抗；一组挑战，可以创造广泛的感知旅程，这取决于设计师所创造的东西和玩家如何理解它。

**好的游戏必须是玩家-主体的好对手**。

由于我们将最后一个类别重新命名为 "体验"，在这个时刻，更多地从玩家的角度而不是从设计师的角度来描述整个框架是有意义的。归根结底，设计师必须理解玩家的观点，才能做出一个伟大的游戏，而且冒着重复自己的风险，游戏设计就是体验设计！这就是体验设计的概念。

这就是 "反面人物 "的概念发挥作用的地方。敌手在讲故事和其他叙事艺术形式中是众所周知的。基本上每一种艺术形式都以不同的形式存在对立面，无论是音乐中的对位还是绘画中的补色。原因是显而易见的：正是通过冲突，或对比，或紧张，几乎所有的艺术都能在不同的认识水平上产生兴趣。

如果一个设计师把游戏系统的动态看作是玩家主体的对立面，那么这个视角就能让设计师把玩游戏的整个体验理解为一种叙事。是的，我们对叙事有一定的期望，好的设计师在创造一个伟大的叙事体验时，会预见到这些期望。如果一个叙事的反面人物没有完成这个角色，那么这个叙事就会很无聊，或者至少没有原来那么有趣，甚至可能会崩塌。

在谈论叙事时，我们不仅仅是指设计者为游戏创造的任何嵌入式故事。[12]当然，任何嵌入式叙事（包括决定是否应该包括一个）都应该支持和加强完整的体验。如果感知之旅和嵌入式叙事不匹配，我们就会得到克林特-霍金所说的 "鲁道-叙事脱节"。

在玩的时候，每个游戏都会创造一个总体性的元故事，一个突发性的故事。但为了成功地做到这一点，游戏必须成为玩家主体的有价值的对立面。就像每个故事的对立面负责英雄必须克服的一系列挑战一样，游戏系统这个对立面也负责玩家在游戏中会遇到和克服（或不克服）的障碍。

即使你喜欢不同的术语，我想我们都可以同意，一个定义明确的设计框架应该显示这种联系。如果游戏对玩家来说不是合适的挑战--如果它不是一个有价值的对立面--玩家就会停止游戏，或者继续游戏但却不满意甚至厌烦。DDE框架支持从抽象到字面的冲突概念；而MDA则完全没有提到它。

**设计、动力和经验不是生产阶段**。

回到设计师（或制作人）的角度，同样，DDE框架的三个子结构不应该被解释为生产阶段。相反，它们是人们为了建立一个有效的迭代过程来创造游戏而必须了解的。如上所述，任何游戏的第一批玩家通常是开发者自己。他们通过一个又一个的改变来迭代设计，直到动态开始产生预期的效果。他们是第一个感知游戏的人，并了解它将为观众带来的旅程。在每一次迭代中，每一行代码和每一项资产，无论是图形、声音还是叙述，都可以被调整，以改变游戏作为一种体验的效果。

今天，迭代生产周期应该是一个既定的事实，但根据我的经验，当时间和金钱耗尽时，它们是最先被淘汰的。不幸的是，没有它们，你就无法开发出一个好游戏。一块一千多块的拼图被扔在空中，永远不会自己拼起来。而游戏通常要比一千块拼图多得多。

DDE模型允许设计师在游戏开发的整体框架内评估和重新评估故事的价值。再看一下蓝图子结构中的条目，你会发现几乎所有的条目都有叙事的内涵。而作为这种情况的第一个结果，早就应该从第一天起就将叙事设计视为任何设计过程中的一个组成部分。(对叙述性设计的持续忽视是商业惯例和权力动态的产物，与MDA或学术批评无关）。

DDE框架显然还没有完成。到目前为止，它达到了创建它的目的，即为我想在书中谈论的东西奠定了一个稳定的基础。随着时间的推移和我对它更深入的思考，这个框架将不可避免地发生更多的变化，一些术语可能会改变，一些定义会得到更多的关注，而且还有一些领域我还没有完全探索。

尽管如此，它已经变得足够稳定，我现在正在寻找来自任何方面的反馈，因为我知道我无法独自完成它。涉及的领域太多，而我根本不具备这方面的专业知识。所以现在是其他声音和其他镜头发挥作用的时候了。现在是我们尝试把这个和其他所有的框架撕成碎片的时候了，看看是否有什么价值。

让我们不要再等11年了。

(由于我不是母语者，这篇博文由马克-巴雷特（Mark L. Barrett）编辑，以保证英语的正确性，他是我多年的朋友和兄弟。我欠你的，马克! 请访问马克的博客 "The Ditchwalk"，在那里你可以找到很多关于互动故事的有见地的文章：http://www.ditchwalk.com/category/interactive/ )