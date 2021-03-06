# 高效的数据科学团队如何建设
原文地址:[http://www.sohu.com/a/67130905_308467](http://www.sohu.com/a/67130905_308467)


ETL - Extract Transform Load 抽取 转换加载，代表从源数据清洗加工到数据仓库的过程。

这篇文章在Hacker News转载后产生很热烈的讨论，主要是从工程师的角度来看问题，讨论了很多有关人员管理和团队分工等一些很现实的问题。不是所有人都同意文中的观点和解决方案，也有很多人写出了自己的经历来佐证作者的想法。争议主要在于ETL工程师的工作价值以及不同职责间的分工问题。

“您的团队和贵公司数据科学家之间关系如何？”我在面试数据平台工程师时，这绝对是我听到的最多的一个问题。这是个好问题，提问者可以有效的衡量这个新职位的好坏。我很乐于回答这个问题。不过我宁愿这个问题不出现，因为面试者往往是因为怀疑或者害怕才问的。

为什么呢？去看看硅谷铺天盖地的数据科学方向的招聘启事，你可能会觉得数据科学家和工程师之间很有合作精神和创新精神，简直就是形影不离。

然而现实很残酷，这种状况很少发生。在大多数公司中，数据科学家和工程师之间的合作经常是低效率的，有时甚至形同陌路。

◆ ◆ ◆

大多数公司将他们的数据科学部门分为3组：

* 数据科学家：搞统计的里面编程最好的，搞编程的里面统计最好的。也称为“动脑的”。

* 数据工程师：搭建“管道”，为数据科学家输送数据，从数据科学家那里获得想法，然后执行出来。也称为“干活的”。

*  基础设施工程师：维护公司的Hadoop集群或者是别的大数据基础设施。也称为“管道工”。

数据科学家总是嫌弃数据工程师的执行效率太低，而且工作周期、路线图和动机不协调。在数据工程师将他们第一个版本的想法放到A/B测试时，他们的第二个和三个版本的想法已经出来了。数据科学家的抱怨是完全有道理的。

数据工程师总是嫌弃数据科学家写代码又差又慢，从来都不考虑把这些想法投入产品中会产生多大的后续影响。还嫌弃这些“动脑的”总是提出一些不切实际的要求，最后的结果也并没有多么好......他们的抱怨还有很多，这里就不一一赘述了，你懂的。

基础设施工程师的情况也好不到哪里去。所有的人都往集群的磁盘上堆积数据，很快就需要清理了。平时他们没有机会接触上面的两类人，对于他们如何使用这些基础设施，以及这些人要解决的技术或业务问题并不是很了解。这让他们在解决问题提高当前境遇时觉得自己微不足道。这时候，他们就限制大家对基础设施的使用。这样一来，只能让其他人对他们更加恼火。

一个恶性循环就这样产生了。

◆ ◆ ◆

这个循环里的所有人都知道当前的工作状态其实不怎么样，现阶段的大规模招聘的工作内容也很可能一般。为什么不解决这个问题？为什么所有的数据科学和算法开发部门都会陷入这个恶性循环？为什么？！

我主要怪下面两个事情

最近五年里，数据处理工具和技术获得了飞速的发展。除非你需要处理PB级别的数据，或者每天要处理千亿级的事件，现阶段大多数技术已经能轻松满足你的需求了。

除非你想把现有技术级别再推进一层，一般来说你是不需要一组专业工程师在这些技术上层构建解决方案。如果你成功的招聘到了这样的人，他们很快就会觉得无聊。如果他们感到无聊，他们绝对会很快抛弃公司投入谷歌、脸书、领英（译者注：国内同理百度、腾讯和阿里）这类公司的怀抱。在这里，他们的专业技能才会真正被需要。如果他们做的还挺开心的，最大的可能就是他们非常平庸。水平一般的工程师最擅长的事情就是把复杂的事情搞得更复杂，制造出一团他们称作“解决方案”的乱麻。因为越复杂的事情越需要专家。

那必须的，“动脑的”听起来才比较酷炫呀！每天你就坐在那里，想想怎么把事情做的更好，然后把自己的想法甩手给那些急迫的想把你的想法变成产品的人的手中。我敢说你在街上随便找一个人跟他说一下这个工作情况，他都会瞬间接受的！数据科学家，尤其是刚入行的新人们，都拼命想把自己的工作变成这个美好的蓝图。

那是因为我们已经把这个想法根植于他们心中。为此，我们应该感谢已经存在了多年的大公司，他们在大数据风潮出现之前已经成立了商业智能部门......

一个传统的商业智能部门有以下三个人设：ETL工程师，报告开发者，数据库管理员。ETL工程师负责把数据放入数据仓库，最能让他们着迷的就是各种数据建模,比如Kimball的维度建模方法。报告开发者的职责就是用一个专业的工具（比如Microstrategy和现在大热的Tableau以及Qlik）设计出展示各种数据的图表报告，他们是专家。数据库管理员（和其他工具管理员）的主要职责就是让所有的工具保持运作、不出任何问题。

你可能也发现了，在这个设计中所有人都是“干活的”。在大约10年前，大数据和数据科学刚刚成为流行语时，已经有非常成熟的商业智能部门了。在这些部门里，“干活的”比较多，但“动脑的”不够。所以就专门为“动脑的”设置了一个岗位。我们把数据科学家和商业智能部门整合在一起，保证他们有能力自由摆弄数据和直接改变公司业务。聪明的读者你可能已经猜到了，现实并不是这样的。这些数据科学家偶尔可以做出一些不错甚至酷炫的东西出来，但是大多数时候，他们的工作仅仅是水平高一点儿的报告开发者。

但是数据工程师这个岗位听起来真的好有吸引力，很多人争相应聘。所以这既传统又现代的数据科学部门横空出世：数据科学家（报告开发者，“动脑的”），数据工程师（ETL工程师，“干活的”）和基础设施工程师（数据库管理员，“管道工”）。

咦？好像商业智能部门兜兜转转但是本质并没有变，仅仅是把Hadoop集群加进去就摇身一变有了新名字。

◆ ◆ ◆

这取决于你的目标是什么。如果你同意我上面的观点，那这个运行方式已经存在了很多很多很多年，从商业智能出现的时候（对于硅谷来说简直就是远古时代，译者注）。但是我坚信这个方式是非常低效的。除了做幻灯片和好看的数据面板之外，你的数据科学部门应该有更大的抱负！

最根本的问题就是这个方案假设有一大批杰出的工程师，他们迫切的想实现数据科学家的想法，而这个假设与现实情况相去甚远。如果你认识这样有才华的工程师，记得给我打电话哈。

在这个方案中，如果出现系统或者实现的问题，责任都在“干活的”身上。如果项目成功了，那最后功成名就的是“动脑的”。这是现阶段各个角色无法调和的根本问题。

如果你想招到真正的工程师人才去做“干活的”角色，你的业务规模需要非常大才会让这些人才获得解决问题的快感。你需要因“大数据”的出现才造成的问题。不过请你扪心自问一下，究竟自己有没有大数据。很不幸，你根本就没有！

那么你只能去找一些资质平庸的工程师。他们会让你的项目更加复杂，还记得上文的恶性循环嘛？最后的结果就是有一组数据科学家，他们只能做一些以前报告开发者做的事情，因为并没有一个创新的、稳定的数据平台帮他们实现想法。但是如果你的招聘启事上侧重于实现的方面，这些人绝不会来应聘的。毕竟他们是“动脑的”，又不是“干活的”！

◆ ◆ ◆

与其试图模仿知名企业的固有框架，我们更需要创新和发展新的模式！

几年前，我就是为此加入了Stitch Fix。在Stitch Fix，我们力争做出世界上最好的算法和分析。我们试图用我们的成果引领商业潮流。除非你愿意大胆质疑、重新思考你认为不好的事情，否则这是一个很难的完成的目标。

看着我们的部门过去两年的成长，我很有信心来分享一下我们在做些什么。

我们的目标是引领，而不是简单的开发，我向你推荐一个我认为能更好地搭建数据科学部门的方法。这个方法可以更好地达到角色自治，每个人真正拥有从头到尾的任务所有权，并为最终的投产和结果担起责任。这个方法最适合那些拥有快速发展的商业模型（或数据模型）的公司。

下面是一个创建高效运转、引领创新的数据科学团队的蓝图，它是通过统领思想、APIs和代码一起产生的，而不是被业界的变化牵着走，也不是为了试图重新定位而被迫生硬地组合着PPT演示稿。

◆ ◆ ◆

让我们暂时忘掉传统的角色，想想什么样的动机能让人们在每天清晨兴奋地来上班。

无论是什么角色，凡人和伟人间一个重要区别是他们对于创造的渴求和创新的能力。伟人能够发现问题并创造性地解决问题，这使他们远离平庸。他们在一个能够自治、拥有所有权、能够专注的环境中表现卓越，并且他们渴求这样一个环境。

组装线的模式恰恰造成了截然相反的环境，等于把数据科学家的手铐在工程师身上。（事实上，“动脑的”也讨厌自己要依赖“干活的”）。关键就是要营造一个每人都能拥有自治权、任务所有权和能够专注的环境。

我们还要认识到，让数据科学家和工程师慷慨激昂的工作类型是非常不同的。

数据科学家：数据科学家喜欢解决那些与业务纵向连接的问题，那些通过他们的努力能够对组织或项目的成功产生重大影响的问题。他们致力于优化某些事情或进程或从头开始创造一些东西。这些都是点导向问题，他们的解决方案也是点导向的。他们通常涉及到业务逻辑的重新组合，重新思考问题该如何解决，和如何创新。因此，他们需要深入了解业务的具体部分是如何操作的，并且与垂直业务部门保持高度合作关系。

数据工程师：工程师擅长于做抽象和概括的工作，并在被需要的地方找到有效的解决方案。这些问题通常是横向性质的。当可以广泛应用的时候，它们是最有影响力的。他们需要很好的、全面的了解业务是如何运作的，但是解决方案的抽象性质意味着他们不需要对业务逻辑有太深的了解，也不需要与业务部门深度合作，或是深入理解业务的纵向市场。

◆ ◆ ◆

在数据领域中，工程师们常常担心，无论你的职位描述是什么，你其实是想偷偷地招聘一个ETL工程师。

以防你还没有意识到这一点——没有人喜欢书写和维护数据管道或ETL。这是业界谁都不愿意干的。ETL工程师就是平庸的代名词，这实在不是什么值得惊讶的事儿。

工程师不应该做ETL。这就不应该是一个专门的角色。没有什么比写代码、维护、修改和支持ETL来产生一些自己永远不会用到的数据更消耗人的精神了。

相反的，应该给人们工作从终端到终端的所有权（自治权）。对于数据科学家来说，这意味着对ETL的所有权。这也意味着数据分析和数据科学产出的所有权。数据科学家努力的最好结果的消费者应该是机器，而不是人。不是一份报告、数据面板或PPT，它应该是某种算法或API，被整合到工程栈 ——从根本上改变企业的运作。自治权是指数据科学家拥有该代码。从开始写代码到最后投入使用。他们应该能够不需要工程师的许可就可以进行研发和调配，并负责到底：产品的性能，延迟和SLA要求等等。

这使得纵向责任和焦点直截放到数据科学家的手中。但是，数据科学家通常不是训练有素或者高度熟练的软件工程师。你顶多可以说他们是”水平尚可”。所以，你会认为他们会造成很大的混乱。

这就是为什么ETL和API/算法投产开发通常被流水线式地移交了工程师。但是，所有这些任务本质上是纵向（点）定向。在数据领域才华横溢的工程师几乎都是专注于横向应用的。

所以，那么在这个新的、横向的世界中一个工程师的作用是什么呢？概括起来，工程师们必须能部署平台、服务、概念和框架，使数据科学家来能够自由的构想、开发和实现他们的想法（如工具、框架、或用于构建、安排、执行ETL的服务）。我喜欢用乐高积木的角度去思考它。工程师设计新的乐高积木块，数据科学家用创造性的方式来组合积木，创建新的数据科学产品。这谈何容易，但是：

工程师的工作本质上是水平方向的。这使他们能够专注于构建广泛应用于跨多个数据科学问题的技术。这最大限度地发挥了工程输出的杠杆作用。这很棒，因为在你的数据科学部门里数据科学家可能比工程师多很多。

工程师们专注于自己最擅长的：抽象、概括、创造高效的、可升级的解决方案。

工程师可自主操作，不受他人影响。从工程团队以这种方式部署的生产应该像“魔术”一样。对于数据科学家来说，事情就应该是“水到渠成”的，因为他们的需求能够被预料到，他们所使用的的平台、服务和框架都被妥善的照顾着。

为了使这些可以顺利进行，大部分时间里工程师需要预测到数据科学家的需求。他们应提前制定多个步骤。

对于才华横溢、创造力非凡的工程师和数据科学家来说，这样太有趣了。

◆ ◆ ◆
完全不是这样的。如果有这样的事情话，工程师的角色比标准模型中角色更具有挑战性，要求也更高。数据科学家也是一样的。我们并不是为了效率来优化组织，只是为了优化自治权。这能够明确想法的所有权和传递责任。

这些角色对于那些拥有企业家精神的人吸引力是巨大的。它使快速运转成为可能，消除了那些达成不必要共识的需要，并为破坏性创新打开一扇大门。但它的确是以专业化和效率作为代价的。

然而，我们并不是期望数据科学家突然成为优秀的工程师。也不希望工程师完全不了解业务逻辑和垂直举措（vertical initiatives）。实际上，合作是这个模型取得成功所必须的。工程师们需要建立防线，来防止数据工程师掉进陷阱，产生一些不能扩展的、不可靠的解决方案。

在没有得出解决方案的框架前，工程师要与科学家合作来开创解决方案。而不是甩手不管。工程方面的挑战是建立自服务组件，例如数据科学家可以自主的重复业务逻辑和算法，将他们的想法应用到业务中。有了最初的的解决方案后，谁拥有什么就很清楚了。工程师拥有他们建立的基础结构，数据科学家拥有业务逻辑和算法实施方案。这就不需要重复任何紧密耦合。

◆ ◆ ◆

此时，你可能会怀疑是否能够实现这种合作方式。然而，我认为值得冒险。以下是可能会妨碍进步的几个方面，需要注意：

人们是不愿意改变的。人们总是倾向于重新创造一个他们原本熟悉的工作环境。这就会对恢复“动脑的”-“干活儿的”（Thinker-Doer）模型产生压力。新雇员需要快速熟悉新结构。

当项目遇到困难时更要保持警惕，例如，API断裂或者算法产生了不好的结果。

人们在这些情况下表现非常敏感。他们会坚持工程师们应该承担责任。但是，他们是在强调表面现象而不是问题。工程师们应该建立更好的平台支持、可视化、概念（abstractions）和弹性（resilience）。并且，他们应该意识到工程师们也会犯错——没有人不犯错。

平台工程师先于数据科学团队考虑问题是非常必要的。你需要非常机警的平台工程师，他们凭直觉就能决定将来什么地方需要什么服务、框架和技能。没有从科学家到工程师的传送过程，意味着工程师们没有对科学家们提出的要求作出及时的反应。

记住，工程师们是在创造乐高积木，数据科学家团队是在组装他们。如果数据科学家团队不需要纠正积木而只是组装，他们就会一直努力直至创造出解决方案。他们会通过组装错误的积木（把方块放到一个圆洞里），或者创造他们自己的积木来解决问题。一般他们会陷入混乱（Big Mess）。原因是一旦被创造出来就很难被撤销。

◆ ◆ ◆

让数据科学家拥有更多权限，其中一个后果就是他们可能无法像工程师一样写出有效的代码或解决方案。我们为了速度和自主权牺牲了技术效能。意识到这是一个深思熟虑后的权衡，这很重要。

然而，很明显，从终端到终端的所有权（自治权）效率较低。数据科学家是他们的解决方案的实施领域里的专家。因此，他们很容易在技术成本、支持成本与要求之间做出权衡。

例如，他们可以决定在特定位置取样，在适当的位置使用合适的方法，并做出增加某些特征的决策，即使这个决策花费了高昂的开发成本，却只产生了微不足道的业务影响。这在科学家和工程师的装配线式合作模型中基本不可能发生（如果他们非要这样做，通常需要无数轮谈判）。

总的来说，我们希望允许数据科学家拥有自主权和创新产生的结果能够弥补因缺少技术专业性而带来的低效。

◆ ◆ ◆

我并不认为我们已经发现了构建数据科学部门最好的架构，也不认为对于你的组织来说这是最好的架构。但是，我认为这对于Stitch Fix（作者JEFF MAGNUSSON所在公司）来说这是一个更好的解决方案。

我真诚的希望分享我们的做法能够鼓励那些非传统架构的部门也进行这样的尝试，鼓励数据科学部门的负责人不受拘束的思考，鼓起勇气去挑战传统，告诉那些对传统角色非常失望的工程师和数据科学家，有不同类型的工作环境等待着他们的加。