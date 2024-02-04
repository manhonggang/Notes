作者：Patrick Wyatt

在PC游戏运行于DOS操作系统的时代，我开始效力于一款名为《魔兽争霸》的游戏项目。（请点击此处阅读本文[第2部分](http://gamerboom.com/archives/78466)）

**我成了项目主管**

虽然我已经开发过数款PC游戏，一系列Mac游戏，以及7款针对超级任天堂和世嘉五代的主机游戏，但我在这些项目中所扮演的不过是新人角色，或者说只是开发其中一些原作的移植版本。游戏移植就是将游戏从一个平台发布到另一个平台的过程，其中包括转换代码、设计、美工和其他游戏资产，以便原先运行于Amiga的游戏也能够运行于任天堂设备。

我的角色包含两项工作：负责领导团队的“制作人”——游戏行业中所谓的项目主管、设计师、布道者、典狱长的头衔；以及负责编写大部分游戏代码的“主程序员”。这可能没有那么可怕，因为一个游戏项目可能招聘10个20个开发者，开发团队最大规模时至少可达到200名开发者。

[![Patrick Wyatt(from games.sina)](http://gamerboom.com/wp-content/uploads/2013/11/Patrick-Wyattfrom-games.sina_.jpg "Patrick Wyatt(from games.sina)")](http://gamerboom.com/wp-content/uploads/2013/11/Patrick-Wyattfrom-games.sina_.jpg)

Patrick Wyatt(from games.sina)

**《魔兽争霸》起源**

我曾就职的初创公司当时名为Silicon & Synapse，之后更名为暴雪，以对应我们暴风雨般猛烈的开发方法——在闲暇时间玩大量游戏，《魔兽争霸》的灵感正是发源于这种活动。

我们玩过（反复重玩）一款名为《Dune 2》（Westwood Studios）的游戏后受到启发而创造了《魔兽争霸》。《Dune 2》是首款现代意义上的即时战略游戏（RTS），拥有横向卷轴世界地图，即时单位建设和移动，以及独立单位战斗等元素。除了一些比例和图像质量之外，它在设计上与《星际争霸2》等现代即时战略游戏并没有很大区别。

其前作《Dune 1》也采用了一些相同元素，但其半即时单位战争元素则隐藏在了冒险游戏中。《Dune 2》除去了前作中让玩家作为游戏角色之一参与其中的理念，其关注重点是现代RTS机制：收割庄稼，收集更多资源，建设军队，最后找到并征服敌人。

和暴雪团队中的其他人一样，我也在午餐时间专门玩《Dune 2》，其中的三个种族都玩遍了，确定了它们各自的强项与弱点，之后再与同事比较玩法风格、策略和战术。

[![Dune2(from rtsguru.com)](http://gamerboom.com/wp-content/uploads/2013/11/Dune2from-rtsguru.com_.jpg "Dune2(from rtsguru.com)")](http://gamerboom.com/wp-content/uploads/2013/11/Dune2from-rtsguru.com_.jpg)

Dune2(from rtsguru.com)

虽然这款游戏非常有趣，但也存在一些明显有待修复的瑕疵。最值得一提的是，我和好友只能同电脑对抗。而这款游戏的理想选择显然是多人模式。与需要每位玩家等待所有对手完成单位移动指令的回合制游戏不同的是，即时战略游戏允许所有玩家同时发出指令，执行快速、决定性的战略移动，而非冗长持久的战略性计划。

脑中有了这个目标之后，游戏开发就无需在游戏设计、技术需求评估、安排日程表或所需人员预算上大费周章。在暴雪我们将此称为“特供商业计划”，也就是标准操作方法。

**初始开发**

作为项目唯一的开发者，在初始阶段没有美术团队，我就先截取《Dune 2》的美术资产来用，直到项目进展不得不需要一两名美术人员时。这些美术人员可以一起赶其他临近截止日期的项目，此时不可以分心，我们一直是时间紧迫。

我早期开发游戏引擎时要做的事情包括创造基于贴图的横向卷轴地图渲染器，绘制游戏单位和其他位图的精灵渲染器，分配鼠标和键盘事件的事件调度器，以及控制应用行为的大量用户界面代码。在最初几周完成这些项目子集后，我们就能够“试玩”一款游戏，尽管我当时还没有植入单位建设元素。早期试玩需要使用输入指令以便屏幕生成单位。

我每天都要以有序的方式在之前的基础上创造内容。由于没有时间表及项目的外部催促因素，我有幸能够自主选择接下去要创造什么功能，这让我觉得动力十足。我原本就很喜欢游戏开发过程，就像嗑药上瘾一样忘我地编程。即使是现在，我已经进入这一行22年了，我还是很喜欢编程中的创意。

**首个独特功能：多单位选择**

我最为骄傲的一个功能就是单位选择。与只允许用户一次仅选择一个单位的《Dune 2》不同，我设计的这项功能允许用户一次选择一大遍的战斗单位，很显然这种功能要以加速玩家的任务调度，极大提升游戏战斗力。

我进入游戏行业之前曾使用一些低端的“计算机辅助设计”（CAD）程序，例如MacDraw和MacDraft，为我爸的公司设计酒窖，所以对于“拖拽”一系列单位的操作得心应对。

我相信《魔曾争霸》是首款使用这种用户界面的游戏。当我第一次部署这种功能时，就可以同时选择和控制大量单位，这里不存在选择的单位数量限制。

而一次性选择和控制100个单位则暴露了我所部署的简单寻径算法的弱点，我完成了基本算法后，就投入大量时间选择单位，并向目的地分配游戏单位，而不是编写更多代码。这是我的编程生涯中最酷的功能！

在之后的开发过程中，我们根据团队成员的许多设计主张，决定允许玩家一次只选择4个单位，因为用户需要关注自己的战略部署，而不只是集结一帮人将其全部发往一场混战。我们在之后的《魔兽争霸2》中将此数目增加到了9个。继承了《Dune 2》的《命令与征服》并没有单位选择数量的上限。但这是另一个题外话了。

除了一次可以控制多个单位之外，这个阶段的《魔兽争霸》完全不像是降级版的《Dune 2》，我甚至开玩笑说，虽然这款游戏脱胎于《Dune 2》，但实际上与其完全不同——我们的雷达迷你地图位于屏幕左上角，而后者则处于右下角。

**团队构成**

在1994年初，我在为该项目获得更多支持方面取得了进展。Ron Millar、Sam Didier、Stu Rose、Bob Fitch、Jesse McReynolds、Mike Morhaime、Mickey Nielsen等人也入伙了。他们当中多数人是在我们公司在1994年2月被Davidson & Associates收购时参与到这款游戏中。

Ron Millar这位金发壮汉很显然是维京战士的后裔。他最初曾在Virgin Games为Gameboy作品制作美术内容，但杰出的创意和设计感令他在暴雪多个项目中担任设计师，在《魔兽争霸》中他也担任同样职位。

Sam Didier是一个矮壮的角色，好像是一只缩小成人类比例的熊，其英雄主义的个性和史诗般的绘画作品奠定了暴雪游戏的美术风格，曾经为16位主机游戏绘制美术资产，在会议期间和其他闲暇时间都可以露几手绘画才能，并因此负责这款游戏的美术设计方向。

Stu Rose原先是插画师，暴雪运用至今的logo就是出自其手——他最初负责绘制游戏的背景贴图美术，但在游戏最终设计时扮演了更重要的角色。Stu十分还是个令人难忘的配音演员，他的喜剧天份令其成功演绎了受尽压迫和苦役的“人类农民”。

Bob Fitch原先是程序员，在我开始展开《魔兽争霸》时他还是另一款游戏的项目主管。Allen Adham是暴雪总裁，曾向Bob分配了开发一款文字游戏“Games People Play”（包含填字谜、scramble、bloggle等多项元素）的任务，但Bob对该项目缺乏热情导致数月毫无进展，看到《魔兽争霸》的情况之后，Bob就过来协助我，他对这款游戏的热情推动了这款游戏的快速进展。

Jesse是加利福尼亚理工学院毕业生，原先是为IPX网络协议创建网络驱动程序，以便游戏能够运行于本地局域网（LAN）。Mike Morhaime是暴雪两名创始人之一，之后接手了更困难的任务，即编写“混合模式”的调制解调器驱动器。虽然《魔兽争霸》是一款DOS“保护模式”游戏，调制解调器驱动器通常来源于保护模式和实时模式，原因是DOS操作系统及其运行的80386芯片构造的变化无常，所以我们经常可以发现他坐在办公室盯着满屏诊断数据，因为他得解决与重新进入代码的复杂时间问题。最后的调制解调器代码稳若盘石，很大程度上要归功于我们当时使用的原始工具组。

**《魔兽争霸》的美术设计**

[![Warcraft_orcs_and_humans(from wikipedia.org)](http://gamerboom.com/wp-content/uploads/2013/11/Warcraft_orcs_and_humansfrom-wikipedia.org_.jpg "Warcraft_orcs_and_humans(from wikipedia.org)")](http://gamerboom.com/wp-content/uploads/2013/11/Warcraft_orcs_and_humansfrom-wikipedia.org_.jpg)

Warcraft\_orcs\_and\_humans(from wikipedia.org)

Allen Adham希望获得《战锤》的授权，以便通过品牌辨识度而增加游戏销量。《战锤》是《魔兽争霸》美术风格的一个巨大灵感来源，但结合了多项元素，包括开发团队中几乎每个人都缺乏商业概念，以及捍卫自己的游戏世界的空前热情。我们已经受够了与DC Comics合作开发“Death and Return of Superman”以及“Justice League Task Force”的糟糕经历，希望自己的新游戏不要重蹈覆辙。

现在很难想象，如果当时暴雪没有控制《魔兽争霸》的知识产权（IP）该会是什么结果——很可能暴雪就不会是当今游戏领域的霸主了。

在《魔兽争霸》发布数年之后，我爸从亚洲回来了，给我带来了一系列《战锤》的微缩角色模型：“我在旅途中发现了这些有趣的玩具，这让我想起了你的许多游戏，你们也可以找法律团队联系他们，因为我认为他们剽窃了你们的创意。”

**游戏开发中的障碍**

早期开发过程中的一个有趣方面就是，虽然我创造了一款可以使用调制解调器或本地局域网运行的游戏，但我们公司办公室却并没有LAN。因为我们开发的是主机游戏，也就是可以插入软盘来玩的游戏，当时还没的配图LAN的必要，虽然这可以简化制作备份的过程。

所以当我开始同其他美术人员和程序员合作时，我们使用了“sneaker网络”，让软盘在几个办公室之间流通，以便整合源代码修订和美术资产。

Bob Fitch是项目的第二个程序员，我和他经常复制文件和反复更改代码。我们间歇性地出现一些整合错误，我们修复的漏洞也会再次出现。我们在复制文件时追踪并发现了这一点——我们偶然重写了漏洞修复，我们就不得不加快之前是如何修复漏洞的。

由于我们开发代码速度很快，并且缺乏管理代码整合流程（只“记得”自己制作了哪些文件），这种情况一再发生。在这方面我比较幸运一点，因为我的电脑是我们执行所有调合过程中最“大师”级别的系统，所以我的调整很少丢失。现在我们使用了源控制以免再出现这类事情，但当时我们确实不知道究竟发生了啥情况。

有了更多程序员、设计师和美术人员，我们的开发过程进展明显，但我们还是发现了这个过程中的一大障碍。这款游戏最初是在DOS的“实时模式”中开发的，这意味着它只有640K的内存可用，比操作系统少120K。你可以想象当时的电脑有多蹩脚吗？

由于美术团队开始制作游戏单位，背景和用户界面的美术内容，我们的内存很快就用完了，不得不寻找其他替代方案。第一个尝试方法是使用EMS“分页内存”，保存超过640K内存上限的美术资源。

程序员讲起EMS内存那副苦大仇深的样子，好比是老一辈人讲述赤脚爬山去上学那种辛酸史，EMS实际上是一种更可怕的经历。

EMS解决方案实际上并不管用，实际上还有更好的方法。有家名为Watcom的公司推出了C编译器，其中包含一种允许程序以“保护模式”编写，可以访问线性32位内存的DOS模式“扩充器”，这是今天的程序员32位（甚至是64位应用）都会用到的工具。虽然它需要两天时间来更新源代码，但DOS模式扩充器真是完美，当我们重返正轨时，就可以获得更多可用内存了。

**小结**

在本系列的下一篇文章中，我将分享Stu Rose以及设计绝招，《魔兽争霸》首个多人游戏，几乎扼杀多人模式的漏洞，Bill Roper如何令游戏适用于软盘，Westwood Studio对我们这款游戏的反应，以及我所能回忆起来的关于这款游戏18年前的开发团队成员的其他趣事等内容。

原文发表于2012年7月25日，所涉事件及数据以当时为准。（本文为游戏邦/gamerboom.com编译，拒绝任何不保留版权的转载，如需转载请联系：游戏邦）

The making of Warcraft part 1

July 25, 2012 by Patrick Wyatt

Back before the dawn of time, which is to say when PC games were written for the DOS operating system, I got to work on a game called Warcraft.

I get to lead a project!

While I had developed several PC games, a couple of Mac games, and seven console titles for the Super Nintendo and Sega Genesis, I was either in a junior role on those projects, or the projects were game “ports” rather than original development work. A game “port” is the process of moving a game from one platform, like the Amiga, and converting the code, design, artwork and other game assets to make them work on another, like the Nintendo.

My role encompassed two jobs: leading the development team as Producer — a game industry term for project manager, designer, evangelist, and cat herder — and writing the majority of the game code as Lead Programmer. This was perhaps less daunting then, when a game project might employ ten or twenty developers, than it is now, with development teams tipping the scales at two-hundred or more developers.

The source of Warcraft

The developers at the startup company I worked for — then named Silicon & Synapse but later renamed Blizzard in a nod towards our tempestuous development methodology — played a great many games during our free time. And from that game-playing came the spark to create Warcraft.

We were inspired to create Warcraft after playing (and replaying and replaying) a game called Dune 2, by Westwood Studios. Dune 2 was arguably the first modern real-time strategy (RTS) game; with a scrolling world map, real-time unit construction and movement, and individual unit combat. It isn’t that much different in design than a modern RTS like Starcraft 2, excepting perhaps a certain scale and graphics quality.

Its predecessor, Dune 1 — a very worthy game itself — shared some of the same elements, but its semi-real-time unit combat was wrapped inside an adventure game. Dune 2 stripped its predecessors’ idea of the player representing a character inside the game-world and focused exclusively on the modern RTS mechanics: harvesting resources, building a base, harvesting more resources, building an army, and finally, finding and conquering the enemy.

Along with the other folks at Blizzard I exhaustively played Dune 2 during lunch breaks and after work, playing each of the three competing races to determine their strengths and weaknesses; and afterward comparing play-styles, strategies and tactics with others in the office.

While the game was great fun, it suffered from several obvious defects that called out (nay, screamed) to be fixed. Most notably, the only way that my friends and I could play the game was against the computer. It was obvious that this gaming style would be ideal as a multiplayer game. Unlike turn-based games, where each player must wait for all opponents to issue unit movement orders, a real-time game would enable all players to give orders simultaneously, placing a premium on rapid, decisive tactical movements over long, drawn-out strategic planning.

And with that singular goal in mind, development of the game began without any serious effort to plan the game design, evaluate the technical requirements, build the schedule, or budget for the required staff. Not even on a napkin. Back at Blizzard we called this the “business plan du jour”, which was or standard operating methodology.

Initial development

As the sole developer on the project, and lacking an art team during the initial phase, I screen-captured the artwork of Dune 2 to use until such time as my forward progress warranted an artist or two. The artists were tied up working on any number of other pressing deadlines and didn’t need distractions at this point — we were always pressed for time.

My early programming efforts developing the game engine included creating a tile-based scrolling map renderer, a sprite renderer to draw game units and other bitmaps, a sprite-sequencing engine to animate game units, an event-dispatcher to post mouse and keyboard events, a game-dispatcher to control unit-behavior, and a great deal of user-interface code to control application behavior. With this subset of the project completed in the first few weeks it became possible to “play” a solo game, though I didn’t implement unit-construction until sometime later; early play required using typed commands to spawn units on screen.

Each day I’d build upon the previous efforts in organic fashion. Without schedule milestones or an external driver for the project, I was in the enviable position of choosing which features to build next, which made me incredibly motivated. I already enjoyed game development, and getting to do this green-field programming was like a drug. Even now, some 22 years after getting into the game industry, I still love the creative aspects of programming.

The first unique feature: multi-unit selection

One feature of which I was particularly proud was unit-selection. Unlike Dune 2, which only allowed the user to select a single unit at a time, and which necessitated frenzied mouse-clicking to initiate joint-unit tactical combat, it was obvious that enabling players to select more than one unit would speed task-force deployment and dramatically improve game combat.

Before I started in the game industry I had worked extensively with several low-end “Computer Assisted Design” (CAD) programs like MacDraw and MacDraft to design wine-cellars for my dad’s wine cellar business, so it seemed natural to use the “click & drag” rectangle-selection metaphor to round up a group of units to command.

I believe that Warcraft was the first game to use this user-interface metaphor. When I first implemented the feature it was possible to select and control large numbers of units at a time; there was no upper limit on the number of units that could be selected.

While selecting and controlling one hundred units at a time demonstrated terrible weaknesses in the simple path-finding algorithm I had implemented, after I got the basic algorithms working I nevertheless spent hours selecting units and dispatching game units to destinations around the map instead of writing more code; it was the coolest feature I had ever created in my programming career up to that time!

Later in the development process, and after many design arguments between team-members, we decided to allow players to select only four units at a time based on the idea that users would be required to pay attention to their tactical deployments rather than simply gathering a mob and sending them into the fray all at once. We later increased this number to nine in Warcraft II. Command and Conquer, the spiritual successor to Dune 2, didn’t have any upper bound on the number of units that could be selected. It’s worth another article to talk about the design ramifications, for sure.

Apart from the ability to control multiple units at one time, at this phase Warcraft resembled nothing so much as a stripped-down version of Dune 2, so much so that I defensively joked that, while Warcraft was certainly inspired by Dune 2, the game was radically different — our radar minimap was in the upper-left corner of the screen, whereas theirs was in the lower-right corner.

The formation of the fellowship

By early 1994, I had made enough progress to warrant additional help on the project. I was joined by Ron Millar, Sam Didier, Stu Rose, Bob Fitch, Jesse McReynolds, Mike Morhaime, Mickey Nielsen, and others. Many of these folks started work on the game after our company was acquired by Davidson & Associates in February 1994.

Ron Millar, who, with his long blond hair and strong build, was obviously the progeny of Viking warriors. He was originally hired on as an artist based on his skill in creating artwork for Gameboy titles at Virgin Games, but his amazing creativity and design sensibilities led to his taking on a design role in many Blizzard projects, and he stepped into a similar role for Warcraft.

Sam Didier, a strong, stocky and stalwart character who resembled nothing so much as a bear scaled down to human proportions, and whose heroic characters and epic drawings are now the definitive art style for Blizzard games, had honed his computer drawing skills on sixteen-bit console titles, but his penchant for drawing fantasy artwork during meetings and at any other spare moment demonstrated his capability to lead the art direction for this new title.

Stu Rose — whose background as an illustrator led to his design of the Blizzard logo still used today — initially contributed to the background tile-map artwork, but he would later take on a critical role in the ultimate design of Warcraft. Stu is quite memorable as a voice actor in the role of Human Peon Peasant, where his rendition of a downtrodden brute-laborer was comedic genius.

Bob Fitch had started work as a programmer and project lead on another title at the same time I started development of Warcraft. Allen Adham, the president of Blizzard, had assigned Bob the task of building a word game called “Games People Play” that would include crossword, scramble, boggle, and other similar diversions. Bob’s notable lack of enthusiasm for the project resulted in his making little progress on the title for many months; with Warcraft showing well Bob was released to assist me, and his enthusiasm for the game helped move the project forward more rapidly.

Jesse, a Caltech graduate, started work on building a network driver for the IPX network protocol so the game could be played on a Local Area Network (LAN). Mike Morhaime, one of the two co-founders of Blizzard, later took on the significantly more difficult task of writing a “mixed-mode” modem driver. While Warcraft was a DOS “Protected Mode” game, the modem driver could be called from both Protected Mode and Real Mode due to quirks in the DOS operating system and the 80386 chip-architecture it ran on, so he could regularly be found in his office staring at screens full of diagnostic numbers as he worked through the complicated timing issues related to re-entrant code. At the end of the day, the modem code was rock-solid, quite an achievement given the primitive toolset we had at the time.

Warcraft art

Allen Adham hoped to obtain a license to the Warhammer universe to try to increase sales by brand recognition. Warhammer was a huge inspiration for the art-style of Warcraft, but a combination of factors, including a lack of traction on business terms and a fervent desire on the part of virtually everyone else on the development team (myself included) to control our own universe nixed any potential for a deal. We had already had terrible experiences working with DC Comics on “Death and Return of Superman” and “Justice League Task Force”, and wanted no similar issues for our new game.

It’s surprising now to think what might have happened had Blizzard not controlled the intellectual property rights for the Warcraft universe — it’s highly unlikely Blizzard would be such a dominant player in the game industry today.

Years after the launch of Warcraft my dad, upon returning from a trip to Asia, gave me a present of a set of Warhammer miniatures in the form of a skeleton charioteer and horses with the comment:

“I found these cool toys on my trip and they reminded me a lot of your game; you might want to have your legal department contact them because I think they’re ripping you off.” Hmmm!

Blockers to game development

One interesting facet of the early development process was that, while I was building a game that would be playable using modems or a local area network, the company had no office LAN. Because we developed console titles, which would easily fit on a floppy disk, it wasn’t something that was necessary, though it would certainly have simplified making backups.

So when I started collaborating with other artists and programmers, we used the “sneaker network”, carrying floppy disks back and forth between offices to integrate source code revisions and artwork.

Bob Fitch was the second programmer on the project, and he and I would regularly copy files and code-changes back and forth. Periodically we’d make integration mistakes and a bug we fixed would re-appear. We’d track it down and discover that — during file-copying while integrating changes — we had accidentally overwritten the bug fix, and we’d have to remember how we had fixed it previously.

This happened more than a few times because of the rapidity with which we developed code and our lack of any processes to handle code-integration other than “remembering” which files we had worked on. I was somewhat luckier in this regard in that my computer was the “master” system upon which we performed all the integrations, so my changes were less likely to get lost. These days we use source-control to avoid such stupidities, but back then we didn’t even know what it was!

With more programmers, designers and artists working on the title progress increased substantially, but we also discovered a big blocker to our progress. The game was initially developed in DOS “Real Mode”, which meant that only 640K of memory was available, less about 120K for the operating system. Can you believe how crap computers were back then!?!

As the art team started creating game units, backgrounds and user-interface artwork, we rapidly burned through all of the memory and started looking for alternatives. A first attempt at a solution was to use EMS “paged memory” mapping and store art resources “above” the 640K memory barrier.

Stories programmers tell about EMS memory are like those that old folks tell about walking uphill to school, barefoot, in the snow, both ways, except that EMS stories are even more horrible, and actually true.

In any event the EMS solution quite fortunately didn’t work; it turned out there was a better solution. A company called Watcom released a C compiler which included a DOS-mode “extender” that allowed programs to be written in “Protected Mode” with access to linear 32-bit memory, something every programmer takes for granted today when they write 32-bit (or even 64-bit applications).

While it required a couple of days to update the source code, the DOS-mode extender worked perfectly, and we were back in business, now with access to substantially more memory.

Not the conclusion

In the next article in this series I’ll talk about Stu Rose and the design coup, the first multiplayer game of Warcraft, the bug that nearly killed multiplayer, how Bill Roper made Warcraft awesome, fitting the game onto floppy disks, the Westwood Studio reaction to our game, and other gems I can dredge up from a game that I and the other members of the development team worked on eighteen (!) years ago.（source：[codeofhonor](http://www.codeofhonor.com/blog/the-making-of-warcraft-part-1)）