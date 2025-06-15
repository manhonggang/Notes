「 点击上方"GameLook"↑↑↑，订阅微信 」

由Second Dinner研发、朝夕光年发行的《Marvel Snap》是去年年底最大的手游爆款，它不仅拿到了TGA年度最佳手游，首月流水破千万美元，还在随后持续增长，目前月流水稳定破亿。更为难得的是，作为一款卡牌手游，《Marvel Snap》主动限制氪金的设计，还得到了大量玩家的好评。

如果说《炉石传说》开辟了数字CCG品类，那么《Marvel Snap》则通过三分钟战斗、位置和直接从西洋双陆棋中借鉴的加倍骰子（doubling cube），将这个品类带向了全新方向。作为Second Dinner工作室的首席研发官，Ben Brode在《炉石传说》项目组十年的工作经验里学到了很多，在从事《Marvel Snap》项目五年的时间里积累了更多的经验。

在GDC 2023演讲中，他剖析了设计这个爆款卡牌游戏的点点滴滴，讲述了项目研发当中不为人知的故事。

以下是Gamelook听译的完整内容：

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/LnV8UVj5ORVOte6Dcy1ZjC4iasHxTzlVpWrv2QBXYNTUjiaLGicGAmnYO2xMUfboJIicxwUFicJmMUoOpK0po1PBeGg/640?wx_fmt=jpeg&wxfrom=5&wx_lazy=1&wx_co=1)

**Ben Brode：**

我是Second Dinner工作室首席研发官Ben Brode，我们过去五年的时间都在做《Marvel Snap》，在此之前，我在暴雪工作了15年，主要是为《魔兽争霸3》、《魔兽世界》和《暗黑破坏神2》做QA和一些其他事情。但是，我在暴雪大部分的时间是从事《炉石传说》项目，我是那款游戏的第一个策划，最后担任了游戏总监，我在YouTube也有成功的说唱经历，但大部分人都不知道。

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/LnV8UVj5ORVOte6Dcy1ZjC4iasHxTzlVpphJa11AsXOMRIcfE8DIDpDbbaYfmLGicEGPJ78QPiaekCrM6UDibP8x3Q/640?wx_fmt=jpeg&wxfrom=5&wx_lazy=1&wx_co=1)

今天主要分享的是，我们如何设计出了《Marvel Snap》，它的研发用了四年多一点，接下来我会谈到我们尝试过的所有事情、奏效的方法、无效的东西，以及我从这个过程中学到的一切，其中大部分都是与《Marvel Snap》的核心玩法有关。

我不会列内容框架，而是向你们展示今天分享的所有图片：

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/LnV8UVj5ORVOte6Dcy1ZjC4iasHxTzlVphkuicDMEapSr8gCp8cm8cNvV9fNW77G4Bhe4ZCpQ8ol2wclRcQ6BYvQ/640?wx_fmt=jpeg&wxfrom=5&wx_lazy=1&wx_co=1)

可以看到，没有可爱的猫咪照片，所以不要有太高的预期。《Marvel Snap》是一款移动平台优先的超快节奏数字卡牌手游，玩家们通过玩卡牌的方式彼此竞争三个地点中的两个。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

我们将所有的卡牌都做成了3D形式，不过更重要的是我们做了酷炫的骰子。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

**灵感来源**

游戏策划就像是大厨，大部分时候，我们并不发明任何新原料，我们总是用已经有的配料，并且以新的、令人兴奋的方式将它们组合起来。比如，你给两个大厨同样的配料：鲜花、水、西红柿、罗勒、奶酪，他们一个人可能做出披萨，另一个人可能做出意面。但意面大厨不会找到披萨大厨，说“我发明了鲜花，你盗窃了我对鲜花的创意”。

这与发明新配料无关，主要是我们如何混合这些配料。有些时候，人们会发现以令人兴奋的方式混合旧配料，比如我在网上看到有个人做了一个罗勒西红柿奶酪蛋糕：

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

所以，作为游戏粉丝，我们在玩游戏的时候很自然地收集配料，不过，我想说的是，在开始新项目的时候如何以不同的方式处理配料收集。

我们要说的是《Marvel Snap》，但我们在《炉石传说》项目学到的经验或者一些教训带来了很大的帮助。所以，这里我会说一些《炉石传说》的故事，这要从15年前我第一次逛超市开始：

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

15年前，我们开始从事《炉石传说》的研发，那时候App Store还不存在、iPad还没有公布，2008年的时候，人们讨论移动游戏，往往说的是GameBoy游戏。所以，当我加入《炉石传说》团队之后，所做的第一件事就是玩遍了所有的数字卡牌收集游戏品类。

在玩这些游戏的时候，我学到了很多，有些时候我发现了一些想要尝试的新配料，有时候只是发现了一些不喜欢的东西（洋葱），但这仍然是有帮助的。比如，假设没有这些体验，我可能不会知道自己不喜欢卡牌收集游戏里的网格卡牌战斗系统，玩别人的游戏学习教训实际上成本要比自己做游戏低很多。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

不过，尽管在2008年有不少数字卡牌游戏，但《炉石传说》大部分的灵感实际上来自实体卡牌游戏。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这是《炉石传说》核心玩法的“配方”：我们从TCG卡牌借鉴了很多元素，比如卡牌类型、直接攻击、Sticky Damage、获胜条件，以及一个来自《Battle Spirits》里的很重要的元素，也就是法力水晶系统。当然，我们也做了很多的创新，比如英雄能量、无响应、武器持续时间、疲劳、低复杂度。

所以，我问了《Battle Spirits》的策划Mike Elliott，问他是如何为游戏得到新想法的，因为他设计了数百个卡牌桌游，而我却没有设计数百款游戏，因此我决定向他问策。他说，所有的游戏想法都来自游戏大会，只是在游戏展台浏览，看到所有人展示自己从事的新事物，得到了很多的想法，当离开游戏大会的时候就能获得12个新游戏想法。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这就像是一个充满了配料的超市，这其实是我2008还是2009年参加Gen Con的照片，在这里我发现了《Battle Spirits》，后者成为了《炉石传说》很重要的灵感来源之一。所以，我用了Mike的技巧去发现并通过他的游戏得到了灵感。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

我是在《炉石传说》2014年发布前的六年就开始加入了团队，但却错过了游戏的发布派对，因为当天我的儿子出生了。当时还没有发布移动版本，但我的手机上当时有一个特别版本，而且我在抱儿子玩的时候用另一只手在手机上玩了很久的《炉石传说》。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这改变了我玩游戏的方式，在此之前，我可能坐在电脑前玩四个小时的游戏，然后可以在逛公园或者去洗手间的时候接着玩。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

几年之后，《皇室战争》发布了，我对这款游戏非常羡慕，如果你只有五分钟的时间，那么你100%会选择一款《皇室战争》这样的游戏，我觉得这款游戏非常成功。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

五年前，我和Hamilton（Chu），他是《炉石传说》的EP（执行制作人）、也是Second Dinner工作室的CEO，我们决定组建一个新公司、打造一些新东西。当时甚至不知道要做一款卡牌手游，不过，决定了之后，我开始体验能够找到的每一款数字卡牌手游。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这些是我在2018年玩的手游，左侧的《卡牌怪兽（Card Monsters）》是一款3分钟一局的轻度快节奏对战手游。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

那么，《Marvel Snap》的成功配方是什么？这张图片是我故意放出来吸引你们来到这里的。

**创意原型**

我们脑海中有了很多的配料，所以，是时候开始做创意原型了。

这是《Marvel Snap》第一个创意原型开起来的样子：

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

我认真的！我们当时坐在沙发上对游戏想法进行头脑风暴，Hamilton说他一直想玩一款带有西洋双陆棋加倍骰子的回合制策略游戏。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

所以，我打开了《炉石传说》，游戏里每个回合Hamilton都说是否要做个加倍骰子，我们什么都没有做就立即感受到了这个机制的影响力，通过初始玩法测试，我们意识到了这个机制的一些东西。

它增加了情绪范围，而不是之前每次游戏得到一颗星的方式，我们失败的时间更少。传统意义上，如果一款游戏的胜率只有5%，你要失败很多次才能赢，这是很残酷的，就像是《Monopoly》的最后六个小时。另外，游戏时间会更快。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

但我觉得有两件事的影响很大，这里我会详细说明。首先，零和博弈相当于毫无乐趣。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

如果两个玩家玩游戏，其中一个获胜，另一个失败，那么，获胜的乐趣和失败的无趣一样多，也就是说，你没有创造一点净喜悦，你只是将快乐从一个人的身上转移到了另一个人身上。

所以，我们努力避免这种情况，有很多方法可以解决这个问题。第一个方法就是机器人，这也是避免零和博弈最简单的方法，因为你获得了胜利的喜悦，而没有人遭受失败的痛苦。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

我很喜欢《PUBG MOBILE》，第一次玩的时候就拿到了第一名，之后的第二次游戏也顺利吃鸡，我觉得自己的游戏技术可能又回来了！所以，我把这个截图分享到了社交媒体上，然后很多朋友评论说，“伙计，前两局游戏里，你的对手都是机器人”。我觉得很尴尬，并且删掉了帖子。

不过，如果他们不告诉我这件事，我本来可以享受没有任何挫折的胜利喜悦。

在2014年的GDC上，我的导师、《炉石传说》最初的游戏总监Eric Dodds谈到了《炉石传说》的设计价值，他提到了小胜利（little victories）的概念。大的胜利，是你赢得了游戏，而小胜利则指的是在游戏过程中，那些让你觉得自己聪明或者强大的事情。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

比如在《CS》里，你一出来就被爆头，就不会感受到任何聪明或者强大的感觉，但是，如果你消灭了敌方成员但仍然失败了，那么你依然会觉得自己的表现不错，这就是小胜利。本质上来说，这些小胜利为你带来了一点喜悦，哪怕你输掉了游戏。

所以，在《炉石传说》里，我们避开了封锁敌人法力水晶或者迫使对手放弃卡牌的卡，因为它们可以创造出让你觉得不再强大的场景。在《Marvel Snap》当中有六个回合，每个回合你都需要做一些事情，让你觉得自己有些强大。

不过，骰子对于零和博弈有最大的影响。我们发现，当你的对手获胜时，你可以像这样撤退，有些情况下它让失败给人的感觉像是获胜了一样，让你觉得这只是战略撤退，让你觉得你并没有输，你只是逃出生天了，你简直是个天才。同样，我们也不会在玩家失败的时候增加一个声音说，“你输了”，这是我们试图避免的事情。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

骰子对于零和博弈最大的改变，在于其深度。我们经常说，扑克是一款从来不需要拓展的游戏，但它同样能够数十年都保持战略深度，主要是因为下注和虚张声势（Betting and Bluffing）机制。所以，《炉石传说》加上加倍骰子，就是所有的游戏深度加上了下注和虚张声势的深度。

我们当时在想，该如何降低这个品类的复杂度、并依赖加倍骰子做出深度？所以，我们决定做一款可以让我们使用加倍骰子的最简单的卡牌游戏。我很喜欢简单但同时有很多深度的游戏，很多人谈到过这两个词汇， 但我这里要说的是，复杂度是你在玩游戏之前就要付出的成本，你先要学会怎么玩游戏。而深度则是你得到的乐趣，是这些有趣的决策。

在发布《炉石传说》之后，我们在Metacritic网站得到过这样一个评价：“儿童版卡牌游戏”，这是游戏发布之初的评价，我觉得是因为人们误解了复杂度和深度的关系。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

很多玩家都想要有深度的游戏，的确，你必须增加一些复杂度才能创造游戏深度。但很多人看到带有大量复杂度的游戏，就认为它一定会很有深度。但是，有时候你增加的复杂度，并不会带来任何深度。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

比如，我们增加一个规则：每次你在《Marvel Snap》出一张卡，都必须在麦克风喊出卡牌的名字，否则你就输。这是个重要的规则，你必须学习，但它并不能为游戏增加任何有趣的深度。

另一方面，有些复杂度会带来大量的深度，我们常把通过很小的宏观复杂度带来很多深度的机制称之为优雅的设计。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

比如井字游戏（ticktacktoe）的复杂度很低而且深度也很低，但增加一些复杂度（围棋）就可以带来大量的深度。《Monopoly》有着非常高的复杂度，但并没有井字游戏那样的深度。最右侧有大量深度的是《万智牌》，AI研究人员称它是世界上最复杂的游戏。

所以，你可以通过不断增加新内容的方式增加游戏深度，如果你通过增加更多复杂度得到了深度，那么就应持续增加更多复杂度以保证深度的增加？

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

实际上，我认为深度是有极限的。如果你的游戏需要一生的时间才能掌握，那么，增加更多深度会给你带来什么？更多的寿命吗？人只有一条命！所以，我认为你应该做的是，如何用最少的复杂度，尽可能快的达到深度极限。

如果你的游戏深度在极限之外，或许你应该降低复杂度和深度，直到它落在极限之内。然而，移除复杂度可能会给你的团队带来奇怪的影响。在《炉石传说》早期，嘲讽本来的设计是一次性效果，如果你用嘲讽攻击敌人，你就会失去这张卡。有一天遇到了bug，嘲讽一直进行，我们觉得这样让事情变得更简单，所以就决定不解决bug。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

团队里有不少人告诉我们，游戏失去了很多的深度。他们没有错，这的确没有那么多的深度，但问题在于，团队已经付出了所有的复杂度成本，来学习游戏机制如何运作，所以，当你去掉复杂度的时候，他们唯一的感觉就是失去了深度。

因此，我经常说规则复杂度，但比它更重要的是，文本复杂度。这就是一个滤镜，决定了哪些人会学习你游戏的规则。你可以将自己的游戏做的看起来更简单或者更复杂，取决于你如何解释规则。

George Fan在2012年的这次演讲，“我是如何让老母亲通关《植物大战僵尸》的？”是最出色的演讲之一，这让图片让我大开眼界，如果你在屏幕上同时展现的字数超过8个，玩家们很大可能不会阅读它。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

我觉得他说的很对。这是《Marvel Snap》前15分钟所有的工具提示，可以看每条提示的字数，都在8个字以内。有一些对话会超过8个字，但你是否阅读并没有关系，因为这并不是你需要学习的重要东西。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

真正难做的是卡牌（描述）文字，我们意识到，《炉石传说》作为一款数字游戏，我们不需要写出太多的边缘案例，所以，你的英雄向目标或盟友带来2点伤害，描述就是“带来2点伤害”。《炉石传说》的平均字数是9个，《Marvel Snap》的平均字数是11个，一部分原因是我们没有使用关键词，所以我们没有达到George Fan的理想标准，这让我们有些难过。

不过，为了保证卡牌文字复杂度更低，我们会向人们展示，如果需要阅读一次以上才能理解，那么这个描述就是不合格的，我们不希望任何一张卡需要玩家阅读两次或者更多次才能理解。

所以，我们的目标是低复杂度、高深度，加倍骰子帮我们实现这个目标带来了很大贡献。大量的深度很容易理解，然而，加倍骰子简单的机制，却让我们用了很多的时间才把它做好。

**骰子的设计**

当我们玩实体游戏的时候，你可以掷骰子无数次，我们知道做成数字创意原型之后需要更多的结构，比如你每个回合可以加倍一次，因此我们加入了一个对话框：你的对手加倍了，你是继续加倍还是现在让步？

这有点不太和谐，因为它打断了玩家体验，因为你必须在回合中间不得不停下来处理这个对话框。所以，我们决定将它放到回合结束。有些同事认为应该为这种押注和虚张声势机制增加更多的深度，比如可以选择加倍或者超级加倍。

不过，这增加了大量的对话框，团队里的很多人并不理解，不知道为什么要关心这些数字。我只是想要玩卡牌游戏，你却在增加这些对话的权重，因此，我们尝试将加倍的确认，改为自动加倍，告诉玩家，下一个回合骰子数值将增加，并且问玩家是否想留下来继续，如果继续，那我们默认玩家接受了加倍。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

只是，玩家错过了点击按钮确认的机会，所以我们让玩家直接点骰子，将2倍改为8倍。这就带来了另一个问题：如果你在游戏刚开始的骰子点数很低，而到了后续回合才越来越高，那么大部分都会在刚开始的时候选择退让。因此，我们需要对骰子数值平衡，确保开始的数值更接近平均数。

所以，大部分的加倍都是自动的，我们只让玩家终止几次，错过的玩家觉得有了离开的接口，所以我们综合了所有方法，在游戏最后增加了一个自动加倍，然后增加了Snapback，这差不多就是整个过程。

但是，为什么我们将点击骰子称之为Snap？为什么游戏叫做Marvel Snap？因为起名太难了…

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这是我们为游戏取名头脑风暴的时候，写的一些选项，比如Marvel Cosmic Posse、Marvel All Capsule Orb，我们甚至还考虑过Infinity Stone Heroes of Marvel，但我们没有那么做。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

我通常都是用起名秘诀来命名，这是XKCD漫画里的一帧图片，说的是“两个音节的单词，重音在第一个”，在诗歌术语里，这叫做扬抑格（trochee），它是最好的词汇类型，比如很多著名的公司名字，都是扬抑格：Riot、Blizzard、Google、Facebook、Marvel、Netflix、Lego、Tesla、Meta、Intel、Apple、Call of Duty、Youtube……

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这里的所有单词都是扬抑格。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

我还认为，你给自己的公司或游戏取什么名字，其实并不重要。比如Apple，当你看到这个单词的时候第一个想起来的是什么？有人可能会想到右边能吃的苹果，有人也可能会想到左边的苹果公司。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

Amazon这个单词，或许你们大部分人都会想到左侧的亚马逊公司。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

不知道你们对Starbucks怎么看，但我看到它从来没有想象过右侧的太空币。你可以取任何想要的名字，人们会根据你告诉他们的内容，为这个名字注入新的含义。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

实际上，你的游戏名甚至不需要任何真正的单词，比如这些都是没有意义的单词，比如chess、什么是国际象棋？

很多年来，我们都为游戏名字的包装苦苦挣扎，《炉石传说》有着令人回味和接地气的包装，它讲的不是故事，而是游戏设定。那么Snap有故事、有设定吗？

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这是我在游戏里最讨厌的事情，“欢迎来到Marvel Snap……”

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这里要说到故事层次列表（Story Tier List），S层我们得到一个适合所有年龄段的故事，到了F层，则是枯燥的故事。关键的是，在A层，没有任何故事。所以你的选择就是，做一个枯燥的故事，还是直接去掉故事。

比如，我并不需要知道《街霸》的故事，也能享受格斗乐趣。游戏甚至会在战斗的时候告诉你是谁和谁在对战，比如布兰卡对战E·本田，战斗开始！但没有人会问他们为什么要格斗。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

不过，《Marvel Snap》讲述另一个故事：无限宝石被摧毁，它们的碎片散布在整个银河系，不同的力量开始收集这些碎片，它们不能落入坏人之手，这些石头必须重铸。但是，他永远不知道Marvel Snap….

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

最初的计划并不是以这种方式在游戏里讲故事，但是，为了将其作为获得骰子的背景设定，玩家们获得越来越多的碎片，合成无限宝石可以解锁游戏里的新功能。不过，我们非常喜欢游戏名字，所以决定保留这个故事。

所以，为什么不把无限宝石放到游戏名字里呢？比如Marvel Cube或者类似的名字，因为我们认为Snap有着更强大的影响力和乐趣。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

现在来看看我们的配方：我们有了加倍骰子，有了5分钟以内的游戏时间，不过，配方里其余的灵感来自实体桌游和卡牌游戏。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这是我的父亲，当我还是个孩子的时候，他将他的旧名片给了我，然后我在其背面设计卡牌。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

我在暴雪拿到了第一份工作，保留了所有的旧卡片，想象着有一天我可以用它们做一款卡牌游戏。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这是我们在《Marvel Snap》研发过程中做的第一个实体创意原型，它写在我的名片背面，我们有了加倍骰子、每张卡只有两个数字，还有一些奇怪的升级系统。但我们想要实现最大的事情，就是同步开牌。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

Reiner Knizia的《魔戒对决（The Lord of the Rings The Confrontation）》是我最喜欢的双人桌游，他也是最高产的桌游设计师之一，做了数百款桌游。它有点像西洋陆军棋（Stratego），但是，当你和对手玩卡牌的时候，双方的卡牌都是面朝下的，并且你们同时开牌，它会影响战斗，我很喜欢这个设计。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

Christian Peterson的《权力的游戏桌游（A Game of Thrones The Board Game）》也是我非常喜欢的一款桌游，它也有类似的战斗机制。我非常喜欢这个设计，所以想要在卡牌游戏里尝试它。所以，我知道游戏里想要加入同步开牌，但却记不得怎么玩，因为我们只玩过一次，体验过之后，我和Hamilton都觉得，这个原型并不怎么样，这有点打击士气。

当你同时玩卡牌的时候，是需要上下文环境的，我想要的是，他们会出什么牌？然后根据这些猜测出牌。这一点我是应该能想到的，因为毕竟我参加过职业剪刀石头布竞赛。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

剪刀石头布是完全随机的，它非常枯燥、几乎没有什么策略，问题是，这些锦标赛在开始之前，你有一分钟的时间嘲讽对手，人们通常会在这时候给对手错误的暗示。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这款游戏是Paul Peterson设计的《Smash Up》，它没有同时开牌的设计，但你在一些地点玩卡牌，这些地点有特殊能力，因此每次游戏都会有不同体验。我觉得这可以给我们做的游戏带来一些上下文，这个决定非常简单，但却可以带来即时乐趣。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

刚开始的时候，所有地点都同时公布，我们觉得了解所有信息需要学的东西太多，所以后来改为每个回合公布一个地点。不过，更重要的是，我认为它给我们的核心玩法带来的多样性。

**游戏里的随机性**

我之前说George Fan的演讲是我最喜欢的GDC演讲，但Richard Garfield的“游戏里的运气（Luck in games）”是我迄今为止最喜欢的游戏设计演讲，我觉得大多数都误解了运气和技术的关系。

很多人认为运气和技术是两个极端，游戏在两者之间选择平衡，我们尝尝以运气为基础的、或者技术为基础的，来形容游戏处于哪个区间。但事实并非如此。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

你可以有低技术、高运气的《Chutes and Ladders》，或者高技术、低运气的国际象棋，但是，你也可以有低运气、低技术要求的井字游戏，或者高运气、高技术要求的扑克。扑克游戏的随机性很强，但优秀的玩家总能一直赢。

我认为高技术、高运气的游戏很有趣，因为它们加入了大量有趣的决策，但每次玩的时候，也都能提供乐趣和令人兴奋的时刻。

不过，出于一些原因，我认为《炉石传说》的核心比其他卡牌游戏的变化少一些。其一，法力水晶系统并不是随机的，每个回合只能得到1个法力水晶。你每个回合并不是抽取更多的资源，只是更多可用的卡牌。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

但问题是，我们希望《炉石传说》有更多的变化，所以我们增加了一些变体卡，比如奥术飞弹（Arcane Missiles）随机给敌人带来伤害，闪电风暴对敌方随从带来范围伤害，动物伙伴可以随机召唤一个野兽。

在增加游戏随机性方面，这个设计是很成功的，但玩家们并不喜欢，很多人反馈说《炉石传说》太随机了。我觉得一方面可能是随机性太高了，但另一方面，我认为随机性有两种：输入随机性和输出随机性。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

输入随机性指的是随机事件，比如抽一张卡，然后你需要做战略决策。所以，输入随机性是非常好的，它将你带到了新的情况，你需要实时思考并作出决定。像国际象棋这样的游戏是没有随机性的，比如你不需要考虑第一个回合需要走哪个棋子。由于随机性的存在，你会觉得对游戏里的随机性有很高的控制。

输出随机性恰好相反，你做了一个决策，然后根据随机性来判定这个决策是对是错。比如Danger Room，你在那里每次出一张卡，都有25%的概率被摧毁。再比如炎魔之王拉格纳罗斯，在每个回合结束随机给敌人造成8点伤害，或许是敌方英雄，那么打出伤害你就赢了，也或许是你不想打的对象，那你可能就会输，但你首先要选择这张卡。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

输出随机性令人兴奋，主播和观众很爱使用这些卡牌，经常能带来非常有名的故事。我觉得在游戏里，给玩家最好的问题就是，这个风险值得冒吗？这需要取决于玩家，比如你会想，我反正快要输了，我想要冒一些风险，我要在Danger Room玩这些卡牌，希望能不会中那25%的概率。

如果你加入了随机性，玩家们很可能会迷失其中，所以这有利有弊。对于地点，它有输入性也有输出随机性，你可以选择在哪个地方获得更多的随机性。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

我们谈了很多的随机性，但它们还有一些其他有趣的效果，一款卡牌游戏里，随着时间的变化，核心玩法会变得没有新鲜感，这也是为何其他卡牌游戏每年发布数千张新卡的原因，主要是为了保持玩法新鲜感。因为，你最终会遇到没有新问题需要解决的情况，随机地点可以给每一个卡牌游戏增加新东西，降低了游戏失去新鲜感的风险，而且它不会对游戏平衡造成太大的影响。另外，它对于在线运营也可以带来很大的帮助。

在游戏发布的时候，我们有一百多个地点，当时在想，我们为何不减掉60个地点，只发布40个，然后接下来的一年里每周都发布一个新地点？这个数字可能不准确，但我们的确减少了地点数量，然后每周发布一个新地点，这对我们的在线运营带来了很大的帮助。

从第一个创意原型，到现在有了这些机制，只用了两天，这有些不正常，我们决定停下来设计其他游戏，因为我们不太确定这样做是否正确。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

最终，我们打印了创意原型，多年之后，我们还在使用这个创意原型为2v2玩法做创意原型，这个模式只有5个位置，你的团队必须得到三个位置才能赢。这是非常有趣的，如果没有最初的实体创意版本，我们可能没办法做这么快。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

因此，这就是《Marvel Snap》的配方，除了以上提到的所有配料之外，我们还做了一些创新，比如六个回合、12个卡组，1个卡牌类型，实际上也就是没有卡牌类型。这些创新是很有影响力的，但它们在当时对我来说并不明显，因为你的游戏一定需要创新才能吸引用户的兴趣。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

如果我问一个玩家，你觉得《Marvel Snap》最具创新的三个点是什么，我相信这三个一个都不会出现。所以，有了创意原型之后，我们开始制作数字版创意原型。

**数字版创意原型**

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这是我们的首个数字版创意原型，我们希望快速推进，大概用了2周时间完成，当时没有考虑网络问题，这毕竟只是个创意原型，我们把它放到了iPad上。

我们让一切变得很容易改动，以便找到游戏里适合的设计。比如我们尝试过六个回合、五个回合，还尝试过每个地点9张卡或者6张卡，我们尝试了很多东西。

到这个时候，所有东西都是我和Hamilton两个人做出来的。我认为，刚开始有一个尽可能小的团队，可以带来很戏剧化的核心，因为你不需要投入太多时间解释愿景并被一个大团队接受。我记得《炉石传说》最初的团队只有10个人，然后暴雪调走了3个工程师做《星际争霸2》，我们当时以为这个项目很大可能会被取消。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

离开团队的是艺术总监Ben Thompson、Eric Dodson以及时的首个主策划。当这样的事情发生的时候，我们有了很高的自由度，可以尝试一些非常疯狂的想法，团队其他人并没有走，他们参与了玩法测试和一些交流，但到了那年底团队回来的时候，《炉石传说》的核心玩法已经被确定。

一旦团队变得更大，转向就变得更加困难。在《Marvel Snap》研发后期，我们改变了一些主题并去掉了一些游戏货币，团队这时候很担心还没有锁定一些关键的东西。所以，我知道这些改变并不是那么容易通过，因此我和每一个团队成员单独对话，向他们展示想法，给他们提出问题和表达意见的机会，做出这些改变需要数周的时间，哪怕是这个想法都让很多人感到不安。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

最后，我们增加了人手，这是我们的首席制作人，当时他是秘密作为我们的后端服务器工程师。可以看到这里我们每个位置9张卡，尝试的是5回合制。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这是我们的艺术总监Jamaro Kindred加入之后，我们快速推进游戏创意原型，但我们遇到了困难。我觉得每个卡牌游戏都会有破坏目标生物的卡牌，我们有很多这样的卡牌。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

《炉石传说》的UI设计很出色，尤其是攻击时候有个箭头，让你知道可以攻击的目标。但在移动设备上，人们大多数的操作都是点击，所以这个设计并不是很好。所以我们需要做一个全新的UI。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

实际上，《Marvel Snap》的每张卡都需要一个目标，你需要在左中右之间选一个方向，我们最初要求玩家选择两个目标，我们意识到可以让第二个目标通过第一个目标来实现。另外，还可以通过卡牌顺序来解决目标问题。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

比如Mystique之前是选择一个复制卡，随后的目标是在你出了你想要复制的卡之后。我们并没有那么多需要目标的卡牌，大概只有10张，但我们都做了改变，游戏感觉好了很多。

解决了这些问题之后，我们开始为游戏增加更多东西，创意原型也开始慢慢成为了一个真正的版本。

**核心循环（Core Loop）**

之前，我吹牛说我们用了两天设计了核心玩法，但是，结果我们发现，后来我们用了四年的挣扎，才确定了游戏的核心循环以及令人满意的进度模型。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这是我们游戏的核心循环，千万不要细看，这是我们迭代的版本之一。我们做了联赛，你需要不断升级联盟等级才能解锁特定卡牌。我们还做了一个英雄收集系统。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

这是游戏的英雄卡系统，你必须从其中选择一个想要升级的英雄。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

我们从这里学到最大的教训就是尽量简化，所以后来做成了这个版本。我们砍掉了很多东西，以为这个版本已经可以了，但结果发现还是太复杂。

我们保留了联盟，但解决了之前的问题，改变了主题，加入了无限宝石，每周排名，甚至还加入了一个游戏内商店让玩家直接购买想要的卡牌，卡池每天都会更新。意味着到最后还出现在商店里的，都是你不想买的卡，所以这个方案也不好。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

到了2020年，我们将核心循环改成了这样，也是游戏发布时的版本。我经常遇到这样的问题，当我觉得解决问题的方法是增加复杂度的时候，往往随后都会发现其实需要的是简化。我觉得Pascal的话最能形容，“我本来想写一封更短的信，但我没有时间。”

**总结**

最后，我希望将我们的心得总结为四个经验，但需要强调的是，核心玩法的设计对于游戏整个体验是非常重要的，但是，这只是让游戏变得优秀所需的1%的工作量。更重要的是，我们作为一个团队所做的所有决策。

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

作为一个远程团队，我这里没有完整团队的合家欢照片，我想说的是Second Dinner团队非常棒，很荣幸能够成为其中一员。

以下是我的四个心得：

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

大厨需要配料，所以在你的储藏室保存食材。

成为快艇，直到你的方向足够清晰。

拥抱随机性，不管是输入还是输出性的。

简化，哪怕你的团队因此讨厌你。

····· End ·····

___

**GameLook每日游戏产业报道**

全球视野 / 深度有料

爆料 / 交流 / 合作：请加主编微信 igamelook  

广告投放 : 请加 QQ：1772295880

      长按下方图片，"**识别二维码**" 订阅微信公众号  

![图片](data:image/svg+xml,%3C%3Fxml version='1.0' encoding='UTF-8'%3F%3E%3Csvg width='1px' height='1px' viewBox='0 0 1 1' version='1.1' xmlns='http://www.w3.org/2000/svg' xmlns:xlink='http://www.w3.org/1999/xlink'%3E%3Ctitle%3E%3C/title%3E%3Cg stroke='none' stroke-width='1' fill='none' fill-rule='evenodd' fill-opacity='0'%3E%3Cg transform='translate(-249.000000, -126.000000)' fill='%23FFFFFF'%3E%3Crect x='249' y='126' width='1' height='1'%3E%3C/rect%3E%3C/g%3E%3C/g%3E%3C/svg%3E)

····· 更多内容请访问 www.gamelook.com.cn ·····

Copyright © GameLook® 2009-2023

        觉得好看，请点这里 ↓↓↓