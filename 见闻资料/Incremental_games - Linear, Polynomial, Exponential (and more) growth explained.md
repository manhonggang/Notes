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

# 翻译

本教程的灵感和信息主要来自这个wiki。

如果你是这个子的常客，你会看到线性、多项式和指数这些术语有时会被抛来抛去。有一些博客和教程很好地解释了这些函数在平衡增量游戏中的作用（有时可能是相当的数学密集型）。不过，还是有一些人似乎对不同函数增长的含义感到迷茫。

增长指的是一个数字序列的增长速度。在增量游戏中，这些序列通常是按时间计算的资源或基于等级的价格。边界的概念也很重要。如果B的增长速度比A快，也就是说，在某一点上B比A大，并且永远保持大，我们就说B约束A（上面）（下面的约束也是如此）。

请注意，bound 是关注一个序列变大的速度，而不是特定的值。让我们看一个例子。

A: 1.000.000, 2.000.000, 3.000.000...

B: 1, 4, 9, 16...

我们可能会认为A增长得更快，因为它的数字更大。然而，经过（漫长的）一段时间后，它看起来像这样。

A:9.99999E11, 1.0E12, 1.000001E12

B:9.99998E11, 1.0E12, 1.000002E12

因此，B比A增长得快。

当一个序列上下被同一个函数所限定时，我们说它的增长与该函数一样，例如二次增长。同样，我们不关心具体的数值，而是关心序列如何发展。这个概念很有用，因为我们可以用它来对序列进行分类，将它们与众所周知的数学函数进行比较。

神圣的三位一体。

线性、多项式（度数>=2）和指数是目前最常用的增量增长率。原因是它们互相依次约束（线性 < 多项式 < 指数），可以结合起来平衡游戏中生产和价格的进度。

如果价格增长慢于产量，在某些时候，买东西就变得微不足道，因为你生产的东西比你花的钱多，平衡就被打破了。如果它们以同样的速度增长，买东西所需要的时间几乎保持不变（例如每10分钟1次），这可能会或可能不会有趣。如果价格增长得更快，买新东西的时间就会越来越长，从而减缓了进度。设计师们利用这种减慢速度的方法来迫使玩家在进度太慢的情况下撞上 "墙"，通常会迫使玩家采取某种行动（声望，移动到游戏的新部分）来继续前进。

我们现在要着手逐一解释。

多项式

线性

描述。像线性函数一样增长。

函数示例：x

示例序列。1,2,3,4,5...

解释。虽然我们平时说的线性和多项式是不同的东西，但是线性是多项式的一种，具体是1度。

线性增长是大多数人都会熟悉的，因为它在我们的日常生活中随处可见。这个序列以固定的速度增长，所以连续两个元素之间的不同是相同的。这也是人们对事物进展的直观思考：如果去某地需要1小时，那么再走两次大概需要2小时。如果买东西要花100元，以此类推。

可能的用途。线性增长几乎总是被用来作为资源生成率。它很简单，很容易操作，人们也很熟悉它。他们也自然而然地接受了它的训练，并且可以很容易地对它的进展进行猜测。

超线性。

二次方

描述: 像2度的多项式一样增长.

函数示例: x<sup>2</sup>

例子序列： 1,4,9,16,25..: 1,4,9,16,25...

解释：当我们谈论多项式时，通常是指度数>=2的任何多项式。当我们谈论多项式时，通常我们指的是度数>=2的任何多项式。度数正好为2的多项式有一个特殊的名字，叫二次型。

从这个例子序列中我们可以看到，与线性增长中不同的是，这里两个连续数之间的距离会越来越大。现在让我们看看两个连续数字之间的距离。

3,5,7,9,11...

我们可以看到，虽然距离越来越大，但它是以2的恒定速度增长的。

人们对二次方增长的理解比较困难，因为在我们的日常生活中，二次方增长并不像线性方增长那样常见。其中有这样几个例子：在一次体育比赛中，每支队伍都需要与其他队伍进行一场比赛。在这种情况下，总的比赛场次是以x2为单位的（感谢这篇文章的启发）。

可能的用途。由于二次方位于线性和指数之间 它既可以用来计算价格也可以用来生成资源。一个用于生成资源的tipycal例子是 "创造建筑物的建筑"，如在衍生点击器中看到的那样

立方体、夸脱体等。

说明: 3(x<sup>3</sup>),4(x<sup>4</sup>) 等度的多项式。与四元组的描述相同，但每一个都增长较快。

指数。

说明。序列的增长率是当前值的一个系数。

函数示例：2<sup>x</sup>

示例序列：2,4,8,16,32,64,128,256...。

解释。指数型增长是人们通常最容易出现问题的。我们知道它的增长速度很快，但人们通常并不完全理解这个快是什么意思。它通常被误认为是高程度的多项式，因为这些多项式产生的数值很大。

如同在多项式的情况下，我们看到数字之间的距离是如何变大的。让我们来看看两个连续数字之间的距离。

2,4,8,16,32,64,128

我们可以看到，与多项式不同的是，两个连续数之间的距离之差不是恒定的，而是增大的。这就意味着，不仅数字之间的距离会随着时间的推移而增大，而且这种趋势会随着时间的推移而加速。

指数增长在现实生活中的一些情况下也会出现，但通常比较复杂，有些人可能会迷失在其中。例如，贷款或银行储蓄的利率都会遵循指数增长，因为它们每年都会乘以一个比率。此外，一些生物的数量，如病毒和细菌的数量也遵循指数增长，例如病毒的总数量每天都会翻倍。

可能的用途。指数几乎只用于价格，因为它既是线性的，也是多项式的，它确保玩家的进步会随着时间的推移而减慢。

增长的动物园。

除了我们看到的三个成长函数之外，还有很多其他的函数，既有慢速的，也有快速的。这些函数大多鲜为人知，虽然有些函数对增量游戏的作用不大，但有些函数却有很大的潜力来实现有趣的游戏机制。

在下面的章节中，我们将描述从慢到快的不同增长速度。

次多项式。

迭代对数。

说明。像迭代对数一样的增长，log*。

函数示例：log* x

示例序列：log* 2 = 1，log* 4 = 2，log* 16 = 3，log* 65536 = 4，log* 265536 = 5。

解释。迭代对数函数的意思是 "我们需要对这个数应用多少次log才能使它<=1?" 它的增长非常非常慢。有多慢呢，看看这个序列。对于265536，它的值只有5。出于所有实际目的，我们可以认为这个函数的值是<=6。

可能的用途。我能想象到这个函数的唯一用途 就是我们希望保持一个几乎不变的值。

对数。

说明。像对数一样增长

函数示例：log x

例子顺序： 1, 1, 1, 2, 2, 2, 2, 2, 2, 2, 2, 3, 3...

解释：指数的倒数，这个函数随着时间的增长而变慢。在某些时候，它很难再增长了。

可能的用途：这个函数可以用来实现发电机或升级的收益递减， 这样你从购买更多相同的东西中得到的好处就会减少，你拥有的越多。

多项式。

子线。

说明：以多项式速度增长，但比线性慢。以多项式速度增长, 但比线性慢.

示例函数: sqrt(x)

例子顺序： 1, 1, 1, 2, 2, 2, 2, 2, 3, 3, 3, 3...

解释：X的平方根是x1/2。x的平方根是x1/2。如果我们把线性想象成x1，那么平方根的增长速度比线性慢是有道理的。另外，虽然它的生长速度比线性慢，但并不像对数那样不堪一击，还是能取得一些缓慢的进步。这种增长也可以概括为立方根、4根等，每一种增长都比较慢。

可能的用途。一些游戏使用了对资源生产施加惩罚的技术 来减缓玩家的进步。这种惩罚可以使用平方根曲线。由于线性边界为sqrt，我们将减缓生产速度，而不会有完全停止生产的风险。

超线性但次二次方程。

说明。增长速度比线性快，但比二次型慢。

函数示例：x*log x

Example sequence: 200,202.43,204.87,207.32,209.77,212.22,214.68,217.14,219.60,222.07

解释：它的增长速度比直线型略快，比二次型明显慢。它的增长速度比直线型略快，比二次型慢得多。它可以泛化为更高度的多项式，如x<sup>2</sup>*log x。

可能的用途。可以用来略微提高产量，例如根据当前的资源量提供发电量奖励。

超多项式，但又是亚指数式。

说明。增长速度比任何多项式快，但比任何指数慢。

函数示例：x<sup>logx</sup>

例子顺序： 1, 3, 6, 13, 24, 44, 75, 124, 200...

解释：它的行为更接近指数而非多项式，但仍受其约束。它的行为更接近于指数而非多项式，但仍受其约束。

可能的用途。这是个非常有趣的函数 人们通常使用指数增长来减缓价格的进步。使用这个函数，我们将在长期内实现同样的减速，但这个过程需要更长的时间，增加玩家的进阶曲线。

超指数但次迭代指数。

指数多项式。

说明：指数是指指数为多项式的指数。指数的指数是一个多项式。

函数示例：2<sup>x<sup>2</sup></sup>

Example sequence: 2,16,512,65536,33554432,68719476736,5.6295E+14,1.84467E+19

解释。指数的快速版本。

可能的用途。如果资源按指数增长，这个函数可以用来计算价格，约束生产。当常规的指数增长不够时，也可以使用这个函数。

超倍指数，但次迭指数。

说明：定义固定高度的电力塔。定义固定高度的电力塔。

函数示例：xxx, 222x

解释。我们把一组嵌套的权力称为权力塔。塔的高度是指有多少个权力，例如xxxx是一个高度为4的权力塔。

迭代指数。

Tetrational.

说明。按四项函数的顺序增长。

例函数：2↑↑x，使用Knuth上箭头符号。

例子序列：1, 2, 4, 16, 65536, 265536: 1,2,4,16,65536,265536,2个数字约19000个数字

解释。你有没有想过指数之后是什么？ 答案是渗透。tetration是一种运算，它定义了一个数字被提升到自身幂的多少倍。在这个案例中，x定义了动力塔的高度。而且它的增长速度快得惊人。

有多快？看看这个序列。在6个步骤中，我们已经有了265536。但在下一步，我们有2到一个数字的幂，大约有19000个数字。你能想象吗？好了，这里你有一个有19000位数的数字的样子。这就是2的指数。

可能的用途。这个函数的增长速度非常快，以至于目前的数字库都无法容纳它。

超算子、其他超算子。

说明。渗透之后是什么？渗透 然后呢？六角化 我们可以为每个超算子定义渗透之后的增长速度。

在基元递归、非递归、不可计算上。

描述。最后一站 句号的结束。我们已经看到了增长快得离谱的函数。有什么能比这更快呢？那我们甚至无法计算的函数呢？我不是说我们不知道怎么做，但它已经被数学证明是不可能的。其中最著名的一个是 "忙碌的海狸"。

例子函数。忙碌的海狸.

例子序列：? 4,6,13,???

解释：? 由于这个函数无法计算，我们只知道准确的前几个值。然而，事实证明，这个函数的增长速度比任何可计算函数都要快。包括四项式、五项式等。

可能的用途。好了，又有新的东西可以做噩梦了 There, something new to have nightmares about.