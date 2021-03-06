# 蔡学镛

### 微博
1. PowerApps/Flow，Eve，PWCT ... 等技术，都是为了降低编程的难度而存在的。但我觉得这些技术都有明显局限，且使用难度还是太高。我比较希望看到的是在 Red 语言上架一个通用框架，通用框架上面有一个 DSL，再通过 “需求聊天机器人” 把用户需求转为此 DSL。用户只要通过聊天，就可以完成软件的开发。
2. 某功能应该放在哪个系统？... 许多系统边界常会发生争议，产生扯皮现象。我认为不应该由 “功能” 自身决定放在哪个系统，而应该是由 “功能所操作的数据” 来决定。数据的边界比较容易定义，判断原则是：1. 业务要求数据达到事务一致性 2. 业务允许数据最终一致性 3. 数据之间没有一致性关系。除了这三点，再佐以系统业务功能愿景（vision），就可以规划得比较好。
3. 人们太在乎信息，太忽略知识，所以猛看新闻，却不看书；信息带来的是表浅的片段化知识。拥有再多的片段知识，还是比不上联结成体系的系统化知识。当遇到新问题时，如果片段知识中没有，就解决不了；而系统化知识却可以通过推理等方式，为新问题找到解决方案，并让知识延伸，强化，甚至进化。
4. 有个方法可以让你写出完美专利：写专利时，幻想专利审查员和你有私人恩怨，你的挫折就是他的喜悦，他一心想在你的专利申请中挑毛病，害你失败。而申请通过之后，邪恶的软件帝国对你的发明内容感到惊艳，想采用但又很抠门不想支付授权费用，只想绕开 ... 有了这两个假想敌，专利会写得更好。
5. 把问题转化成分析模型，可以帮助你更好地看清楚问题，自然也就比较有机会想出适当的解决方案。解决方案是设计模型，这是分析模型在经过某种转换后的结果，具有可实施性。... 这整个过程靠的就是抽象化的能力，这是一种使用范围很广的能力，不局限在软件开发领域。
6. 一个系统内的接口分成两种：1. 可以被外部调用的接口 2. 仅供内部调用的接口 ... 除了基于安全的原因之外，分成这两类接口主要是因为设计的关注重点不同。 第一种比较关注网络传输的效率以及接口规格的不变性，第二种比较关注代码复用性。
7. 根据系统属性的不同，我把接口分成三类：资源接口、服务接口、应用接口。资源接口数目少，但参数多；服务接口数量多，但参数少；应用接口数目少，参数也少
8. 软件架构设计的六原则： 1. 你架构的对象是产品，而非项目 2. 专注非功能性需求，而非功能性需求 3. 尽量延后设计决策 4. 拥抱变化、预见变化 5. 设计架构时要心怀开发、测试与部署 6. 设计完系统后，组织结构必须跟著调整，因为组织结构常会影响应用架构 ... By Murat Erder and Pierre Pureur
8. 六种领导风格：威权型、教练型、联系型、民主型、领先型、高压型。领导者能展现的风格越多越好，熟练四种风格以上（特别是威权型、教练型、联系型、民主型），且能够视情况在各种领导风格之间游走者，能够让团队具有最好的工作气氛和绩效。... 语出 Daniel Goleman （EQ 之父）
9. 学习软件架构设计时，我建议先从各种「架构原则」和「架构风格」著手。如果一开始就直接接触各种架构模式，很可能会感到混乱。
10. 想当一个称职的架构师，我推荐阅读几本书《Design Patterns》、《Cloud Design Patterns》、《Patterns of Enterprise Application Architecture》、《Cloud Computing Design Patterns》、《Domain Driven Design》
11. 我认为设计一个现代化的开发框架要考虑到 1. 降低工程师的开发负担 2. 尽量限制工程师的不良习惯 3 帮助运营 ... 而「帮助运营」还可以再细分成三部分 1. 帮助在云平台上运维 2. 帮助大数据的收集 3. 帮助开放平台的建立
12. 一个好的应用框架就是要让开发容易。现在，在云时代，一个好的应用框架除了要让开发容易，还必须考虑到高并发、高可用、多活 ... 等运维方面的需求。也就是说，框架必须 Designed for Operations.
13. 你有两个 KPI 成绩，一个是公司打给你的，一个是你打给自己的 ... 后面这个比较重要 
14. 语法是最小的坎，库和框架是较大的坎，架构是更大的坎。只要用心，这些坎都能跨越 ... 但技术人员不懂老板的心在想些什么，这是一道跨不过的坎。
12. 想让系统灵活有弹性，可以通过配置（configuration）。简单的配置，只能设置一些常量，无法改变流程。这种情况下，如果想改变流程，就必须通过插件（前提是系统有事先设计插件的接入方式）.... 我不倾向于用插件，我倾向于用更弹性的配置来改变流程，这时候通常需要配合定义一个 DSL 。
13. 设计 DSL 的时候，我先想像自己是使用此领域语言的专家，且没有计算机编程能力，然后设想一个场景，再用最方便的方式描写此场景。描写方式尽量描述目的（What），而非描述做法（How）。几个场景的描述之后，就可以归纳出一个简单有弹性的 DSL。
13. 今天开始尝试著为这个开发框架设计一个 DSL （Domain Specific Language），动手实验看看是否能有突破。不过有别于我之前设计的 EDA 框架采用 Statechart Diagram 和 FSM Engine，这次的 DSL 是采用 Activity Diagram 和 Rule Engine。
1. 设计「开发框架」的任务之所以很难，是因为同时要具备 1. 系统架构能力 2. 详细设计能力 3. 抽象能力。
2. 能力好 => 不怕找不到工作 => 不怕失去现在的工作 => 不怕工作上犯错 => 愿意担负责任 => 拥有更多锻炼的机会 => 能力变更好 ... 这就是职场的正向循环
3. 虽然乔布斯跟我之间是天壤之别，但我能深刻理解他所说的：想做好一些事，避免不了要得罪一些人 
14. 环境可以帮助你进步，但环境无法阻止你进步。领导可以帮助你进步，但领导无法阻止你进步。项目可以帮助你进步，但项目无法阻止你进步。你可以帮助你进步，且你也可以阻止你进步 ... 你想进步，关键不在选择正确的环境、领导、项目，关键在选择正确的你。
15. 技术能力极好的人，通常都是高度兴趣导向且自我意识很强的人，因此可以专注在他们感兴趣的领域，持续投入研究，不管别人怎么说 ... 他们的缺点也很明显：因兴趣主导，他们做事的优先次序通常有问题，甚至会把重要紧急的事搁一边，只想做有趣的事。且因为自我意识很强，无法听进别人对优先次序的建议。
16. 建设「开放 API 平台」之前，最好先重构系统，否则可能会有几个问题：1. 在混乱的系统上包一层皮，API 粒度无法掌握，代码相当难实现 2. 系统内部混乱，导致效率问题，无法扛住开放后大量的访问 3. 系统混乱，导致 API 必须手工打造与设计，无法利用框架自动生成
17. 系统重构的流程![](http://ww3.sinaimg.cn/mw690/6037fd14gw1el792tea2rj213s0tuteh.jpg)
18. 一个好的架构性框架（Architectural Framework）至少应该做到两点：1. 提升开发效率 2. 限制不良的代码习惯
19. 很多问题的来源，都在于分不清楚「需要」和「想要」，「能做」和「想做」，「兴趣」和「憧憬」 
20. 这次回台湾又找长辈吃饭，跟他说了我的架构方法。他听了之后马上给两个方向的建议，都有可能会对我的架构方法产生重大影响。当然具体要怎么做，他不知道，我也还不知道。但思想的种子埋进土壤之后，或许有一天就会发芽。
21. 我的架构设计方法需要找一个简单又真实的例子做实际的讲解，以帮助学员更好理解。但真实的例子往往过于复杂，所以教材内这部分付之阙如 ... 这两天终于找到一个真实又有展示效果的例子，可以展现出 1. XYZ 模型的好处 2. API 和 SPI 的好处 3. 业务模型/资源模型/领域模型/数据模型 的差异 
22. 如何成长为架构师：1. 做过几个互联网项目 2. 做过几个传统企业项目 3. 多读一些架构的书和文档，试图吸取别人的养分 4. 多多和他人讨论架构问题，试图获取一些刺激 5. 总结这些项目、文档、讨论所带来的思维，试图归纳出一套可复用的模型与方法
23. 通过网上找各种破碎的信息、文档、博客、论坛进行特定领域的学习，还不如花几十元找一本好书，学习得更平滑、更快速、更精准。
24. 领域模型设计得抽象程度很高时，好处是：1. 更好理解 2. 接口简化 3. 保有很高的业务扩展弹性，可供以后使用 ... 「很高的业务扩展弹性」是有风险的，必须通过接口调用限制、权限系统等方式控制，否则很容易会产生严重的业务漏洞。如果领域模型被外界得知，容易被发现漏洞（如果有的话）而加以利用。
25. 许多领域模型设计的抽象程度相当高，把许多原本不同类但「关键点有共性」的对象整并成一类，因此可以得到比较精简的领域模型。这么做的好处是：用来操作领域模型的接口数目大大地变少了 ... 但每个接口的参数通常会变多，因为调用时必须指定许多细节，省略不得。前面省，后面就不能省。
26. 暴露核心层的接口设计，很可能就必须一同暴露领域模型设计。而领域模型设计又是一家企业内相当重要、需要保护的资产（基于商业竞争与系统安全考量）。所以一般只暴露服务层的接口，另一个原因是因为服务层的接口比较方便使用。
27. 领域模型属于核心层，上面提供了少数的基本操作接口，接口使用领域的词汇，每个接口的参数都相当多。通过核心层的这些接口，上面包装出一层服务层。服务层的接口使用接近业务的词汇，接口数量比较多，但每个接口的参数数量都比较少。
28. 我不觉得有「互联网系统」与「传统系统」的差别，我觉得只有「对外开放接口的系统」与「不对外开放接口的系统」的差别。
29. 从领域模型中，如果有某个领域概念（通常是名词）是许多信息的汇集点，我很可能就会把这个概念设计为一个核心层的系统；然后我会从领域模型的许多功能场景（Functionality Scenario）中分析，找出其上的服务（通常是动词）。这就完成了核心层与服务层的初步设计，接下来就容易多了。
30. 管理者想赢得程序员技术上的敬重，有几个方向：● 了解程序设计的艺术 ● 有很好的职业记录 ● 在技术上做些值得赞赏的贡献 ● 赶上新技术的趋势 ● 在技术或专业的社群中，扮演积极的角色 ● 展现强烈的个人价值 ... 出自《Managing the Unmanageable》
31. 计发现，超过 40 岁的人无法改变自己。想太多「我想要」，却没有思考「哪些习惯与个性阻挡我的发展」，于是不断试错。就算发现自己有「阻碍成长」的习性，大多数的人却希望「别人来配合我」或「此处不留爷，自有留爷处」，而不是想说改变自己才是正确的解决之道。... [推荐阅读](http://www.ithome.com.tw/node/82285)
32. 【问】：开发人员与产品经理之间的隔阂要如何打破？【答】：唯一的方法是鼓励他们交往！热恋中的人总是会百般呵护对方的。只要他们陷入恋爱关系，开发人员对产品经理提出的需求，有求必应；产品经理也只会对开发人员提出绝对必要的需求。
33. 我觉得生活中经常使用黄色便利贴的人，做事貌似都很规范有效率。你跟她们说一句话，她们立刻拿出便利贴写了东西贴到桌前；你跟她们问一句话，她们除了把答案告诉你，而且贴心地怕你忘记，立刻拿出便利贴写了东西交给你。
34. 如何通过微博塑造「技术大牛」形象：1. 看到新技术发表时，就写微博说「我在三年前已经预测到了这趋势」 2. 到 Amazon.com 上挑大家评价很好的的技术英文书，写微博推荐，彷佛自己已经读过 3. 微博中尽量提到大数据、分布式、高并发、架构 4. 告诉大家昨晚你找出某开源软件中一个严重的 Bug 并修复了
35. 在我的归类中，SalesForce 的 API 是核心层的（较底层，接近数据库），而淘宝的 API 是服务层（较上层，接近应用）。... 好像很少看到有 API 同时支持高层与低层。
36. 数据库就像是内脏，框架就像是骨架，代码就像是肌肉，UI 就像是皮肤。... 系统重构或设计新系统时，我会先把时间都花在内脏与骨架上。
37. 知道是一回事，做又是一回事。「Less is more」大家都会说，但真正到自己做决策时，多数人却还是很难做减法，因为风险太大，抗争也太大。只要还过得去，一般不会采取减法，而是反其道用加法。通常只有在陷入很深的危机时，才会孤注一掷这么做。但结果也很难预料，Apple 成了，而 Nokia 却似乎 ...
38. 我觉得 KPI 应该是好东西，但应该有粗细之别。对某些人或某些职位来说，KPI 可以数据化，定得比较细。但对于某些人或某些职位来说，KPI 应该是指定方向为主，而不是详细到数据化，否则通常会得到消极的应付，最后是在不理想的情况下达到了 KPI，但却错失一些更好的机会（不在 KPI 中的）。
39. 想要做的，企业合作+孵化创新-》平台强化， 需要依靠首席架构师的的架构设计能力，以及团队的执行力
40. 平常的时候工作，重要任务优先。加班的时候工作，紧急任务优先。休假的时候工作，有趣的任务优先。
41. 创业团队的负责人必须提升自己的面试技能，以找出适合项目的人。这个时候，更多的是倚赖自己的判断力，而不是依赖考卷考题。
42. 設計此 PPT 時，我用到一些技巧：1. 圆角框比尖锐框更舒服 2. 红绿蓝三原色区隔效果明显，降低他们的饱和度，以免冲突太大 3. 粗框箭头在白底图中很突出，可以一眼看见流程 4. 说明放在右下可让视觉重量平衡，且格式塔（Gestalt）效果使得这直列说明延续上面的黑线，整体形成一个完整的正方形。
43. 看程序员简历时，单纯就技能来说，我会粗略地把技能分为 ◆ 语言 ◆ 框架/API ◆ 领域/行业 ◆ 工具，这四大类。岗位要求与技能的匹配程度排序为： 领域/行业 > 框架/API > 语言 > 工具
44. 从员工到老板，大家心中都存在着大大小小的委屈，觉得自己吃亏、被误解、被埋没、被忽略，或是努力之后却没有收获。管理专家最近发现，阻挠企业效率，甚至造成团队负面心理的最大关键，在于委屈与不满所造成的「热诚消失」问题。
45. 出来混，总是要还的。想让程序员之路走的顺利一点，非科班出身的程序员至少要把下面这些知识补足：(1) 数据结构与算法 (2) 编程语言原理 (3) 操作系统原理 (4) 数据库原理 (5) 网络与HTTP协议。
46. 最近在写一个小程序，跟大家分享我的作法 (1) 先将REST API包装成低级函数 (2) 将低级函数包装成高级函数 (3) 将高级函数包装成语义模型/领域框架 (4) 为此领域框架建立DSL (5) 使用DSL编写代码。
47. //@蒋涛CSDN:按照80-20法则，80%的程序员几乎不看书，不读Blog，不参加技术会议，不持续学习。这些人也可能会进入大公司，他们日复一日的做着重复的工作。另外20%则在专业方面比较主动，他们喜欢阅读，喜欢学习，喜欢参加技术活动。这20%当中又会有80%的人可能不会特别成功，