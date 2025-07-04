> 🔗 原文链接： [https://zhuanlan.zhihu.com/p/593347...](https://zhuanlan.zhihu.com/p/593347621?utm_id=0)

> ⏰ 剪存时间：2023-05-17 14:33:41 (UTC+8)

> ✂️ 本文档由 [飞书剪存](https://www.feishu.cn/hc/zh-CN/articles/606278856233?from=in_ccm_clip_doc) 一键生成

4 个月前 · 来自专栏 书籍翻译

> _想象一张台球桌上放满了半智能的电子驱动的台球，这些台球的内部程序设定为探索台球桌上的空间，基于它们与其他台球的特定交互来改变自身的行为模式。就绝大多数时间而言，这张桌子是一直处于运动状态里的，台球不断在碰撞，在每一秒不断转换着方向和速度。如此一个系统定义了最回归到元素形式的复杂行为：这个系统有着多个个体，它们遵循自身规则及其他更高层的指示，不断以多种方式动态地交互。但除非这些本体交互能产生某种可辨别的宏行为（Macro Behavior），否则它们还不能真正称之为涌现。假设台球所遵循的自身行为法则最终导致台球划分成奇数球和偶数球的两堆，这就有点涌现的味道了，由于单个个体同时进行复杂交互而最终导致更高层次的模式产生。这些台球并不是明确在程序上编好要各自区分成两堆的，而是编成它们要遵循各自更随机的规则的：例如当碰到纯色球则自动向左，碰到3号球则加速，碰到8号球则停在路线上……等等。完全基于这些底层的规则来产生了固有的形态。_ _——_ _**Steven Johnson**_ _，《Emergence》_

```Plaintext
本章关键字：系统  复杂度  涌现  自底向上  引擎  二阶设计
```

[Rules of Play（玩乐之道）目录 82 赞同 · 9 评论 文章](https://zhuanlan.zhihu.com/p/592860859)

![](https://whdolzxt1k.feishu.cn/space/api/box/stream/download/asynccode/?code=NTI3YjVmNDE3M2NlNTdkNzQ4ZDBkOWFiNWE0MDRlOThfY0J3U0dSN0QzQ054OFk2aXNnNkg0S1ZiZHdORDJhanNfVG9rZW46WDlWTWJrNHBXb1gxMzV4ajdWTWM0MDRQbmREXzE2ODQzNzYxODg6MTY4NDM3OTc4OF9WNA)

## **介绍：涌现系统**

欢迎来到第一个游戏设计图式：从涌现系统看游戏。接下来的章节会陆续定义游戏、设计和规则相关的多个核心概念。不过本章提出的会有点不一样。图式本身是侧重于游戏设计具体某方面的一个概念性框架。任何一个图式都是强调游戏的某些方面同时弱化其他方面的。虽然每个游戏设计图式都能应用在任何游戏上，但你会发现每个图式都更擅长于解决某些设计问题，而不擅于解决其他问题。游戏设计图式的目的在于促成有意义玩乐的设计。

从涌现系统看游戏的这个图式是直接从我们在第4章的讨论里建立起来的。从系统的角度来说，游戏是一组有着相互关系的部分所组成的整体。辨别和分析系统的每个部分，每部分的属性，以及它与其他部分的相互关系，这对理解该系统对整体游戏体验所带来的作用是很有帮助的。在这个图式里，我们会从复杂度和涌现去观察，进一步深化“从系统去看游戏”的这个视角。正如Steven Johnson在本章开头的引言里所说的，涌现是从复杂度里产生的。它是一个系统里出现的未经规划的模式。涌现是游戏里很重要的元素，它把游戏内在的系统特征与可能性空间和有意义玩乐联系在一起。

## **复杂度（Complexity）**

在理解系统和涌现之前，我们先看看复杂度的概念。复杂度的研究是从经典系统理论里发展起来的，它如今已经成为一个独立的跨学科领域了。在复杂度领域里的研究者研究了很多种不同的系统，包括纯信息的计算系统、像细胞和组织那样的生物系统，以及人类社会。复杂系统的研究往往会把系统看作是“不断自我组织、不断复制、不断学习和具有适应性”的系统。[1]在我们对复杂度的简单研究里，我们会以一种不太传统的方式去仅仅接触这个神奇领域的表面。

接下来让我们先阐明“复杂度”这个词。在Jeremy Campbell所写的《Grammatical Man》一书里，它把系统理论中多种元素编织在一起，以此去研究信息、语言和DNA之间的关系。他对复杂度给出了以下的描述：

> 在生命器官乃至是在机器里都存在着一种“复杂度障碍”（complexity barrier）。在这重障碍之外有着极高复杂度的系统，它们完全是靠全新的理论来起作用的。 复杂度不单是一个由多部分组成，且各部分之间有着不简单的关系的系统中的要素，而且它是一种掌控着自己所有权的特殊物质，正是它使得复杂系统区别于简单系统，让它们能做出以及变成我们本没预想到的东西。[2]

Compbell并没有对复杂度给出一个准确的定义，但以上这段话为这个概念提供了很有价值的描述。复杂度是系统里的一种特征，根据Campbell所说的，并非所有系统都是复杂的：只有那些达到了他所说的“复杂障碍”的系统才是。在一个复杂系统里，系统的各种元素间的内部关系是混杂在一起且极其复杂的。

虽然能准确定义这种“复杂障碍”的数学模型是存在的，但从我们的目的来看，简单系统和复杂系统之间的区别更多是概念层面而不是数学层面的。像木桌子那样的简单系统也有着多个相互关联且共同组成自身整体的组成部分（例如4条桌腿和1块桌面），并且其整体是大于部分之和的，因为一张完整的桌子所能提供的作用是各个单独部件所不能提供的。但它显然是一个简单系统，因为各个部分间的关系是固定且完全可预知的。

从系统的层面来说，桌子是比游戏简单得多的，哪怕是最基础最简单的游戏。在井字过三关里，各部分之间的关系、玩家行为的不可预知性、系统随时间的动态变化、结果的不确定性……以上种种都带来了游戏的复杂度，这种复杂度是从根本上不同于桌子的复杂度的。正如Campbell所指出的，这种复杂度是“一种掌控着自己所有权的特殊物质”，换到游戏的情况里，这种特殊的复杂度会产生出有意义的玩乐。如果一个游戏里没有表现出复杂度，那有意义的玩乐也不会随之出现。

## **信使与建筑**

为了让我们的讨论不仅限于游戏，接下来让我们看看一个并非游戏的系统实例。这个系统实例是一个通信网络，这是一座虚构的城市，一个信使在多栋建筑间来回传递信息。这个系统最简单的版本是只有两栋建筑，每栋建筑产生信息用于传递给另一栋，而信使需要在两栋建筑间来往。

![](https://whdolzxt1k.feishu.cn/space/api/box/stream/download/asynccode/?code=NzJlYTdlMjMzYzFiNGNmZjBlMzUzMjA5ZmJhNDhlMTdfRTdrTlI0eUdoMEpuTHVQUmY1eHlIeHJkQ0dmVVZ4ZGtfVG9rZW46VGZBbmJPRnI0b1ZNS1F4UkZJb2NoMnlwbmlkXzE2ODQzNzYxODg6MTY4NDM3OTc4OF9WNA)

总的来说，这并不是一个复杂系统。虽然信使的行为与建筑不停改变状态都让这个系统比前面桌子的例子要明显复杂，但该系统的行为是固定且可预知的。信使会在两栋建筑间来回奔走。即使两栋建筑以随机的间隔去产生信息，使得信使永远不知道下一条信息会在何时何地出现，但这还是不会对整体系统增加任何实质的新状态。

那如果我们往其中加入一些新的元素和关系，把它推向更高的复杂度，那会怎么样呢？设想如今有10个信使要在50栋建筑间传递信息，这50栋建筑的位置是随机摆放的。建筑之间的距离决定了信使往返所需的时间。这点是很重要的，因为我们需要让效能最大化：假如有一个信使过长时间处于非传递信息的状态里，那整个通信系统都无法合理运作。当加入了这些元素以后，系统的复杂度突然间明显提升了。

![](https://whdolzxt1k.feishu.cn/space/api/box/stream/download/asynccode/?code=Y2RjYzY1NzMxMjBhZTBkODQwMjI1NWFjOGJiOTNlZmNfS3RVVUw5bFRRNDB5WFZtV1VISlNqZ2owOEt1aTJ2cldfVG9rZW46VVEwM2JJM3BCb0NiUzl4OFZhbWNxdHlCbnNkXzE2ODQzNzYxODg6MTY4NDM3OTc4OF9WNA)

要理解后来新加入的复杂度，你可以想想一下如今你要编写一个计算机程序去管理信使的行为。在2栋建筑的系统里，这个程序是很简单的，只需要让信使在两栋建筑间来回跑就可以了。但到了10个信使50栋建筑的场合里，这个任务就很复杂了。如果一个信使把上一封信件送到一栋建筑里，而此时没有任何能拿起的新信件，此时他该去哪里呢？此时可以选择去当前离自己最近的建筑，但也应该把其他信使刚去过的建筑考虑在内，因为那些最近没有访问过的建筑往往是最有可能发出下一条等待传递的信息的。

你还可以想想，当信使拿起了多封信件，需要去城市里不同地方的建筑投信时，他该怎么办。到底应该用什么样的逻辑来决定信使投递信件的方式呢？如果信使都可以在建筑里以及建筑与建筑之间碰头，互相交换信件从而使工作更有效率，那会怎么样呢？如果是这样，那这些信使应该在何时何地及如何会面呢？通过交换信件来把送到同一栋建筑的信件合并在一起投递，这能让系统变得更有效率，但如果信使会面太频繁，那系统的整体效率可能也会下降的。此时这个通信系统不再是一个简单的可预知的系统了，不再是在两种状态间来回摆动了。它已经从根本上达到一种全新的复杂度，有着错综复杂的内部关系了。

如果你觉得这个情况还不够复杂，我们还可以为之加入更多的变量。例如，假如某些建筑与其他建筑有着特殊关系（两栋建筑之间有着很多信件来往），且这些关系是会随时间改变的，那会怎么样呢？又或者假设信使不是在“建筑”之间投递信件的，而是在“公司”之间投递信件的。公司会不断变更之间的建筑地址，因此它们在城市地图上的物理位置会不断改变。又或者信使永远都无法鸟瞰整座城市地图的全景，只能从他们自身的经验以及与其他信使分享的信息里了解到城市的布局和行为，这时情况又会有很大变化了。

要写一个电脑程序来模拟以上所有情况，这比起最初的例子是要难得多的。事实上，这个例子也展现了复杂度研究中关于信息传递和社会行为建模的一部分问题。是什么使得我们的通信系统如此复杂呢？正是系统中各个部分间存在的动态且随时可能产生的内部交错关系使得系统超越了Campbell所描述的“复杂度障碍”。这个系统的初始版本只有2栋建筑和1个信使，比较之下显得很简单和机械化。但更复杂的版本囊括了一个有着很多智能体的生态系统。我们会在接下来的内容里通过多个例子更清楚地说明简单系统和复杂系统在概念上的区别。

## **简单复杂度**

在信使城市的例子里，由于我们把大量复杂关系和偶发事件加到里面，导致系统最终变得很复杂。但有时候复杂度会有可能从少数简单的元素里突然以难以预料的方式产生。以下这个例子是程序员兼数学家John Casti提出的，是关于行星物理学的：

> 众所周知，两个行星会围绕对方沿轨道运行，它们的行为是可以完全写下来的。然而，我们不能把三对双体问题的解决方案用来决定一个三体系统是否稳定。所以，三体问题的本质在于这三个星体相互间所有的关联。由此能看出多个相对简单的子系统在相互交互后会诞生如此复杂的行为。[3]

Casti谈的是行星运动的研究，两个星体的系统（例如一个恒星和一个围绕它运动的行星）能用数学来准确预测到它们在太空里的运动。然而一旦把第三个元素加到这个体系后，每个星体的引力都会影响另外两个星体，这会让决定着它们相对运动的数学因子被极大地复杂化。

第三个星体的加入让这个系统里一切都改变了：系统超越了Campbell所说的“复杂度障碍”，变成了一个确实很复杂的系统。系统里各种元素间的关系也以很复杂的方式纠缠在一起，产生了数学上很难解决的动态结果。这个例子最让人吃惊的是系统里包含的元素极少。两个星体是一对简单关系，只对系统里加入一个元素就让其复杂度提升到完全不同的层级了。

现实中还有很多看似简单的系统是实际上复杂得夸张的。例如一次谈话可能只有两个人在彼此交互。但当你把认知、社交、感知、语言，以及背景因素都考虑在内时，显然一次简单的交谈就变成一个极为复杂的过程了。

## **什么不是复杂度**

> _到底什么是复杂度？有序系统肯定是不复杂的，也就是系统中每一点在时间和空间上看起来都像其余点的系统。此外，当系统是随机时，也就是空间中的每一点与其余点完全没有关系的系统，去谈它们的复杂度也是没意义的。——_ _**Per Bak**_ _，《How Nature Works》_

探讨复杂度概念的其中一种方式是找出什么不是复杂度。根据物理学家Per Bak的定义，一个复杂系统不能是太有序的，也就是系统每时每刻的行为不会完全一样。与此同时，这个系统也不能是完全混乱的，也就是系统在每一刻的运作与下一个时刻不能只是随机对应的关系。Bak所说的一个系统在时间和空间上的点是指系统在一段时间内随时间的组织方式。观察系统中的各种关系在每时每刻的改变情况能帮助我们确定一个系统是否具有复杂行为。

例如以电视屏幕这个非复杂的例子来看。当电视没有接收到电力或者任何类型的信号时，它是完全黑屏的。此时每一个像素都会一直保持黑色（“每一点在时间与空间上看起来都像其余点”）。另一方面，当屏幕充满了随机静电噪音时，这个系统是完全混乱的，屏幕中每个点在一个时刻里的颜色与下一个时刻，以及其他点的颜色是完全没有关系的（“每个点与其余点完全没有关系”）。

相比较，如果用图表来现实信使通信系统，情况就完全不一样了。屏幕能显示出某些静态元素（例如建筑），但信使会在建筑间移动过程中从屏幕的一点移到另一点上，他们会拿下或者放下信件，在建筑间碰头来交换信件。这跟完全固定或者完全随机的一组点是不一样的，信使的显示会因为它们在空间中的行为模式而有着自己的逻辑和节奏。这些不可预知却又有着可视化模式的复杂行为序列能反映出其底层极为复杂的系统。

## **四类系统**

在讨论复杂度与游戏前，让我们先总结一下。我们已经看过多个系统的例子了，其中一些是很复杂的，而另一些则不然。那这些不同程度的复杂度彼此之间是如何关联的呢？人工生命领域的出色的数学家Christopher Langton提供了四种方式帮助我们理解一个系统的复杂程度。[4]

图中每一类都对应了一个系统里可能出现的不同程度的复杂度。

![](https://whdolzxt1k.feishu.cn/space/api/box/stream/download/asynccode/?code=ODAzMGJiMWM0NDYxNmM2Yzg4ZTY0MzI1ODc0YTZkOWVfWjFFdmZGZ05wcnNTNkdZY3BPMllPdkV2YUZBNVI4RXdfVG9rZW46Ukx6TWJyemlpb0c0Tzl4b3htcmNobUpoblRkXzE2ODQzNzYxODg6MTY4NDM3OTc4OF9WNA)

-   在最左边的是一直不会改变的固定系统。这些系统里各种元素间的关系是一直保持不变的。电视机那一直不变的黑屏就是这类系统的一个很好的例子。
    
-   固定系统的右边是周期性系统。周期性系统是无尽地重复同一种模式的简单系统。信使系统里2栋建筑的简单版是让单个信使来回摆动的，它就是一个周期性系统。
    
-   在最右边的是混乱系统。在混乱系统里，各种元素是不断运动的，但它们的状态和关系是随机的，就像电视机屏幕充满静电噪音后的样子。
    
-   最后一类让我们最感兴趣的是复杂系统。这种系统比周期性系统要更复杂和更不可预测，但它也不是完全由动态关系所组成，不会成为一种混乱系统。
    

考虑到所有这四类系统都可能存在，那复杂系统只在其中占据了很狭窄的一个范围。一个复杂系统存在的条件是像一个星体能支撑生命存在的条件：在宇宙中存在的众多星体里，只有很少一部分能有合适的气温、大气、气候组合在一起来允许生命的诞生。那让系统能变成复杂系统的特殊条件是什么呢？特别是换到游戏的情况里是怎么样呢？

## **两个糟糕的游戏**

我们对复杂度最后的讨论得回归到游戏设计的领域上。我们都知道游戏就是系统，但到底是什么促使一个游戏变成一个复杂系统呢？我们在前面看过了不复杂的系统，其目的是为了找出复杂系统的特征。接下来我们用了类似的方法，列出了一些无法称得上复杂度的游戏。从游戏的角度来看，它们是很糟糕的，但正如所有糟糕的游戏那样，它们都能教会我们不少东西。其中第一个游戏叫做《Heads or Tails》（猜硬币）：

《Heads or Tails》是一个两人玩的游戏：一个玩家背着另一个玩家翻一个硬币。另一个玩家猜测该硬币是正面朝上还是反面朝上。如果猜的人对了，那他就胜出，否则则翻硬币的人胜出。

这个游戏听起来肯定不大有趣的。设想这个游戏只玩一次：对翻硬币的玩家来说，他翻了硬币后就等着答案了，然后再看看猜的人是对是错。即使把这个游戏玩了一遍又一遍，它还是纯属于一种翻硬币和猜硬币的行为而已。游戏看起来太简单了，完全称不上复杂。另一个游戏的例子没这么简单，但也无法称之为复杂：

这个游戏叫《Grid》，也是两个人玩的：游戏在一个100×100的格子矩阵里展开。每个玩家有着10个一模一样的棋子，在游戏开始时把它们随机放到棋盘上。一个棋子占棋盘上的一格。玩家在每轮里轮流把10个棋子都移动一次。移动一个棋子意味着可以从垂直方向、水平方向和斜角方向的任意组合里把棋子移动1～1000格。这些棋子是不会以任何方式相互影响的。

这个游戏听起来也很无趣。玩家轮流回合，费力地把自己的棋子在棋盘上移动，但由于玩家不会互相影响，所以游戏会无穷无尽地继续下去，没有人会从中胜出。玩家可以在棋盘上用棋子摆出各种图案，但这些图案最终对游戏的获胜是不带来任何意义的。这些棋子就像静电噪音那样，它们是不停在运动的，但却永远不会组成有策略的模式，各部分之间不会存在有意义的关系（正如Bak所说的那样，这些棋子只是“毫无关系的点”）。

无论是《Heads and Tails》还是《Grid》都没有复杂度。它们都是差异很大的游戏。那导致它们没有复杂度的共同点在哪里呢？要回答这点，我们需要回顾有意义玩乐的核心概念。

在一个游戏里，有意义的玩乐从玩家行为与系统结果之间的关系中产生，它是玩家在游戏系统中采取行为且系统对该行为作出响应的过程。游戏中一项行为的意义存在于行为和结果间的关系里。

从有意义玩乐的角度去思考这两个游戏，显然这两个游戏都没有在玩家行为和系统结果间促成有意义的关系，也就是没有在玩家做出的决策和这些决策在游戏里所产生的结果间促成意义。在《Heads and Tails》的例子里，游戏只由一个随机事件组成，该随机事件决定了游戏的结果，而双方玩家对这个结果是没有任何控制权的。而《Grids》这个游戏缺乏有意义玩乐的情况是不同的：它不像《Heads and Tails》，它完全没有随机性，玩家在每一轮都会作出很多决策来移动他们的棋子。但由于这些决策没有任何途径能产生有意义的游戏结果，使得这个游戏最终也缺乏有意义玩乐。

如果这两个游戏都缺乏复杂度，同时它们也缺乏有意义玩乐，那是否意味着有意义玩乐和复杂度就是一回事呢？并不如此。有意义玩乐和复杂度是游戏里不同的两个方面。有意义玩乐关注的是决策和结果间的关系，而复杂度关注的是系统里各个部分相互关联的方式。不过虽然有着这个区别，这两个概念是紧密关联的。在具备有意义玩乐的游戏里，游戏系统中某些方面也会是复杂的。复杂度的形式多种多样，可能是形式策略上的错综复杂，可能是复杂的社会关系，可能是丰富的叙事结构，也可能是现金赌博带来的心理上的复杂度，又或者还有其他的方式，但无论如何，复杂度是有意义玩乐的先决前提。没有了复杂度，一个游戏的可能性空间是不足以庞大到支撑有意义玩乐的。

那如何才能把《Heads and Tails》变成一个能支撑有意义玩乐的游戏呢？我们可以对系统的规则作出简单的调整，看看这些调整会引起什么改变：

**《Heads and Tails》：决策版。** 翻硬币的人不再是随机翻转硬币了，而是需要决定哪一面朝上。另一个玩家基于这个行为去猜测翻硬币的人选择的是哪一面。如果猜测者对了，那他就赢了，否则就是翻硬币的人赢。

在这个翻硬币游戏的版本里，猜测者会一直尝试判断另一个玩家的决策，而不是纯粹去猜测一次随机事件的结果。那这个改变会对游戏带来有意义的玩乐吗？它让游戏变得更复杂了吗？的确，它让游戏不再是一次随机事件了：一个玩家会不断从心理上去估摸另一个玩家，尝试去猜测他的意图。但尽管这样，只玩这个版本一次是不会让它进入到复杂度的领域里的。为什么不会呢？因为此时游戏还是让人感觉随意。即使翻硬币的人能决定硬币的哪一面朝上，游戏的整体结果还是让人感觉是随机的。随机性玩乐是指哪种行为看起来都是毫无关联的，这是有意义玩乐的反面。另一个重要的方面在于游戏没有持续足够长的时间，没有留下任何的线索或者大背景来支持玩家的决策。想象对一局游戏来说，玩家只能把规则试一次，而后游戏就结束了，没有任何机会让他们的决策能以有意义的方式去影响到将来的结果。

所以无论翻硬币是随机还是预先决定的，如果只是一局游戏，那它还是缺乏复杂度的，因为此时它还是缺乏有意义玩乐。正如我们所指出的，有意义玩乐和复杂度不是同一种东西：它们指的是游戏里不同的方面。但复杂度是有意义玩乐的必要前提条件。以下是翻硬币游戏的多个不同的变体，这些额外的变化能有力地强化游戏的复杂度。每个版本都对游戏的部分规则作出调整，影响到玩家行为与系统结果的关联度。虽然每个变体只对游戏增加了一些新规则，但它们都让游戏系统的运作越过了复杂度障碍，成为了有意义的玩乐。

**交谈版。** 在游戏的这个版本里，翻硬币的人会决定硬币的哪一面朝上。但在猜测者开始猜测前，两个玩家能有10分钟的时间去讨论到底该做什么样的决定。翻硬币的人可以说谎，也可以说真话，又或者可以用复杂的双重心理战术。如果猜测者猜对了就赢，否则则翻硬币的人赢。

_为什么这样更有意义：在交谈版里，丰富的社交手段把游戏提升到有意义玩乐的领域里。翻硬币的人能选择一种欺骗策略，而猜测者需要战胜这种策略。猜测者最后作出的猜测是整场谈话里引出决策的一部分。_

**重复猜测版。** 在这个变体版本里，翻硬币的人依旧去决定硬币的哪一面朝上。游戏不允许任何讨论，但这两个玩家会把这个游戏玩上21次。每当猜测者猜对了，他会得到1分。每当猜测者猜错了，则翻硬币的人得到1分。到了游戏结束时，分数最多的玩家胜出。

_为什么这样更有意义：重复猜测版跟决策版是很像的。两者区别在于前者是要玩上很多次的，这就有机会能诞生各种模式。正如剪刀石头布那样，两个玩家会不断猜测对方，尝试去找出对方的行为模式。每一次选择都是基于双方过去作出的决策决定的。_

**逐步增加风险版。** 在这个版本里，玩家轮流承担猜测者和翻硬币的人的角色。每一轮，当前猜测者会尝试猜测一次随机翻硬币的结果。如果猜测者猜对了，则得到1分，并且能选择让硬币再翻再猜一次。如果猜测者第二次还是猜对了，则得到的分数会变成双倍（从1分变成2分）。只要猜测者猜对，则他可以继续猜下去，不断赢得上一次猜对所得的双倍的分数，也就是从1分到2分、4分、8分等等。但一次猜错会清除该轮得到的所有分数，而后双方交换角色。第一个累加得到25分的玩家胜出。

_为什么这样更有意义：虽然这个版本还是用随机翻硬币的方式，但玩家是以有意义的“碰运气”的方式去作出可能会带来奖励或惩罚的选择的。每一次的游戏行为都会对本轮的所有决策带来影响，同时还会对整个游戏带来影响。例如，如果你的对手快要赢了，则你就被迫要承担更多的风险去尝试了。_

每一种翻硬币游戏的变体都对游戏的决策和结果增加更多的关系，并且把这些交互行为融入到更上层的游戏结构里，以此来促成有意义的玩乐。翻硬币游戏的原始版本只是概率上的一种简单行为。但对后面的多个变体来说，没有一个能预知到游戏是如何进行的。例如，在交谈版里，玩家间的谈话会是怎么样的呢？在重复猜测版里，玩家会产生出什么样的行为模式呢？在逐渐增加风险版里，有多少玩家愿意承担风险呢？在这些变体里产生的游戏体验是复杂得让人吃惊的，相比于它们如此简单的规则，其复杂度会让你难以置信。就像这样，系统从简单规则中产生出复杂和难以预知的行为模式的现象，我们把它称之为涌现。

## **涌现（Emergence）**

> _适度数量的规则一遍又一遍地应用在有限数量的对象上，从而引出了多样性、新奇性和惊喜性。你可以描述所有的规则，但肯定不能描述规则所产出的所有产物——例如所有罗马数字的可能组合，例如一种语言里的所有句子，例如由进化所产生的所有生物——_ _**Jeremy Campbell**_ _，《Grammatical Man》_

涌现是理解一个游戏的系统如何变得有意义的一种关键的理解方向。在前面引用的描述里，Jeremy Campbell描述了涌现是如何从复杂度里产生的。Campbell所说的第一句话指出了涌现的多个关键特征：也就是一组简单的规则作用到一个系统里有限数量的对象上，从而引出难以预测的结果。这放到翻硬币游戏的三个例子里是很准确的。交谈版里面玩家进行游戏的方式的数量是无穷无尽的。但游戏本身却是如此简单！这正是游戏里涌现的关键之处：由一组简单规则所产生的复杂可能性。

大多数游戏都有这个特征。兵乓球的规则也是相对简单的，但如果你去想象这个游戏玩起来的所有方式，显然从它的系统里能看出涌现，例如当一个玩家占优势时可以快速结束比赛，例如也可以是一场漫长的拉锯战，又或者有一个戏剧性的结果。即使是像《魔兽争霸2》这样有着复杂得多的规则集的游戏，游戏里也是包含涌现的。虽然这个游戏相比于乒乓看起来很复杂，但从本质上来说《魔兽争霸2》只有少量不同类型的元素，它们之间的交互方式也是很有限的。如果两个敌对部队相遇，它们不会展开一场谈话或者一起跳一场舞，而是要不处于战斗，要不不处于战斗。尽管游戏的代码有着一定复杂度，但诚然还是“适度数量的规则”作用到“有限数量的对象”上。游戏里各种系统在游戏过程中会产生涌现中各种难以预知的模式。

通过把范围如此宽广的游戏现象囊括到涌现的分类里，我们诚然是从正统的复杂度理论里进一步延伸概念了。涌现的理论学家往往会对“强”涌现和“弱”涌现作出明确的区分——例如，除非乒乓球是一个自治的自适应的个体，能自己去学习如何避开或撞到球拍上，否则这个游戏还不能看作是“强”涌现的情况。不过，从我们的角度来看，我们会把这两种区分合并起来，从更通用的角度去考虑涌现。涌现能透过复杂的程序机制产生，这个程序机制会模拟出自适应的智能体和系统。与此同时，自适应还能在体验层上出现，也就是从极其简单的多条规则里诞生出玩家间复杂的社会或心理关系。

## **部分与整体**

不管我们用什么样的方式去看，所有这些涌现的实例都有着一些共同的特质：

> 涌现首先是一种有着互相联系的依赖于上下文背景的各种交互方式的产物。从技术上来说，这些交互方式及其产生的系统都是非线性的：也就是整个系统的行为是不能简单把构成该系统的各个部分的行为加在一起来表达的。我们无法把各种棋子的行为数据加在一起就说我们了解这个桌游了，同样我们也无法只通过了解普通的蚂蚁来了解一个蚂蚁族群的行为。在这种情况下，整体实际上是大于其部分之和的。[5]

这段话引自计算机科学家John Holland的原话，话里包含了大量跟涌现相关的概念。由于Holland是从具体例子谈到通用情况的，所以我们会逐行地解释这段话，从最终的陈述再回到最初的描述。在这段话的最后一句里，Holland说明了当涌现生效时，“整体实际上是大于其部分之和的”。这点符合我们对系统的整体理解，系统里各个部分是通过互相关联来组成一个整体的。在涌现系统里，各个部分与整体间存在着一种特殊关系。由于涌现系统会以各种难以预知的方式展开，所以游戏的整体是大于其各部分之和的。

那Holland说这点到底想说明说明呢？我们可以看一下前一句：

“我们无法把各种棋子的行为数据加在一起就说我们了解这个桌游了，同样我们也无法只通过了解普通的蚂蚁来了解一个蚂蚁族群的行为。”

Holland用桌游和蚂蚁族群来作为涌现的例子，他指出这些系统是无法只通过了解系统中单个孤立对象的普遍行为来了解整个系统的。这个概念很接近于Campbell提到的概念：“你可以描述所有的规则，但肯定不能描述这些规则所产生的所有产物——例如所有罗马数字的可能组合，例如一种语言里的所有句子，例如由进化所产生的所有生物”。Campbell所指的是，在一个涌现系统里，你可能清楚所有的原始规则，但你无法描述当这些规则运作时会产生的所有情况。他给出了数学、语言和进化上的不同例子。例如在一种语言里，我们无法描述该种语言能支持的所有句子，即便我们已经清楚该语言中的所有字词以及组织这些字词的所有语法规则也是如此。

Campbell和Holland说的都是同一点：让一个系统具有涌现的关键在于系统的规则以及这些规则所延伸的产物间存在着一种特殊的割离。虽然规则都是准确和已知的，但这些规则的行为当在系统中生效时会产生出规则本身所无法包含的模式和结果，它们会共同产生出“多样性、新奇性和惊喜性”。语法规则能让我们知道如何把字词组织成句子，但它们无法预知到有“Huckleberry Finn”这个人，无法预知到美国宪法，也无法预知到有Britney Spears的“Oops! I Did It Again”的这句歌词。语法规则透过语言的运用，在生效时超越了复杂度障碍，产生出涌现的结果，这些结果是永远不能用区区一组规则去预知的。

这正是Holland所说的“整个系统的行为是不能简单把构成该系统的各个部分的行为加在一起来表达”的意思。仅仅把所有规则整合在一张清单里并不能说明一个涌现系统里多种多样的行为。Holland所说的“从技术上来说，这些交互方式及其产生的系统都是非线性的”，这句话是说它们从数学上来看是非线性的。他指的是这些对象在系统里的交互所产生的复杂度不是逐渐累积的，而是按几何级别提升的。这正是在三体系统的例子里所看到的复杂度。对系统中增加第三个星体并不单纯累加了系统的复杂度，而是把它极大提升到新的复杂度层级了。

## **对象的各种交互**

如今我们已经解读到引自Holland的那段话的第一句了：

“涌现首先是一种有着互相联系的依赖于上下文背景的各种交互方式的产物。”直到如今为止，我们已经看过一个系统里可能产生的各种涌现的例子。那到底是什么让一个系统能越过其复杂度障碍，变成真正的涌现呢？这里的关键在于“互相联系”和“依赖于上下文背景”这两个词。Holland所说的涌现是一种有着这两种交互形式的产物，是一个系统里各种对象间的交互。

回顾《系统》一章里Littlejohn提到的系统的四种元素：对象、属性、内部关系和环境。当一个涌现系统的各种规则生效时，对象间的内部关系会逐渐改变各种元素的属性。这些改变随后会影响到对象的内部关系，这会进一步改变它们的属性，从而导致行为的循环和模式化。因此，一个复杂系统里各种交互是相互联系的，也就是系统中的各种元素是递归联系的。正如蚂蚁族群中的蚂蚁那样，系统中各种对象会以单个对象无法做到的方式相互作用。由于这些对象是互相联系的，系统中的一点点改变会产生其他改变，而改变会进一步导致进一步的改变，让系统的空间产生一系列的模式更改。这些交互是依赖于上下文背景的，也就是出现的各种改变不是每一次都一样的。相反，这些改变会依赖于系统在特定时刻正在发生的情况。互相关联的交互能在系统里产生全局性的模式，而交互依赖于上下文背景能确保这些模式的每次排布是随时间动态改变的。

在信使通信系统的例子里，各种对象（信使和建筑）都有着属性和彼此间的关系。如果信使从一栋建筑里拿起信件，则建筑的属性（是否有未派出的信件）和信使的属性（是否有要投递的信件，下一个目的地是哪里）都会因此改变。随着系统不断运作，系统中各种对象会按系统规则所定义的方式去彼此交互。如果系统真是涌现的，那各种对象的行为会产生无法预知的模式，这些行为是不包含在规则本身里的。例如，设想我们决定把所有无需派出信件的建筑涂成蓝色，那蓝色建筑的图案是会不断变化的。这些图案不是任何一条系统规则中的一部分，而是在系统规则运作时随之产生的。这正是本章开头引自Steven Johnson所说的机械撞球所做出的涌现图案。在这两个例子里，系统中各种元素间互相联系且依赖于上下文背景的交互产生了这种涌现现象。

## **The Game of Life**

在复杂度理论的领域里，或许最有名的例子是来自于细胞自动机的数学研究的。细胞自动机是一个大致类似于游戏棋盘的建立在格子上的系统。在任何一刻，格子要不是空的，要不被占据。系统有着一系列规则描述各种细胞是如何行为以及它们的状态是如何随时间改变的。“细胞自动机”这个词从格子矩阵里产生，每个格子称为“细胞”，一旦系统运作后，规则会不断推动系统，让其无需从外部给出任何输入就自动化地运作。

并不是所有细胞自动机系统都会自动地产生涌现的。它完全取决于掌控着细胞行为的规则本身。例如，如果我们想在细胞自动机格子矩阵里重现一个空白的电视机屏幕，那我们可以建立以下的规则：

1.  最初所有细胞都是没被占用的。
    
2.  细胞的状态不会改变。
    

这些规则会产生一个有着黑色空白领域的固定系统。如果我们想用细胞自动机系统重现一个完全混乱的情况，那我们可以建立以下的规则：

1.  最初一半的细胞被占用，另一半没被占用，这是随机决定的。
    
2.  每隔三分之一秒，重现随机决定一半的细胞被占用。
    

这些规则会产生一个不断在改变却毫无图案和光泽的点，使其组成电视机静电噪音时的样子。

细胞自动机最初是由John Von Neumann和Stanislaw Ulam分别在20世纪30和40年代建立和发展的。但其最有名的应用来自于John Conway。他所做的细胞自动机系统叫做“The Game of Life”，简称Life，在Martin Gardener在1970年的《Scientific American》杂志上作为谜题发布后被进一步推广开来。

“The Game of Life”有着很多种迷人的观察方式。它让我们最感兴趣的一点不在于它是人造生命的一种早期形式，也不在于它能称之为游戏（从我们的定义来说它不是一个游戏），而是它是涌现和复杂度原理的一个精彩的例子。Life是在一个无限的格子矩阵里进行的，矩阵格子里的细胞由一组简单的规则掌控，以下是Steven Levy在《Artificial Life》里对其的总结：

> 生命是在一个虚拟的棋盘上产生的，棋盘上的格子称之为细胞。细胞有两种状态：存活或死亡。每种细胞最多可能有8个邻居，也就是紧贴着它四边和四个角的细胞。 如果格子上的细胞是存活的，且它周围有2～3个细胞也是存活的，那它在下一个时间点（或者下一代）会存活下来。如果它周围有多于3个细胞是存活的，那它会因为过度拥挤而死亡。而当周围存活的细胞少于2个时，它也会因为过分暴露而死亡。 如果格子上的细胞死了，它会在下一代继续保持死亡，直到它周围8个格子里有3个细胞是存活的时候才活过来。在这种情况下，细胞会在下一代“生长”出来。[6]

虽然Conway的Life最初不是在电脑上做的，但如今它已经出现在电脑软件上了。Life在开始时往往是以随机或者预定义的方式让一部分格子填满，另一部分空着。当程序运行时，格子会在每一代进行更新，每一代都根据当前格子上的配置来迭代所有规则。从视觉上来说，Life在各个格子细胞死亡和生长的过程中展现了一组动态的不断变化的几何图案。

![](https://whdolzxt1k.feishu.cn/space/api/box/stream/download/asynccode/?code=OWM1MmRkNTVkYTQzMmJhOGIyNjZiNzUzZDQwYWMwMDJfdE5XSlQ0VEdYdENGN3FNNW5RMFFhUEFNc2VXTmI3ZWhfVG9rZW46QTlqQ2JCcmY1bzY4eHN4eWxLVGNKeUdQblZsXzE2ODQzNzYxODg6MTY4NDM3OTc4OF9WNA)

The Game of Life: Glider模式

![](https://whdolzxt1k.feishu.cn/space/api/box/stream/download/asynccode/?code=NDgwNWVmOGQwMGZlMWY0YmJmYjVhMjZmMDllODZhODRfUmhNWno4bWNoekE2VFd4ZGgzNERnalB6eFFES0xLWHZfVG9rZW46UDBVMmJQa0hMb3B1SEt4UDN0amNHaUNCbnFoXzE2ODQzNzYxODg6MTY4NDM3OTc4OF9WNA)

The Game of Life的一些样例

Life最让人吃惊的一点在于，从这些极其简单的规则里诞生出难以预料的模式。其中的一些形状会在格子里快速地消亡，而另一些形式则在格子里保持稳定，又或者永远在两种状态间摆动。有一些细胞会在格子上稳定地移动（就像前面著名的“Glider”模式那样），还有一些会展现出更复杂的行为（例如“Glider gun”模式，每隔30代会产生一个新的“Glider”）。

通过把这些不同的模式和难以预知的行为结合在一起，Life的Fans们做出了各种各样的东西，包括各种丰富的图案、能使用的计算机，以及用格子上的细胞来运作的“虚拟机器”。Life是一个复杂系统，它展现了一套简单的规则所能衍生的涌现行为。通过研究Life这个例子，我们能清楚了解到涌现是如何从系统的各种元素间互相联系且依赖于上下文背景的交互里形成的：

**互相联系：** 在Life里，两两对象间的交互并不是彼此孤立的。相反，两个对象间的关系取决于整组互相联系的关系。Life中的细胞无论是死亡还是重生都取决于它相邻细胞的位置和状态，而这些相邻的细胞的存活和死亡又取决于它们相邻的细胞。这种互相联系的关系产生了横跨整个空间的环环相扣的形式，从而产生出让人吃惊的图案。

依赖于上下文背景：在持续时间里，随着系统中一个对象的上下文背景发生改变，它与其他对象间的关系也随之改变，从而让系统发生全局性的改变。在Life的例子里，一个细胞的上下文背景是其周围8个细胞的情况。这个背景在每一步里都会变化，在整个系统中动态地传播行为。正如互相联系的交互会在整个格子空间中传递那样，依赖上下文背景的交互会在系统空间中随时间改变，为系统里各种对象塑造出新的上下文背景。

## **自底向上行为**

“The Game of Life”里让人吃惊的一点在于从简单一套的规则里衍生出相互联系且依赖于上下文背景的众多交互。我们可以来总结一下这些细胞的行为有多简单：

-   如果一个存活的细胞周围有2～3个细胞是存活的，那这个细胞在下一代会继续存活下来。
    
-   如果一个死亡的细胞周围有3个细胞是存活的，那这个细胞在下一代会重新活过来。
    
-   除此之外，细胞都会死亡。
    

事实上，这些简单的规则能产生从Glider gun到可运作计算器等一切可能的情况，这点是非常让人吃惊的。Glider gun是以上三条规则里没有提到的，但矛盾的是这种情况却实实在在地存在于这三条规则所定义的可能性空间内。这些细胞所有可能的模式以及所有虚拟机器都能在Life的格子里产生，在“The Game of Life”里能发现到的众多的“生命”形式都能一定程度上包含在这三条规则之内。

Life展现了在涌现系统里，简单的局部交互是如何引发出更上层更复杂的模式的。复杂度理论学家往往用自底向上这个词来总结这种现象。理论学家Steven Johnson用以下的话来描述了诸如蚂蚁群落、城市空间和自适应软件等系统中的自底向上过程：

> 这些系统都有着哪些共同特征呢？共同点在于它们都是自底向上的系统，而非自顶向下的。这是什么意思呢？在这些系统里，各个智能体会寄居在一层里，不断产生各种行为，这些行为会在它们上方再搭建一层：例如蚂蚁塑造出群落、都市里的居民塑造出邻居、简单的图片认知软件学会了如何推荐新书。这种从低层规则向高层复杂现象的转变正是我们所说的涌现。[7]

Johnson说到，除了这类系统外，还有另一个重要类别的系统是有着自底向上的涌现的：那就是游戏。游戏在规则的形式结构促成难以预知的玩乐体验的过程中能产生复杂的涌现行为。正如Glider gun包含于Life的规则里那样，所有层级进行过的棒球比赛，各种各样的获胜战术、各色各样的团队和球员情况，所有这些都一定程度包含在棒球的规则里。

自底向上涌现是游戏天生具备的，它不只限于游戏的形式复杂度里。涌现能在任何游戏的规则、玩乐和文化层里以不同形式出现。我们在本章只谈到涌现的形式特征，但从一定意义来说，本书其余部分都会延伸这里的概念，探讨一个游戏里能产生的各种有意义玩乐的方式。

## **游戏中的涌现**

涌现的很多研究都会研究像“The Game of Life”这样的系统，这些系统是自治且不需要主动的人力参与就可以运作的。但Life并不是一个游戏。它不单缺少可量化目标，而且也不是一个有着一到多个玩家参与的冲突系统。确实，用户能设立细胞的起始状态，把它们设成存活或者死亡。但一旦系统运作后，Life会完全自治。一旦程序运作后，Life的行为是完全不受人力交互的影响的。

游戏跟这个是完全不同的。游戏需要玩家，而玩家作出的各种决策会推动游戏前进。例如，有意义玩乐的概念是基于玩家行为与游戏结果间存在可感知关系的前提下的。游戏可参与的本质让我们很难去研究游戏，因为它和Life不同，真正的游戏总有一个以上的玩家在系统里作出各种各样的决策的。在游戏里，涌现是通过玩家与形式游戏系统的交互以及他们作出的决策产生的。一个有力的例子是扑克中的虚张声势。虚张声势的策略（也就是假装你手里有更好的手牌）是游戏的关键组成。但这点是没有明确列入规则内的。虚张声势只是游戏里出现的一种涌现行为，它是由赌徒心理、玩家手牌被隐藏的事实，以及想要赢得游戏的欲望所促成的。虚张声势就像“The Game of Life”里的Glider gun，它是呈现在规则永远没有明确指出的可能性空间里的。

虽然最简单的游戏也能产生出数量庞大的难以预知的行为，但John Holland还是以桌游来清楚阐述这点：

桌游是简单规则能产生出极高复杂度的涌现例子。即使在传统的3×3井字过三关里，可行的配置数量也超过5万种，并且获胜的方法不是一看即明的。如果是4×4×4的三维井字过三关，那里面带来的挑战就足够吓到一个成年人了。国际象棋和围棋也有着涌现的特质，它们能不断地激发我们的好奇心，让我们在数个世纪以来一直能出现新的研究。而迄今为止的研究还远远不能达到其可能性空间的全部。在多年的研究中持续出现各种新的玩法和规则，使得当代的大师能轻易地打赢几个世纪前的大师。[8]

即使是简单规则集也能创造出数量极大的涌现复杂度。这些复杂度所显露的方式并不总是一眼能从规则里看出来的。例如，比较Holland提到的国际象棋和围棋这两个游戏。它们是世界上最古老和最复杂的游戏之一，并且它们在很多方面都是相似的。两个游戏都需要两名玩家，都是回合制的策略游戏，游戏棋盘上都有着很多棋子。那至少从形式的数学角度来看，哪个游戏更复杂呢？观察其规则，看起来国际象棋是更复杂的。在国际象棋里有6种棋子，每种在棋盘上都有着独一无二的走法。游戏还有着很多“特殊”规则，例如步兵在最开始的移动、把步兵当做皇后、王车易位等等。相比之下，围棋的规则更简单。它只有一种棋子，并且棋子一旦放到棋盘上，棋子就不能再在格子上移动了。

虽然围棋的规则集更简单，但从数学上来说是更复杂的。其中一个例子是开发电脑AI程序来玩这个游戏。为围棋和国际象棋开发程序是一大计算机科学问题，是过去数十年来无论在学术领域还是商业游戏开发里都全球关注的问题。虽然围棋的研究焦点在亚洲，因为游戏在这个地方更常见，但两个游戏在AI编程上的关注度是类似的。几年前Gary Kasparov在电脑上做的国际象棋里输给了IBM的Deep Blue，让电脑程序超越了人类的国际象棋大师。但能挑战到一个高级玩家的围棋程序还没编写出来。

为什么会有如此差异呢？因为围棋展现出程度更高的涌现复杂度，这种复杂度是由游戏棋子间互相联系的交互所产生的。围棋里每个棋子就像细胞自动机那样，它们与相邻棋子以及空格子都构成了各种关系。当这些简单的关系多重地横跨在游戏棋盘后（围棋的棋盘比国际象棋大），棋子互相联系的关系所带来的额外复杂度远超国际象棋。

这种对比并不是为了证明哪个游戏更高级一点。国际象棋和围棋都是有名的棋类运动，无论玩哪一个都是一种必需的智力追求。这里想说明的是更复杂的规则不一定能造就出同等程度的复杂度。矛盾的在于围棋里的规则更简单，但却做出了更高程度的涌现复杂度。

## **设计惊喜**

那复杂度和涌现的概念能如何运用到游戏设计里呢？显然游戏都是系统，而复杂度和涌现会影响有意义的玩乐。但复杂度和涌现会如何影响设计过程呢？从复杂系统去理解游戏能对游戏制作带来什么帮助呢？

复杂度是从根本上与有意义玩乐关联的。玩游戏的过程也是在探索一个游戏的可能性空间的过程。如果系统是一个固定的、周期性的，或者混乱的集合，那它所提供的可能性空间在广度和灵活度上是不足以给玩家寄居于其中去探索的。相反，如果一个系统是涌现的，那在游戏元素里探索其可能的关系的过程就会持续不断地吸引人了。如果游戏体验是充满“多样性、新奇性和惊喜性”的，那玩家会一遍又一遍地玩这个游戏。对于在线更新内容的行业来说，显然一个好的产品是其内容最有黏着度的产品。一部动画的Fans可能会把最新一集看上两三遍，但沉迷一个游戏的玩家会把它玩上数十、数百乃至数千次。成功的涌现游戏能在玩家一次又一次地探索系统行为的可能的排列组合时不断产生新的体验。

Peter Molyneaux做的《上帝也疯狂》是游戏涌现的一个很好的例子。游戏设计师Rollings和Morris生动地展现出一个复杂游戏系统是如何做出各种难以预料的新玩法可能性的：

在《上帝也疯狂》里，敌方武士会跑到你的传教士角色前，当传教士开始吟唱时他们会在近距离停下来。而后他们会坐下来听一段时间。如果这个过程没有被打断，则这群武士会转化到传教士的阵营。

这是其中一条规则。另一条规则是当敌方武士开始战斗后，传教士就无法转化他们了。

这在实战中意味着你可以把传教士围在你的营地周围作为外线防御。第一波的敌方武士会被转化。这个过程是自动的，玩家可以不管它去做别的事。但我们可以想象第二波的敌方武士。他们继续冲过来，然而首先进入的不是传教士的转化半径，而是最后被转化的一群武士的攻击半径。于是这两群武士会打起来，而传教士无法从中干预，不能转化第二波的武士。

这里产生的特征使得你无法不去管你的外线防御。你需要不时地在营地里巡逻，把新转化回来的武士放到传教士后面。

我不清楚这点是不是设计师预期的。很可能是。但这个涌现的例子的确很好，因为这两条规则显然不能一眼看出与这个结果是有关联的。[9]

根据Rollings和Morris的说法，《上帝也疯狂》的涌现是在两个层级上产生的：一个是各种单位之间的局部交互，另一个是更高层面上的玩家行为。玩家控制的传教士和不断闯入的敌方武士之间的局部交互产生了依赖于上下文背景的结果。这两种元素间的第一次交互把出现的敌方武士变成了己方武士。但当第二波敌方武士出现时，包含了转化后的武士的上下文背景塑造出一种全新的情况，武士们开始打起来了。决定这些单位行为的规则是相对简单的：传教士转化一定半径范围内的敌方武士。但由于武士有着自己的简单行为（他们会与敌方武士战斗，且在战斗时免疫转化），于是这些简单规则的交互产生出涌现的行为，这种行为是根据这些元素所在的上下文背景来改变的。

涌现也出现在第二个层级上：也就是玩家在游戏里更上层的行为中。正如Rollings和Morris指出的，玩家需要周期性地“在营地里巡逻，把新转化回来的武士放到传教士后面”，通过游戏的玩法来不断管理这些涌现的关系。传教士与武士交互的效果会往外扩散，从最初的局部行为扩展变成整体玩法有机组成的一部分。

这个例子说明的一点是游戏里各种元素间的关系是需要具体设计其细节的。Rollings和Morris所谈到的涌现行为之所以在游戏里出现是因为传教士和武士都有着恰到好处的属性。例如，传教士能转化敌方武士的半径范围有多大呢？转化要花多长时间？敌方武士在多远距离能发现传教士？反过来呢？敌方武士的移动速度有多快？他们是在何时免疫转化的？游戏单位的这些属性都需要仔细平衡。如果敌方武士移动太快了，又或者转化过程需要太长时间，那敌方武士都会在传教士把他们转化完成前就把传教士统统屠杀掉。如果战斗中的武士不能免疫转化，那第二波的敌方武士也会被转化，那玩家就不需要巡视营地周围的传教士了。所以只有通过仔细留意游戏中的规则设计，最后才促成了《上帝也疯狂》里各种行为的涌现。

## **引擎调试**

要让一组游戏规则能成功地产生涌现行为，这是需要一段艰难且耗时的设计过程的。你只能通过我们在第2章列出的迭代式设计过程里完成。“The Game of Life”的规则看起来是很简单和优雅的，但它花费了John Conway2年的测试和改良时间才达到这个最终形式。

在《上帝也疯狂》的例子里，各种涌现行为是游戏设计师Marc LeBlanc称之为“游戏调试”的结果：也就是通过对游戏规则进行迭代式的调试、测试和改良才塑造出丰富的游戏体验。游戏调试也用在电脑游戏《Gearheads》的设计过程里。在这个游戏里，1～2个的玩家在场上放发条玩具，企图让尽可能多的玩具跨越场上到达屏幕的另一边。玩家在放下一个玩具前等待的时间越长，则它具有的能量越多，从而能走得越远。一旦玩具放下后，玩家就无法控制它了，因此双方玩家都能用它来得分。有的玩具是很缓慢沉重的，有的玩家能推动其他玩具，就像Big AI里的发条推土机那样，有的玩家会像Ziggy机械蟑螂那样快速地闪电移动。有的玩具会像移动炸弹那样摧毁其他玩具，还有的玩具能像Deadhead那样，通过头戴骷髅面具把其他玩具吓到，让它们改变移动的方向。游戏里12种玩具每种都有着自己的特殊能力，玩具在场上彼此间的交互是游戏设计里的关键要点。

在设计过程相当前期时，游戏就做出了可玩的原型了，这让设计师能做出各种新玩具并调整它们的属性。在游戏程序里有一个下拉菜单，菜单里能调整每个道具的属性数据。当每种玩具的属性改变过后，这些修改会在游戏里马上生效，因此即使是一局游戏玩到中间，设计师还是能轻松地作出各种调整，看看这些改变会如何影响到整个游戏的玩法。这个迭代的游戏测试过程整整花了18个月的开发周期，帮助塑造出一个平衡的游戏。

在开发过程中，设计师发现了各种玩具的涌现结合玩法。他们发现虽然这些玩具能作为单个游戏单位使用，但把玩具互相结合起来能做出极丰富的玩法。往往发现ul的玩具组合是让人吃惊的。设计师Frank Lantz和Eric Zimmerman用引擎这个词来描述这些玩具的各种组合：这些玩具组合就像一个机器引擎那样，它们是一组组环环相扣的部件，这些部件共同做出了更厉害的效果。以下我们列出了游戏系统里发现的各种引擎：

拳击蟑螂：虽然Ziggy这种发条蟑螂是游戏里最快的玩具，但它的移动是飘忽不定的，当它碰到其他玩具时，它会跳到该玩具的背上（再遇到第二个玩具时会跳到它的脚上）。而另一个玩具Kanga是一个不断拳击的袋鼠角色，它会拳打自己遇到的任何一个玩具。一个简单的引擎是放出很多只蟑螂在棋盘上，最终大部分会待在别的玩具的背上，而后放出一两个Kanga玩具，通过它们来把很轻的蟑螂打飞，让它们飞到屏幕的另一边来得分。

炸弹盾牌。游戏里有两种破坏性的玩具，它们分别是Disateroid和Walking Time Bomb。Disateroid是一个移动很慢的巨型机器人，它会对遇到的任何玩具向前射出激光，把遇到的玩具消灭。而Walking Time Bomb是一个很强大的中速移动的玩具，但当它没有能量时就会爆炸，把附近除了Disateroid以外的所有玩具都清除，Disateroid是炸弹唯一不能破坏的对象。其中一种引擎是把这两种玩具组合起来，先放出一个Disateroid，再马上跟着它放出Walking Time Bomb。由于后面被推着，炸弹会把原本移动很慢的Disateroid往前推，而激光会把前方所有的玩具清掉，为两个玩具的得分清出一条道路。即使Walking Time Bomb在到达屏幕一侧前就爆炸了，Disateroid也会在爆炸中幸存下来，很可能会得分。

永恒运动：一种更复杂的引擎是利用Handy和Crush Kringle两种玩具。Crush Kringle是一个专业的摔跤圣诞老人玩具，它能稳定地在场上移动，周期性地停下来重踏地面。当它踏地时，所有附近玩具的方向会从左边变成右边。Handy是一个会移动的白手套，它的特殊能力是当遇到场上一个玩具时，它会帮这个玩具上发条，重新补充其能量。虽然Crush Kringle是一个很强大的玩具，但它移动很慢，这意味着玩具必须花很长时间去为它上发条。然而可以通过一个游戏引擎来走捷径，突破这个限制。首先，玩家可以犯下一个只是上了一会发条的Crush Kringle，后面紧跟一个Handy，后面再放一个Crush Kringle，这三个玩具都放在场上的同一行里。移动更快的Handy会推着第一个Crush Kringle，补充其能量。而后Crush Kringle踏地，让Handy的移动方向反过来，往后回到第二个Crush Kringle旁，而后再次为它上发条。第二个Crush Kringle最终会踏地，让Handy回到第一个玩具后面。通过这种方式，这三个玩具能一起在场上向前移动，Handy会不断在两个Crush Kringle间来回往返。

这些玩具组合起来的引擎并不是Gearheads的规则里直接设计好的。它们是由定义了每种玩具的更简单的一套属性所产生的涌现玩法。在某些情况里，玩具的属性会进一步改良来支持特定的引擎，但大多数情况下，引擎都是在游戏不断玩和开发的过程中逐步被发现的。

正如《上帝也疯狂》那样，Gearheads里的涌现也是同时在多个层级上表现的。玩具间没有预料到的局部交互产生了场上更上层的模式。当玩具组合在一起后，玩家会调整他们的行为来利用这种涌现的组合，从而产生了玩家直接的决策制定过程。玩家可以在一场比赛开始前挑选出有限数量的玩具，这鼓励了玩家从涌现的角度去思考：有经验的玩家会挑选4～5个能组成1～2个引擎的玩具。这些引擎进入到游戏开发中的另一个途径是AI编程。在设计玩家的电脑对手时，对手会加入这种基于引擎的探索方法，AI程序会意识到玩具组合的优势，它们往往会用引擎来对抗玩家。一些Gearheads的玩家完全是通过观察AI的行为来学习某些引擎的。

## **二阶设计**

像这样的引擎也会出现在非电子游戏里。类似《魔法风云会》那样的卡牌游戏有着数千种不同的卡牌，完全是涌现的温室，这个游戏是特别为了促成玩家组合出各种卡牌引擎而设计的。在《魔法风云会》或者Gearheads里，利用各种游戏元素的组合能促成丰富的可能性空间。通过把这些元素用在不同的组合里，玩家在游戏过程中塑造出自己的意义。单位的组合和引擎并不是游戏里创造涌现效果的唯一方式，如果你的游戏也有着大量不同的对象，你可以把它们设计成互相能组合在一起，这样你游戏里的可能性空间也会大幅度提升。

要设计出一个涌现的游戏系统，使其能从一套简单的规则里产生出有意义的复杂度，这是很有挑战的。为什么这点如此困难呢？从游戏设计师的角度来说，你是永远无法直接设计你玩家的行为的。你只能去设计系统的规则。由于游戏是涌现的，所以往往不可能预见到规则会在游戏中如何演变。作为游戏设计师，你面对的是一个二阶设计问题。成功游戏设计的目标是有意义的玩乐，但玩乐是从规则的作用过程中产生的。对于游戏设计师的你，你永远无法直接设计玩乐。你只能设计能产生玩乐的各种规则。游戏设计师创造体验，但只能间接地创造它。

在一个复杂的涌现系统里，每种元素都通过它与其他元素可能的交互方式来得到直接的识别。当一种元素改变时，其余的关系也会轮着受到影响。迭代过程的关键在于把游戏看作是系统，分析它们的运作方式，了解游戏的系统是在何时、如何，以及为什么无法产生出有意义玩乐的。每一条规则的调整都会产生游戏玩乐过程的改变，而你永远不能测试出每一条可能的规则变体，乃至不可能测试出其中的一小部分。这就是为什么游戏设计师必须培养的核心技能是预测一个游戏的形式结构里各种改变会如何影响其玩乐的原因。游戏设计师需要持续培养一种“第六感”，了解哪些设计在游戏里是行之有效，哪些是相反的，清楚对系统中一个部分的改变会如何影响到整体的体验。与此同时，你是无法预知每一种效果的。所以当一名游戏设计师的一项最大的快乐在于看到你的游戏在以你从来没预想过的方式展开着，看到玩家探索出你从来不知道其存在的可能性空间中的点点滴滴。理解涌现的运作方式，了解如何创造出能引起涌现的设计，这是能为你带来以上快乐的一种方式。

虽然基于规则的方法不是理解游戏的唯一方法，但它是游戏设计师的概念工具里不可或缺的一部分。通过定义规则并从涌现系统的角度去看游戏，我们为今后从结构性角度去思考游戏奠定了基础。接下来提供的游戏设计图式都会以更具体的方式去从形式系统的角度思考和设计游戏。

## **进阶阅读**

**《Complexification》** ，John Casti

这本谈复杂度的书是数学家John Casti所写的，John Casti是从非技术层面但却很复杂的方式去谈这个主题的。这本书所涉及的物质范围很广，从分形与涌现到奇异吸引子，各种物质应有尽有，书里提供的图灵试验为复杂系统的研究带来了很大的帮助。

推荐章节：

-   Chapter 1: The Simple and the Complex
    
-   Chapter 6: The Emergent
    

**《Emergence: From Chaos to Order》** ，John Holland

John Holland被称为“遗传算法之父”，他是一名数学家兼计算机科学家。虽然书中后面的章节会更偏技术性，但前面的章节为游戏理论和细胞自动机提供了稳固的基础。书中提出的很多问题都是具体对应于游戏规则和游戏AI的。

推荐章节：

-   Chapter 2: Games and Numbers
    
-   Chapter 3: Maps, Game Theory, and Computer-Based Modeling
    

**《Emergence》** ，Stephen Johnson

《Emergence》对涌现系统和复杂度作了很好的介绍，它是电子文化专家Stephen Johnson所写的，这本书提出了多种涌现的现象，包括蚂蚁群落、城市规划、电脑游戏等等。

推荐章节：

-   Chapter 1: The Myth of the Ant Queen
    
-   Chapter 5: Control Artist
    

**《Grammatical Man》** ，Jeremy Campbell

《Grammatical Man》是一本涉及范围很广的记者式的记录，它囊括了复杂度理论、系统理论、信息理论、游戏理论、遗传学，以及科学和工程学相关的领域。作为这些不同领域完整性的补充，这本书是很有价值的资源。

推荐章节：

-   Part One: Establishing the Theory of Information
    
-   Part Two: Nature as an Information Process
    

**《Turtles, Termites, and Traffic Jams》** ，Mitchel Resnick

Mitchel Resnick是Seymour Papert的学生，它是麻省理工学院媒体工作室的一名大学教学人员，他的研究小组负责乐高的头脑风暴项目。《Turtles, Termites, and Traffic Jams》是一本关于分散系统的极为易用的书。书中包含了对该主题的介绍，以及对Resnick在StarLogo的个人工作成果的详细描述。

推荐章节：

-   Chapter 1: Foundations
    

## **总结**

-   当系统能跨越“复杂度障碍”时，系统能达到复杂度的层级。跨越了这个障碍的系统是 **复杂系统** ，它们会表现出各种特殊的行为。
    
-   Christopher Langton指出了四种有着不同复杂程度的系统：
    
    -   **固定系统** 是永远保持不变的，系统中各种元素间的关系永远不会改变。
        
    -   **周期性系统** 是无尽地重复同样模式的简单系统。
        
    -   **复杂系统** 介于周期性系统和混乱系统之间，表现出来的各种行为会比周期性系统的重复性要明显复杂。
        
    -   **混乱系统** 的行为是完全随机的。
        
-   复杂系统是众多复杂且相互关联的元素的结果。但有时候一个复杂系统只包含了数量很少的元素，只是这些元素彼此间的关系错综复杂。
    
-   当一个游戏缺乏复杂度时，它也会缺乏有意义玩乐。当有意义玩乐在一个游戏里呈现时，游戏中某些方面会具有复杂度。复杂度能确保一个游戏的可能性空间足够宽广到能支撑有意义的玩乐。
    
-   **涌现系统** 能通过数量有限的规则产生出无法预知的充满复杂度的行为模式。在涌现系统里，整体大于部分之和。例如，语法里有限的规则是无法说明该语言里可能产生的所有句子的。
    
-   在一个涌现系统里，系统中各种对象的交互是 **互相关联** 且 **依赖于上下文背景** 的。互相关联的交互能影响到该系统的整体空间和模式，因为每种交互会相互联系，而这种联系又会继而影响到其他交互。依赖于上下文背景的交互会在每时每刻根据系统中其他部分当前正在发生的情况来发生改变，创造出随时间动态改变的模式。
    
-   一个涌现系统里的 **自底向上** 行为是指该系统的局部规则所产生的涌现交互会在整个系统里扩散开来，塑造出全局的模式。例如，“The Game of Life”是一个自底向上的系统，它产生了诸如Glider guns那样的现象，而这种现象是没有在系统规则中明确描述的，它们是其简单规则自底向上生效时所产生的模式。
    
-   游戏中从形式系统里产生的涌现是靠玩家来利用的。例如扑克中的虚张声势是游戏规则中没有明确陈述的，但它是从游戏中出现的玩家行为模式。
    
-   一个游戏中出现的涌现往往是不能从规则里一眼就看出来的。围棋有着比国际象棋更简单的规则，但由于涌现的影响，这个游戏在数学上有着更多的排列组合。
    
-   如果一个游戏是涌现的，那它就会有着足够宽广的可能性空间，这个空间能激励玩家去探索所有可能的玩法。例如，在那些有着不同类型的单位和对象的游戏里，玩家能把单位用难以预料的方式组合成各种 **引擎** 。设计出能支撑这些不同种类引擎的游戏，能在游戏里产生丰富的涌现，提升游戏的可能性空间。
    
-   **游戏设计是一个二阶设计问题。** 游戏设计师能直接地设计游戏规则，但只能间接地设计玩家的体验。基于系统去理解游戏是如何运作的，这能极大提升游戏设计师的预知能力，让他们能预知到游戏规则中的一点点改变会如何影响整个游戏的玩乐体验。
    

```Plaintext
[1] Jeremy Campbell, Grammatical Man: Information, Entropy, Language, and Life (New York: Simon & Schuster, 1982), p. 105.
[2] Ibid, p. 102.
[3] John Casti, Complexification: Explaining a Paradoxical World Through the Science of Surprise (New York: HarperCollins Publishers, 1994), p. 40-41.
[4] Christopher Langton, Artificial Life: An Overview (Cambridge: MIT Press, 1995), p. 112.
[5] John Holland, Emergence (Reading, PA: Helix Books, 1998), p. 121–122.
[6] Langton, Artificial Life, p. 52.
[7] Steven Johnson, Emergence: The Connected Lives of Ants, Brains, Cities, and Software (New York: Scribner, 2001), p. 18.
[8] Holland, Emergence, p. 22–23.
[9] Andrew Rollings and Dave Morris, Game Architecture and Design (Scottsdale: Coriolis Group, 1999), p. 26.
```

[](https://zhuanlan.zhihu.com/p/592860859)

  

编辑于 2022-12-29 13:41 ・IP 属地上海