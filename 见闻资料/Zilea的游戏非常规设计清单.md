I've been asked a few times, "Why don't you do stuff like Rupture (from DOTA Bloodseeker) in LoL?"

I usually respond -- Rupture contains several basic design 'anti-patterns'. I thought I'd post for the benefit of those who are interested what strong anti-patterns I am aware of.

So... Here are a few that come to mind.... Note that you can find an example of each of these somewhere in our game at some intensity level. Sometimes this is just bad design. Sometimes this is because we got something else in exchange. Design is an optimization -- but these anti-patterns are of negative design value, so you should only do them if you get something good in return.

To be clear, LoL has a number of abilities that use these anti-patterns. Sometimes it's because we got something good in return. Sometimes it's because we made design errors. However, we generally avoid them nonetheless, and certainly use them a lot less than other games in our genre.

Power Without Gameplay

This is when we give a big benefit in a way that players don't find satisfying or don't notice. The classic example of this is team benefit Auras. In general, other players don't value the aura you give them very much, and you don't value it much either -- even though auras can win games. As a REALLY general example, I would say that players value a +50 armor aura only about twice as much as a +10 armor aura... Even though +50 is 5x better. Another example would be comparing a +10 damage aura to a skill that every 10 seconds gives flaming weapons that make +30 damage to all teammates next attack (with fire and explosions!). I am pretty sure that most players are WAY more excited about the fiery weapons buff, even though the strength is lower overall.

The problem with using a "power without gameplay" mechanic is that you tend to have to 'over-buff' the mechanic and create a game balance problem before people appreciate it. As a result, we tend to keep Auras weak, and/or avoid them altogether, and/or pair them on an active/passive where the active is very strong and satisfying, so that the passive is more strategic around character choice. For example, Sona's auras are all quite weak -- because at weak values they ARE appreciated properly.

Burden of Knowledge

This is a VERY common pattern amongst hardcore novice game designers. This pattern is when you do a complex mechanic that creates gameplay -- ONLY IF the victim understands what is going on. Rupture is a great example -- with Rupture in DOTA, you receive a DOT that triggers if you, the victim, choose to move. However, you have no way of knowing this is happening unless someone tells you or unless you read up on it online... So the initial response is extreme frustration. We believe that giving the victim counter gameplay is VERY fun -- but that we should not place a 'burden of knowledge' on them figuring out what that gameplay might be. That's why we like Dark Binding and Black Shield (both of which have bait and/or 'dodge' counter gameplay that is VERY obvious), but not Rupture, which is not obvious.

In a sense, ALL abilities have some burden of knowledge, but some have _a lot more_ -- the ones that force the opponent to know about a specific interaction to 'enjoy' the gameplay have it worst.

Good particle work and sound -- good 'salesmanship' -- will reduce burden of knowledge (but not eliminate it). We still would not do Rupture as is in LoL ever, but I would say that the HON version of Rupture, with it's really distinct sound effect when you move, greatly reduces the burden of knowledge on it.

In summary, all mechanics have some burden of knowledge, and as game designers, we seek to design skills in a way that gives us a lot of gameplay, for not too much burden of knowledge. If we get a lot more gameplay from something, we are willing to take on more burden of knowledge -- but for a given mechanic, we want to have as little burden of knowledge as possible.

Unclear Optimization

This is a more subtle one. when players KNOW they've used a spell optimally, they feel really good. An example is disintegrate on Annie. When you kill a target and get the mana back, you know that you used it optimally, and this makes the game more fun. On the other hand, some mechanics are so convoluted, or have so many contrary effects, that it is not possible to 'off the cuff' analyze if you played optimally, so you tend not to be satisfied. A good example of this is Proudmoore's ult in DOTA where he drops a ship. The ship hits the target a bit in the future, dealing a bunch of damage and some stun to enemies. Allies on the other hand get damage resistance and bonus move speed, but damage mitigated comes up later. Very complicated! And almost impossible to know if you have used it optimally -- do you really want your squishies getting into the AOE? Maybe! Maybe not... It's really hard to know that you've used this skill optimally and feel that you made a 'clutch' play, because it's so hard to tell, and there are so many considerations you have to make. On the other hand, with Ashe's skill shot, if you hit the guy who was weak and running, you know you did it right... You also know you did it right if you slowed their entire team... Ditto on Ezreal's skill shot.

Use Pattern Mis-matches Surrounding Gameplay

I won't go into too much detail on this, but the simple example is giving a melee DPS ability to a ranged DPS character -- the use pattern on that is to force move to melee, then use. This does not feel good, and should be avoided. I'm sure you are all thinking -- but WoW mages are ranged, and they have all these melee abilities! Well... Frost Nova is an escape, and the various AEs are fit around a _comprehensive_ different mage playstyle that no longer is truly 'ranged' and is mechanically supported across the board by Blizzard -- so the rules don't apply there ;p

Fun Fails to Exceed Anti-Fun

Anti-fun is the negative experience your opponents feel when you do something that prevents them from 'playing their game' or doing activities they consider fun. While everything useful you can do as a player is likely to cause SOME anti-fun in your opponents, it only becomes a design issue when the 'anti-fun' created on your use of a mechanic is greater than your fun in using the mechanic. Dark Binding is VERY favorable on this measurement, because opponents get clutch dodges just like you get clutch hits, so it might actually create fun on both sides, instead of fun on one and weak anti-fun on another. On the other hand, a strong mana burn is NOT desirable -- if you drain someone to 0 you feel kinda good, and they feel TERRIBLE -- so the anti-fun is exceeded by the fun. This is important because the goal of the game is for players to have fun, so designers should seek abilities that result in a net increase of fun in the game. Basic design theory, yes?

Conflicted Purpose

This one is not a super strong anti-pattern, but sometimes it's there. A good example of this would be a 500 damage nuke that slows enemy attack speed by 50% for 10 seconds (as opposed to say, 20%), on a 20 second cooldown. At 50%, this is a strong combat initiation disable... but at 500 damage it's a great finisher on someone who is running... but you also want to use it early to get the disable -- even though you won't have it avail by the end of combat usually to finish. This makes players queasy about using the ability much like in the optimization case, but it's a slightly different problem. If the ability exists for too many different purposes on an explicit basis, it becomes confusing. this is different from something like blink which can be used for many purposes, but has a clear basic purpose -- in that place, players tend to just feel creative instead.

Anti-Combo

This one is bad. This is essentially when one ability you have diminishes the effectiveness of another in a frustrating manner. Some examples:

Giving a character a 'break-on-damage' CC with a DOT (yes, warlocks have this, but they tuned it to make it not anti-combo much at all)

With Warriors in WoW -- they need to get rage by taking damage so that they can use abilities and gain threat -- but parry and dodge, which are key to staying alive, make them lose out on critical early fight rage. So, by gearing as a better tank, you become a worse tank in another dimension -- anti combo!

With old warrior talent trees in WoW, revenge would give you a stun -- but stunned enemies cannot hit you and cause rage gain... So this talent actually reduced your tanking capability a lot in some sense! Anti-combo!

False Choice -- Deceptive Wrong Choice

This is when you present the player with one or more choices that appear to be valid, but one of the choices is just flat wrong. An example of this is an ability we had in early stages recently. It was a wall like Karthus' wall, but if you ran into it, it did damage to you, and then knocked you towards the caster. In almost every case, this is a false choice -- because you just shoudln't go there ever. If it was possible for the character to do a knockback to send you into the wall, it wouldn't be as bad. Anyhow, there's no reason to give players a choice that is just plain bad -- the Tomb of Horrors (original module) is defined by false choices -- like the room with three treasure chests, all of which have no treasure and lethal traps.

False Choice -- Ineffective Choice

Similar to above, except when you give what appears to be an interesting choice that is then completely unrewarding, or ineffective at the promised action. An older version of Swain's lazer bird had this failing... Because the slow was so large, you could never run away in time to de-leash and break the spell and reduce damage, and in cases you did, you'd just dodge 20% of the damage at a big cost of movement and DPS -- so running was just an ineffective choice.

Or We Could **** the Player!!1111oneoneone

This is where you straight up screw over the player, usually with dramatic flair, or maybe just try to make the player feel crappy in a way that isn't contributing to the fun of the game. These range in severity, but examples usually are spawned because the designer is a pretentious wanker who likes to show what a smart dude he is and how stupid the player is. I do not respect designers who engage in this pattern intentionally, and encourage any design lead out there to immediately fire any of your staff that does. I do understand that it can happen inadvertently, and that you might cause some of this stress on purpose in an RPG for character development.. And of course, I love you WoW team despite the 'playing vs' experience of Rogue and Warlock, as you DO have the best classes of any MMO, and they look even better in Cataclysm.... But, on Bayonetta, did the developers really think the stone award was a good idea? But I digress...

Very Severe: The original tomb of horrors D&D module is the worst in existence. Good examples are the orb of annihilation that doesnt look like one and instakills you and all your gear if you touch it, and the three treasure chests where each has no loot and deadly traps and no clues that this is the case.

Severe: There's a popular wc3 map in China where you enter a bonus round, and have a 2% chance of just straight up dying rather than getting cool loot.

Situationally Moderate:Horrify + fear kiting from a competent warlock who outgears you in WoW. Guess what? You die before getting to react, while watching it in slow motion!

Mild: Stone award in Bayonetta. So... you barely get through the level for the first time, then get laughed at by the game with a lame statue of the comic relief character, and a mocking laugh. Please -- maybe a bronze award and a 500 pt bonus might be more appropriate? The player might have worked VERY hard to get through the level, espec on normal and higher difficulties.

Non-Reliability

Skills are tools. Players count on them to do a job. When a skill is highly unreliable, we have to overpower it to make it 'satisfying enough'. Let me give you an example: Let's say Kayle's targeted invulnerability ult had a 95% chance of working, and a 5% chance of doing nothing when cast. We'd have to make it a LOT stronger to make it 'good enough' because you could not rely upon it... and it would be a lot less fun. Random abilities have this problem on reliability -- they tend to be a lot less satisfying, so you have to overpower them a lot more. Small amounts of randomness can add excitement and drama, but it has a lot of downsides. There are other examples of non-reliability, but randomness is the most obvious one. Abilities that require peculiar situations to do their jobs tend to run into the same problems, such as Tryndamere's shout that only slows when targets are facing away from him.

Zileas的游戏设计反模式列表

创建时间：2023年3月20日下午2:29

我被问了几次，“为什么你不做一些像（DOTA风行者的）破裂这样的东西在LOL中呢？”

我通常会回答——破裂包含了几个基本的反模式设计。我认为我应该为那些感兴趣的人发布一下我知道的一些强烈的反模式。

所以……以下是我想到的一些……请注意，在我们的游戏中，您可以在某个程度上找到每个反模式的例子。有时这只是不好的设计。有时是因为我们得到了其他的东西。设计是一种优化——但这些反模式是负面设计价值，因此您只应在得到好处时才使用它们。

明确一下，LOL有许多使用这些反模式的技能。有时是因为我们得到了好处。有时是因为我们犯了设计错误。然而，我们通常仍然避免使用它们，并且肯定比我们这个类型中其他游戏使用它们少得多。

没有游戏性的力量

这是当我们以玩家不满意或不注意的方式提供大量好处时的情况。这种情况的典型例子是团队效益光环。通常，其他玩家不太重视您给予他们的光环，而您也不太重视它——即使光环可以赢得游戏。作为一个非常普遍的例子，我会说，玩家只会将+50护甲光环视为+10护甲光环的两倍左右的价值……即使+50的效果更好5倍。另一个例子是比较+10伤害光环和每10秒给予团队中所有队友30点额外伤害的技能（带有火和爆炸！）。我敢肯定，大多数玩家对火热武器的加成更加兴奋，即使强度整体上较低。

使用“没有游戏性的力量”机制的问题在于，您倾向于在人们欣赏它之前必须“过度强化”机制并创建游戏平衡问题。因此，我们倾向于保持光环较弱，或完全避免它们，或将它们与非常强大且令人满意的主动/被动配对，以便被动围绕角色选择更具策略性。例如，Sona的光环都很弱——因为在弱值下它们被适当地重视。

知识负担

这是在初学者中非常普遍的模式。这种模式是，当您执行一个复杂的机制并创建游戏玩法时，仅当受害者理解正在发生的事情时才能进行。破裂是一个很好的例子——在DOTA中，破裂会使您获得一个DOT，如果您，受害者，选择移动，则会触发DOT。但是，您没有办法知道这正在发生，除非有人告诉您或除非您在网上阅读……因此，最初的反应是极度沮丧。我们认为给受害者反制玩法非常有趣——但我们不应该让他们承担“知识负担”来弄清楚那个玩法是什么。这就是为什么我们喜欢Dark Binding和Black Shield（两者都具有非常明显的诱饵和/或“闪避”反制玩法），但不喜欢Rupture，因为它不明显。

在某种意义上，所有技能都有一些知识负担，但有些技能有更多的——强迫对手了解特定交互才能“享受”玩法的那些技能最糟糕。

良好的粒子效果和声音——良好的“推销”——将减少知识负担（但不会消除它）。我们永远不会像LOL那样对待破裂，但我会说，HON版本的破裂，它的移动时有非常明显的音效，大大降低了它的知识负担。

总之，所有机制都有一些知识负担，作为游戏设计师，我们希望以尽可能少的知识负担的方式设计技能，给我们带来大量的游戏玩法。如果我们从某些事情中获得更多的玩法，我们愿意承担更多的知识负担——但对于某个机制，我们希望尽可能少地承担知识负担。

不明确的优化

这是一个更微妙的问题。当玩家知道他们已经最优地使用了一个技能时，他们会感到非常好。一个例子是Annie的disintegrate。当您杀死一个目标并获得魔法值时，您知道您已经最优地使用了它，这使得游戏更有趣。另一方面，某些机制非常复杂，或具有许多相反作用，因此无法“即兴分析”您是否最优地运用了它们，因此您往往不会感到满意。这种情况的一个很好的例子是Proudmoore在DOTA中的大招，他会放下一艘船。船在未来的某个时候击中目标，对敌人造成大量伤害和眩晕。另一方面，盟友会获得伤害抵抗和额外的移动速度，但减轻的伤害会在稍后出现。非常复杂！几乎不可能知道您已经最优地使用了这个技能——您真的希望您的脆皮进入AOE中吗？也许！也许不是……很难知道您已经最优地使用了这个技能并感到自己做了“关键”的操作，因为它太难以判断，并且您必须考虑太多的问题。另一方面，如果您在Ashe的技能射击中击中了弱小而逃跑的人，您会知道自己做得很好……如果您减缓了他们整个团队的速度……Ezreal的技能射击上也是如此。

游戏玩法周围的使用模式不匹配

我不会详细介绍这个问题，但简单的例子是为远程DPS角色提供近战DPS技能——这种使用模式是强制性的。这不会感到好，应该避免。我敢肯定你们都在想——但是魔兽世界的法师是远程的，他们有所有这些近战技能！嗯……冰霜新星是逃脱，各种AE是围绕一个_全面_不同的法师玩法组合而设计的，这不再真正是“远程”，而且在机械上由暴雪全面支持——所以规则不适用那里；p

乐趣无法超越反乐趣

反乐趣是您的对手在您做出防止他们“玩他们的游戏”或进行他们认为有趣的活动时感到的负面体验。虽然您作为玩家可以做的所有有用的事情都可能会导致一些反乐趣，但只有当您使用某种机制时所创建的“反乐趣”大于您使用该机制时的乐趣时，它才成为设计问题。Dark Binding在这个评估上非常有利，因为对手可以像您一样获得关键的闪避，因此它可能实际上在双方都创造乐趣，而不是在一方创造乐趣，在另一方创造弱反乐趣。另一方面，强力的法力燃烧是不可取的——如果您将某人的法力耗尽到0，您会感觉很好，他们会感觉很糟糕——因此反乐趣超过了乐趣。这很重要，因为游戏的目标是让玩家有乐趣，因此设计师应该寻求能够在游戏中增加乐趣的能力。基本的设计理论，是吗？

目的冲突

这并不是一个非常强烈的反模式，但有时会出现。一个很好的例子是在20秒冷却时间内，对攻击速度造成50％的减缓（而不是20％）的500点伤害技能。在50％时，这是一种强有力的战斗启动禁用……但在500点伤害时，它是一个很好的追杀技能……但是您也想早早使用它来获得禁用——即使通常在战斗结束时它不再可用，以完成操作。这使得玩家对使用能力感到不适，就像在优化案例中一样，但它是一个稍微不同的问题。如果该能力存在于太多不同的目的上，就会变得混乱。这与可以用于许多目的的闪烁不同，但具有明确的基本目的——在该位置上，玩家往往只会感到有创意而已。

反连招

这个很糟糕。这实际上是指一个技能降低了另一个技能的效果，让人感到沮丧。以下是一些例子：

给角色一个“受伤打断”的控制技能，带有持续伤害效果（是的，术士有这个技能，但他们调整后使其不再反连招）

在《魔兽世界》中的狂战士需要承受伤害以获得怒气，以便使用技能和获得威胁，但招架和闪避是保持生命的关键，会使他们失去关键的早期战斗怒气。因此，通过更好的装备成为更好的坦克，你在另一个方面成为了一个更差的坦克 - 反连招！

在《魔兽世界》的旧战士天赋树中，复仇会给你一个眩晕 - 但眩晕的敌人无法攻击你并导致怒气增加...因此，这个天赋实际上在某种意义上大大降低了你的坦克能力！反连招！

虚假选择 - 欺骗性的错误选择

这是当你为玩家提供一个或多个选择时，其中一个选择是完全错误的，但看起来是有效的。最近我们在早期阶段就有一个类似的技能。它是一个像卡尔萨斯之墙一样的墙，但如果你撞上它，它会对你造成伤害，然后将你击向施法者。在几乎所有情况下，这是一个虚假选择 - 因为你永远不应该去那里。如果角色可以发动一个击退技能将你送进墙里，那就不会那么糟糕了。无论如何，没有理由给玩家一个明显糟糕的选择 - 像《恐怖之墓》（原始模块）中定义的虚假选择 - 就像有三个宝箱的房间，所有这些宝箱都没有藏宝和致命的陷阱。

虚假选择 - 无效的选择

与上面类似，但是当你提供看起来有趣的选择时，它却完全没有奖励或不能按照承诺的行动。斯旺的激光鸟的旧版本就有这个问题...因为减速效果很大，你永远无法及时逃跑，以解除控制，减少伤害，在某些情况下，你只能躲避20％的伤害，代价是移动和DPS的损失- 因此跑步只是一个无效的选择。

或者我们可以 对玩家进行攻击！！1111oneoneone

这是你直接欺负玩家的地方，通常是以戏剧性的方式，或者只是试图以某种方式让玩家感到糟糕，而这并没有为游戏的乐趣做出贡献。这些问题的严重程度不同，但通常的例子是因为设计师是一个自命不凡的傻瓜，喜欢展示自己有多聪明，以及玩家有多愚蠢。我不尊重有意采用这种模式的设计师，并鼓励所有设计领导立即解雇你的员工。我明白这可能是无意中发生的，并且您可能会在RPG中故意造成一些压力来进行角色发展。当然，我非常喜欢你们的《魔兽世界》团队，尽管在与盗贼和术士的体验方面存在问题，因为您有任何MMO中最好的职业，并且在灾变中它们看起来更好...但是，在贝约娜塔中，开发人员真的认为石头奖是个好主意吗？但我偏离了主题...

非常严重：原版的D＆D恐怖之墓模块是最糟糕的。好的例子是毁灭之球，看起来并不像是毁灭之球，如果你碰到它，它会立即杀死你和你所有的装备，以及每个宝箱都没有战利品和致命的陷阱以及没有线索表明这种情况。

严重：在中国有一个流行的WC3地图，在其中你进入一个奖励回合，有2％的机会直接死亡，而不是获得酷炫的战利品。

情况适度：在《魔兽世界》中，一个装备比你更好的能力强大的术士使用恐惧控制技能让你无法反应，你死亡了，同时以慢动作的方式看着！

温和：在贝约娜塔中的石头奖。所以...你勉强第一次完成了这个关卡，然后被游戏拿一个滑稽的漫画解释了一下，并嘲笑着。请-也许铜奖和500点的奖励可能更合适？玩家可能已经非常努力地通过了这一关，尤其是在普通和更高难度上。

不可靠性

技能是工具。玩家依靠它们来完成工作。当一个技能非常不可靠时，我们必须加强它，使它“足够令人满意”。让我举个例子：假设Kayle的有目标的无敌技能有95％的成功率，并且有5％的几率在施放时无效。我们必须使它更加强大，使其“足够好”，因为您不能依赖它...而且它会变得不那么有趣。随机能力在可靠性方面存在这个问题-它们往往不太令人满意，因此您必须更加强大。小量的随机性可以增加刺激和戏剧性，但它有很多缺点。其他不可靠性的例子，但随机性是最明显的一个。需要特殊情况才能完成其工作的能力也会遇到相同的问题，例如Tryndamere的嘶吼，只有当目标背对他时才会减速。