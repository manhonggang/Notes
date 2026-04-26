中文翻译自：[[Battle Circle AI Let Your Player Feel Like They're Fighting Lots of Enemies]]

难度：中级 | 篇幅：短 | 语言：

近身格斗是电子游戏世界中最受欢迎的消遣之一，它是无数知名和冷门系列游戏的核心，做得好的话，是一种紧张而扣人心弦的体验。许多游戏开发者都曾面对过两个人互殴直到一方再也无法还手的游戏，并心想："如果有一大堆坏蛋的话，这该多好啊！"有时候这确实没错，但往往整体大于部分之和，同时与大量"坏蛋"战斗并不像一次只打一个那样激动人心、有深度或有细微差别。

许多近身格斗游戏在面对多个对手时并不使用任何特别的人工智能。这通常意味着，同时与两个对手战斗的难度呈指数级增长，比打一个对手要难得多，因为他们会同时发起攻击，而你基本上只能反击其中一个。在最糟糕的情况下，当面对成群结队的敌人时，这意味着最优策略是把敌人引成一条直线，然后一边后退一边逐个击破！这感觉一点都不精彩也不刺激，对吧？

<iframe width="600" height="338" data-src="//www.youtube.com/embed/ukXrOSFH-_Y" frameborder="0" allowfullscreen="" src="//www.youtube.com/embed/ukXrOSFH-_Y"></iframe>

跳到 0:53。

接下来是"战斗圈"（battle circle）。这是一段AI代码，它告诉敌人有意识地将自己围绕在玩家周围，并且只在玩家有机会做出反应的时候才发起攻击。这迫使敌人以一种对玩家来说有趣得多的风格和节奏来战斗……尽管这实际上是一种相当糟糕的战斗策略！

你想要使用战斗圈的主要原因，是让玩家**感觉**自己正在同时与许多敌人战斗，而实际上并不需要面对**真正的**、同时与许多敌人战斗的挑战。因此，在最核心的层面上，战斗圈是一种**幻觉**。你是在刻意让事情对玩家来说变得更容易，这样他们就能体验到那种单挑一大群家伙并且知道自己能活着出来的**幻想**，就像在任何一部武侠电影中那样。

<iframe data-src="//www.youtube.com/embed/PDQPIJSO0XA" height="338" width="600" allowfullscreen="" frameborder="0" src="//www.youtube.com/embed/PDQPIJSO0XA"></iframe>

跳到 1:13。

战斗圈并不需要为每一款游戏以相同的方式运作；如果你选择使用它，你必须花时间根据你的游戏来**定制**它。在光谱的一端，你有"电影式"战斗圈，比如在《刺客信条》或《蝙蝠侠：阿卡姆疯人院》中，敌人耐心地等待轮到他们才尝试攻击，并给玩家足够的预警来应对即将到来的攻击。在另一端，你有"危险式"战斗圈，比如在《黑暗之魂》中，敌人会尽量不挡彼此的路，但除此之外，他们毫不介意一拥而上将你团团围住。

我使用"电影式"（cinematic）和"危险式"（dangerous）这两个词来描述玩家身处战斗圈内时预期会获得的体验类型：它是一种更偏向激动人心的视听体验，让玩家在其中感到**自在舒适**，还是说它是一种玩家应该尽量避免的**脆弱**处境？

<iframe data-src="//www.youtube.com/embed/hnj4RHFG038" height="338" width="600" allowfullscreen="" frameborder="0" src="//www.youtube.com/embed/hnj4RHFG038"></iframe>

这个概念可以进一步简化为管理施加在玩家身上的**压力**（pressure）。具体来说，这是玩家对战斗圈中的敌人做出反应的内在驱动力的大小。一个低压力的战斗圈会让玩家等待即将到来的攻击进行反击，或者在攻击某个特定敌人时不会立即遭到报复。一个高压力的战斗圈会迫使玩家一旦进入圈内就必须选择"战斗还是逃跑"，因此一开始进入战斗圈就应该是一个经过深思熟虑的战术决定。在这样一个危险的圈内，玩家必须立即决定攻击谁、反击谁，以及何时以何种方式逃脱。

我已在[示例Unity文件](https://github.com/tutsplus/battle-circle-ai)中提供了一个功能齐全（尽管简约）的竞技场式清版动作游戏。如果你不使用Unity，你仍然应该对如何将战斗圈代码适配到你正在使用的任何语言和引擎有一个大致的了解。你需要关注的文件是 [EnemyMob.cs](https://github.com/tutsplus/battle-circle-ai/blob/master/src/Assets/Scripts/AI/EnemyMob.cs?source=cc) 和 [SwordzPlayer.cs](https://github.com/tutsplus/battle-circle-ai/blob/master/src/Assets/Scripts/SwordzPlayer.cs?source=cc)。

下面是战斗圈的实际运行效果。点击演示以获得焦点，然后使用方向键移动，按 **X** 键进行攻击。

它是如何运作的
------------

战斗圈AI的基本运作方式如下（从敌人的角度）：

首先，朝玩家走去，直到我进入一个"危险"（danger）半径范围。

![gamedevtuts_battlecircle_600_01](https://cdn.tutsplus.com/gamedev/uploads/2014/02/gamedevtuts_battlecircle_600_01.png)

在"危险"模式下，不要离另一个敌人太近，除非我被允许攻击玩家。（参见 [Avoider.cs](https://github.com/tutsplus/battle-circle-ai/blob/master/src/Assets/Scripts/AI/Avoider.cs?source=cc)。）

![gamedevtuts_battlecircle_600_02](https://cdn.tutsplus.com/gamedev/uploads/2014/02/gamedevtuts_battlecircle_600_02.png)

同样在"危险"模式下，尝试接近玩家。如果路上有太多敌人挡道，那么在那些敌人移动或玩家移动之前，我实际上无法接触到玩家。

当玩家进入我的"攻击"（attack）半径（大约是我攻击的最大射程）时，向玩家询问我是否被允许攻击。如果允许，将我添加到玩家对象上的当前攻击者列表中。（参见 [SwordzPlayer.cs](https://github.com/tutsplus/battle-circle-ai/blob/master/src/Assets/Scripts/SwordzPlayer.cs?source=cc)。）

![gamedevtuts_battlecircle_600_03](https://cdn.tutsplus.com/gamedev/uploads/2014/02/gamedevtuts_battlecircle_600_03.png)

*   如果列表上已经达到了最大允许的攻击者数量，我将被拒绝许可。
*   如果我被拒绝许可，尝试朝随机方向横向移动一两秒，直到我被授予许可。
*   如果玩家移出攻击范围——即使我正在攻击——将我从攻击者列表中移除。
*   如果我死亡、被击晕或因为其他原因无法攻击，将我从攻击者列表中移除。

**最大允许同时攻击者数量**（`simultaneousAttackers`，在 [SwordzPlayer.cs](https://github.com/tutsplus/battle-circle-ai/blob/master/src/Assets/Scripts/SwordzPlayer.cs?source=cc) 中）对于平衡你的战斗圈至关重要。数值越高，**压力**会呈指数级增加。在示例演示中，我将其设置为 `2`；不那么紧张的、更"电影化"的游戏将其设置为 `1`。如果你将这个数值设得太高，你就破坏了战斗圈的目的，因为大群敌人会变得无法攻克，或者只能用无趣的戳了就跑的战术来击败。

同样重要的是**敌人攻击频率**（`attackRate`，在 [EnemyMob.cs](https://github.com/tutsplus/battle-circle-ai/blob/master/src/Assets/Scripts/AI/EnemyMob.cs?source=cc) 中）。这不是敌人最快的可能攻击频率，而是他们在获得许可时**会选择**攻击的频率。正如你所预料的，较低的数值会**增加压力**，但你通常应该让这个频率比真实的攻击频率高出几倍。你可以通过增加 `attackRateFluctuation` 来让这个频率变得稍微不可预测一些（从而让**压力**的程度也稍微不那么可预测），这将在每次攻击后增加或减少攻击频率。

使用这个系统，你就有了创造那种**力量幻觉**的基本手段，让你的玩家在与大量敌人战斗时感到更加有趣。

结论
----

你可以为战斗圈内的战斗做大量微小的改动和补充，使其变得更加有趣：

*   一个"击晕"或"反击"攻击，玩家可以用来让敌人暂时脱离战斗，这样玩家就可以攻击战斗圈中的其他敌人
*   一个"闪避"动作，让玩家能够快速进入、退出或在战斗圈内移动
*   "推"和"拉"的动作，让玩家能够将敌人移入和移出战斗圈
*   远程敌人，会通过战斗圈的空隙狙击玩家，迫使玩家强行穿过战斗圈优先攻击这些敌人
*   特殊的"队长"敌人，会增加附近敌人的攻击频率，或者无视攻击许可，从而增加战斗圈中某些部分的**压力**

所以，让创意之泉尽情流淌吧！这仅仅是个开始：让战斗圈成为你游戏玩法的核心部分，打造属于你自己的、与**你的**游戏完美契合的战斗圈版本。
