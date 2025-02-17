#  【趣文】Rust 公案 （Rust Koans）

> Rust 公案（Koans）是来自 Rust 官方用户论坛中 [DanielKeep](https://users.rust-lang.org/u/DanielKeep)  在 2015 年编写的一[系列趣文](https://users.rust-lang.org/t/rust-koans/2408)。
>
> 公案（Koans）是来自于佛教中的一个词，用来表示禅师无法理性回答的疑问或矛盾的问题。
>
> 此处 Rust 公案 则用来映射 Rust 新锈在学习 和 使用  Rust 时必然要经历和思考的一些问题，给人启迪。

本文一共分成四个短篇：

- [障碍（Obstacles）](#障碍) 
- [行为建模（Behavioural Modelling）](#行为建模)
- [完美（Perfection）](#完美)
- [咒语](#咒语)

## 障碍

连续第八天， 新锈 科尔 发现自己站在神庙的两个大守卫面前。他们站在寺庙的大门前，身穿简单的长袍。尽管如此，他们还是很有气势，让人敬畏。他自信满满地走向第一个守卫，并把写有他的计划的羊皮纸递给他。

第一守卫仔细阅读了它。这一步不过是个形式；昨天，他只是没有得到第二卫队的同意。他确信他已经解决了所有悬而未决的意见。

第一守卫将羊皮纸递回给科尔。然后，他以一种盲目的动作，用他的手在科尔脸上拍了一下。第一守卫用缓慢且严肃的声音对他说："不匹配的类型：期望 `&Target`，发现  `&<T as Deref>::Target`"，然后就沉默了。

科尔拿着他的羊皮纸，退回到附近的长椅上，几乎要哭了。八天了。他的程序似乎并不特别复杂，但他却无法说服两大守卫允许他进入神庙。他在其他寺庙没有遇到过这么大的困难！在另一张长椅上，他看到了一个同伴。

在另一个长椅上，他看到了一个同龄的 新锈。两天前他们曾交谈过，当时他得知他的同胞为了让他的计划被接受，已经在寺庙外辛苦了近两个星期。

这都是警卫的错。科尔知道他的程序会按计划进行。他们所做的似乎只是在小错误上挑毛病，以最琐碎的理由拒绝他。他们在寻找拒绝他进入的理由；就是这样！他开始愤愤不平。

他开始愤愤不平了。

这时，他注意到一个僧人在和另一个新来的人说话。他们的谈话似乎很活跃，突然间，这个 新锈大叫一声，跳了起来，冲向寺庙。在他奔跑的过程中，他似乎在疯狂地修改他的程序。

然而，他没有面对两大守卫，而是走到墙的一个小的、喧闹的部分。令科尔惊讶的是，墙壁打开后似乎是一个秘密入口。 新锈通过了，然后从眼前消失了。

科尔目瞪口呆地坐在那里。一个秘密的入口？那么......那么两个大守卫可能只是一个恶作剧！？其他僧认让 新锈经历的事情，是为了教他们谦虚。或者......复原力。或者......或者......也许只是为了偷偷地嘲笑他们。

"你想知道我对他说了什么吗？"一个声音问。科尔转过身来，看到那个僧人站在他的长椅旁边。"你告诉他有另一条路可以进去，是吗？"

"是的，" 他回答。"我告诉他那扇门不安全。"

"不安全？" 科尔问。

"的确如此。这是那些在寺庙里长期努力学习的人知道的秘密。事实上，人们可以通过使用不安全的艺术来克服编写程序中的许多障碍，正如《Rustonomicon 》中所说的那样。"

"它们很强大吗？" 科尔惊奇地问道。

"非常强大。通过转换，人们可以简单地重新分配一个值的类型，或延长一个指针的生命周期。人们甚至可以从空气中召唤指针，或从虚无中召唤数据。"

科尔觉得他终于明白了神庙的工作原理。僧侣们所使用的正是这种 "不安全 "的魔法! 然而...

"那么，如果人们可以简单地穿过不安全的门到达寺庙，为什么还要雇用两大守卫？为什么不......"

就在这时，从寺庙内传出一声令人毛骨悚然的尖叫。它回荡在整个院子里，然后突然结束。

寂静降临了。没有人动。没有人说话。风静止了。甚至鸟儿也停止了歌唱。

科尔可以感觉到他的心脏在他的耳边跳动。

"他们在那里，"僧侣说，打破了咒语，"保护你不受寺庙和里面的东西影响。"

科尔转过身来，再次凝视着那扇隐藏的门。"那为什么那扇门会存在？"

"因为，即使是他们也不是无懈可击的。有些时候，人们必须独自面对危险。" 他叹了口气。"但不是所有的人都那么勇敢或熟练。"

就这样，僧人从他的斗篷里拿出一张羊皮纸，走向两大守卫。第一守卫看了他的方案，点了点头。第二守卫看了他的方案，把它递了回去，然后在她脸上打了一下。

"借来的价值活得不够长。"

僧人揉着脸，走了回来，坐在其中一个长椅上，喃喃自语地咒骂。

在那一刻，科尔豁然开朗。



## 行为建模

在一个温暖的秋日里，法布尔德修士在最近开放的 锈寺 附近的抽象花园里散步。他经过了许多好奇的、精心设计的复杂抽象作品的展示，这时他偶然发现了一个僧侣在她自己的展示中辛勤工作。她的长袍表明她是个新锈，尽管她那双布满皱纹、磨损的手说明她有很多很多年的经验。在她周围，散落着几十块各种形状和大小的白色石头，还有几把不同的耙子。每个石头上都贴着一个小的纸标签，上面写着一个字。

他很感兴趣，走近一看。

"嗬！"他说，"你叫什么名字？"

"我是尼奥普特-马兰。"

"如果我可以询问的话，你在研究什么问题？"

"我正试图翻译一个以前的设计，它可能适合于寺庙，" 新锈回答说，集中精力看一张大纸，上面画满了盒子的草图，由许多线条和箭头连接。

"我看到了许多标签；那些是用来做什么的？"

"它们定义了每个物体的类（Class）。"

法布尔德弟兄停顿了一下。"什么是类？"

新锈面向他露出困惑的眼神。"你不知道类是什么？"

"不，"他回答。"我听说过这样一个从远方随风传来的词语，但在这个地方，我们不使用它。"

"啊，我明白了，"马兰说。"在我来的那个寺庙里，我们用类来定义一个事物的所有属性和行为，许多人可以共享一个定义。"

"一个有用的装置，然后。在这样的计划中，作为一个简单的园丁，我将有一个倾向性的行为，那么？"

新锈点了点头，拿起一块小石头。"这是一块岩石，"她说，给法布尔德修士看了看标签。"它没有方法，因为它所做的就是躺在地上，直到被操作，但它有重量和体积等属性。"

"所以一块石头根本不能做任何事？"

"什么都不能。不像这个耙子，它拥有耙动一个或多个岩石的能力。这使我能够对一个花园及其演变进行完整的建模。"

"真的吗？这个简单的模型允许你捕捉所有可能的相互作用，然后呢？"

"是的！"马兰新锈自豪地感叹道。"我已经使用了很多年，取得了巨大的成功。"

"但如果岩石希望滚动，或发光，或说话呢？类听起来是限制性的；我更喜欢定义较小的行为，每个东西都可以挑选它想做的事情。"

新锈嘲笑道。"一个物体只能做它被设计为做的事情，没有别的。你说你是个园丁；你的任务是指导 新锈，还是做饭？"

"我不是；我的任务是做园艺。"

"对于类，这样的情况在设计时由你的类来表达。因此，永远不可能有任何混淆！"。改变行为就是改变系统的设计！"

"很迷人，"法布尔德说，点了点头。 新锈转身回到她的工作上。

"我必须承认，我很难找到如何以神庙认可的方式来表达这个概念，但我--" 新锈被打断了，因为一块较小的白色石头砸中了她的头。

抱着她的头，马兰转过身来。"是你向我扔石头吗？"她问道。

"我？"法布尔德修士说。"当然不是。我只是一个普通的园丁；我对扔石头一无所知。"

"这块石头不可能自己扔出去！"

"然而，你的设计不允许这样的事情发生。当然，你一定是搞错了：没有石头被扔出来。"

马兰新锈冷哼一声，转身回到她的草图上。

一会儿，她闪开了，因为一根长木杆击中了她的手臂。"你是不是......？"

"耙子 " 只能耙岩石；它不能 "打新锈"。 你一定是在胡思乱想。

"但你......"

"嗬！法布尔德修士！"另一个修士从花园的另一端喊道。"谢布修士生病了；你能不能好心地代替他做晚膳？"

"我很乐意，杜尔修女；我现在刚刚完成对这位新锈的指导。"

在那一刻，马兰豁然开朗。

## 完美

修女清 在被阿伯特称为 "架构大师 "的人的注视下紧张地跺脚；他是一个叫托兰大师的僧人。"按照承诺，我在新月的前一天向他提交了我完成的设计，以及三百六十一页的大量文件，解释了接口的所有正确和错误的使用方法，"她总结说。"我对文件特别自豪。我费尽心思，确保所有可能的不相容性和失败案例都被详细列举出来，但阿伯特似乎并不太高兴。"

"然后呢？"托兰问。

"他说，'你已经辛苦了很久才完成这个，但现在我想让你和架构大师一起工作一段时间。也许会学到一些东西'。因此，我来到这里，"她说完。

托兰大师点头表示理解。他显然似乎知道这是怎么回事。"阿伯特让我为寺院设计一座新的宝塔，让寺院的知识有一个合适的归宿。在我开始建造之前，我必须确保设计是完美的。因此，我将给阿伯特送去一个模型；既是为了让他检查它，也是为了确定设计是否合理。"

清点了一下头，因为这听起来非常有道理。

"恰好，我已经准备了这样一个模型。它在那里。"大师说，指了指房间角落里的一张桌子。清走到那里，发现上面布满了数以百计的细小的、松散的精雕细琢的木头碎片。

"这是......当它未被组装的时候，它真的能被称为模型吗？"

"有道理，修女。你的任务是将模型组装起来。"

"我......"？

"我已经劳累了许多天，几乎没有休息；我想我应该在花园里走走，让我的头脑清醒一下。毫无疑问，像你这样有天赋的修女在完成这最后的手续时不会有任何困难。"

"师父，我是算法的架构师，不是建筑的架构师；我对木材和石头知之甚少。"

"要学的东西很多，但幸运的是，我已经知道这项任务所需要知道的一切，并且已经为你建造了这些作品。"

"但我不知道......事实上，我对宝塔的外观只有一个模糊的概念！"

"这对你这种能力的人来说应该没有什么困难。" 就这样，托兰大师把清和那堆模型零件单独留在车间里。

清感到很沮丧。在不知道模型是什么样子的情况下，她不可能组装好这个模型的！她不知道该怎么办。图纸，蓝图，一些大致的轮廓......一个所谓的大师怎么能指望她在没有任何指导的情况下建造如此复杂的东西？

有一段时间，清只是盯着这些杂乱无章的木片。漫不经心地，她开始检查这些碎片。她开始为有这么多不同的、独特的部件而着迷。即使是像小木梁这样简单的东西，也有许多略有不同的变体。一个可能在一端有一个方形接头，下一个可能是圆形。另一个会以六边形结束。

她心血来潮，拿了两块看起来很像的木砖，发现它们并不适合在一起。放下一块，她又尝试下一块。再下一个。再下一个。最后，她找到了第二块合适的砖。

她现在有了两块瓦片。于是，她又找了第三块。

然后是第四块。

然后是第五块。

每走一步，她都能找到一块合适的地方。不久之后，她意识到她已经建造了一个似乎是地板的东西。地板上有几个孔，可以容纳其他部件。仔细搜索了一下这堆东西，发现只有五根横梁可以安装。因此，她把它们放在一起。

当外面的太阳越过天空时，这一切都在继续。宝塔越长越高，似乎是自己的意愿。地板被组装起来，墙壁被连接起来，瓦片被锁在那里。清友觉得她无法控制模型是如何形成的：就好像模型知道它需要什么形状，不允许她有任何自由。

当太阳低垂在天空时，清友发现模型已经完成。每一块都被使用了。结构是健全的。它很高，屋顶有优雅的弧度。尽管她不明白这是怎么做到的，但托兰大师以某种方式建造了一个稳定而美丽的宝塔模型，尽管他没有参与组装。

"啊，正好赶上我散步回来。"

清并没有转身面对他。"我相信你现在头脑清醒了很多 ？"

"的确如此。现在，我想让你把模型交给阿伯特，并告诉他所学到的东西。"

。。。

"于是，我回到这里。"她说完，向阿伯特展示了完成的模型。

阿伯特皱起了眉头。"那么，"他问，"学到了什么？"

"我为我的文档感到自豪是错误的。虽然它来自于巨大的努力和用心，但我应该把这种努力用于使接口本身更好。我应该努力做出一个不需要三百多页解释的接口。一个由类型本身引导程序员使用的接口。

"一个完美的接口是一个不可能使用错误的接口，即使是意外。

阿伯特叹了口气。"我想这是没办法的事。来，让我们把它和其他的放在一起。"

清困惑地跟着阿伯特，他带着她穿过寺庙的蜿蜒走廊。最后，他们来到一个长长的大厅，每面墙上都有几个架子。

每个架子上都摆放着几十个小模型佛塔，每个都和上一个略有不同。走到房间的最里面，经过一系列的小建筑，阿伯特指了指架子上的一个空位，基友把她的模型放了进去。

这似乎是一个教过和学过很多次的课程。

"这是你学到的宝贵一课，但这不是我派你去见托兰大师的原因。"

"噢？"

"的确不是。大约八年前，托兰大师被要求为这座寺庙建造一座宝塔。每次他完成一个设计，就会再次撤回，声称它还不够完美。" 他又叹了口气。

"我倒是希望你能教教他实用主义的价值，为了完成而妥协完美。即使是一个丑陋的、摇摇欲坠的棚子，也会比一个假设的、无缺陷的宝塔更有用。"

在那一刻，清豁然开朗。

## 咒语

新锈 科尔有一天来到图尔大师面前说。"我几乎已经完成了一个程序，在其中我看到了重复的代码模式。这些模式不够规则，无法用函数或特质来抽象。我想使用宏，但不知道该如何进行。"

图尔大师考虑了这个问题。"我相信我知道谁可以帮助你找到清晰的思路。来吧。"

他们一起离开了主殿，经过了花园。在院子的外围，他们遇到了一座奇怪的建筑。每块木板、每块面板、瓷砖、窗户；在形状、大小、颜色、质地、材料上都是独一无二的...... "这是什么地方？" 新锈问。

"这是 "落雪花（Falling Snowflake） "家族练习合成抽象艺术的地方。他们最讨厌重复。" 科尔在他们进入时点了点头。

在里面，建筑同样是无情的独特。没有两扇门是相同的形状或大小。每支蜡烛和它的栖息地都以不同的方式设计和着色。科尔开始感到头晕目眩。

甚至僧侣们本身也是这种做法的典范。与其他僧侣所穿的朴素的深棕色长袍相比，落雪寺的每个僧侣都穿着杂乱无章的材料和颜色的集合。科尔想，也许是一场大风暴卷起了一个布商的货物，并把它们放在这些毫无戒心的僧侣身上。

然后他的目光被墙壁所吸引。墙壁上布满了程序，这些程序似乎是用某种奇怪的语言写成的，正如他所期望的那样，来自APL的寺庙......但在这里和那里，他瞥见了熟悉的语法，尽管它们没有什么意义。

僧侣们的讲话也很奇怪。科尔观察到有几组人静静地站着，互相凝视着对方。他开始想，也许他们根本就被禁止说话，这时他听到有一组人爆发了。

"Sie durm! Wik puom, eeis"。

就这样，站在这群僧侣中的人互相点了点头，走了。

"大师...... "科尔开始说。

"正如我所说，他们厌恶重复。因此，他们厌恶我们的语言，因为它充满了冗余，更不用说不准确了。相反，他们使用自己的语言，这既是完全精确的，也是完全最佳的。他们只说自己的意思，不说别的。"

"但他们是如此安静，否则。"

图尔大师点了点头。"你认为在说一个字之前，完全准确地决定一个人想说什么，这容易吗？"

当他们穿过一个小小的、五边形的门洞时，他们来到了一个穿着染成千百种深灰色的布的僧人面前。袈裟上缠绕着一个令人着迷的白线图案，似乎永远在布上盘旋；一个由直线和方块组成的无限的、弯曲的野兽。

"新来的，这是昆仑大师，落雪花族的族长。" 僧人点头致意。"告诉他你的问题。"

科尔吸了一口气。"我几乎已经完成了一个程序，在这个程序中我看到了很多重复的东西。

"在某些情况下，逻辑必须调用不同的函数，尽管周围都保持不变。在其他情况下，不同的类型实现了类似的方法，然而它们不能通过特质来统一。

"有人告诉我，宏可能是解决我的问题的一个办法。你有什么建议？"

昆仑大师沉默了。持续了很长时间，以至于科尔开始在大师的注视下紧张地晃动，不确定他是否以某种方式冒犯了他。

科尔注意到，这位大师的眉毛有点奇怪......

最后，昆仑大师这样说话。

"Fheiq kah, puom"。

然后他向科尔点了点头，转身就走了。

"谢谢你的建议，昆仑大师。"图尔大师一边说，一边引导科尔沿着他们来时的路回去。

他们一边走，科尔一边试图理解发生了什么。走回阳光下，他得出了一个结论。

"与昆仑大师交谈是否有助于你找到答案？" 图尔大师问他。

"是的，"科尔回答。"我已经完成我的程序。"

图尔大师点了点头；这个新来的人已经开窍了。

