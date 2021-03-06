# 《软件架构设计》摘录

我总结的框架的定义是：框架是可以通过某种回调机制进行扩展的软件系统或者子系统的半成品。

首先，框架是半成品，这是他和其他所有软件组件的本质区别。这涉及到“软件重用”的一对内在矛盾：“重用几率”大小和“重用所带来的价值量”大小之间的矛盾。简言之，软件单元的粒度越大，则重用所带来的价值量越大，但重用几率越小；反之，粒度小的软件单元被重用的几率越大，则重用所带来的价值量越小。框架的智慧在于此：为了追求重用所带来的价值量最大化，将容易变化的部分封装成扩展点，并辅以回调机制将它们纳入框架的控制范围之内，从而在兼顾定制开销的同时使被重用的设计成果最多。

框架不一定都必须用面向对象编程语言实现，如C语言等传统编程语言可以通过函数指针作为参数来实现回调机制，而面向对象编程语言利用抽象方法。

可以将框架分为技术框架和业务框架。 技术框架致力于解决某一技术领域的通用技术问题，并提供定制和扩展机制。例子很多，例如Hibernate就是解决ORM问题的技术框架。 业务框架则是特定业务领域内通用的框架，比如工作流领域的框架、CRM领域的框架。

《面向模式的软件体系结构（第一卷）》

框架是一个可实例化的，部分完成的软件系统或子系统，它为一组系统或子系统定义了架构，并提供了构造系统的基本构造块，还为实现特定功能定义了可调整点。在面向对象环境中，框架由抽象类和具体类组成。

《设计模式》

框架是构成一类特定软件可复用设计的一组相互协作的类。例如，一个框架能帮助建立适合不同领域的图形编辑器，像艺术绘画、音乐作曲和机械。另一个框架也许能帮助你建立针对不同程序设计语言和目标机器的编译器。而再一个也许能帮助你建立财务建模应用。你可以定义框架抽象类的应用
相关的子类，从而将一个框架定制为特定应用。

框架规定了你的应用的体系结构。它定义了整体结构，类和对象的分割，各部分的主要
责任，类和对象怎么协作，以及控制流程。框架预定义了这些设计参数，以便于应用设计者
或实现者能集中精力于应用本身的特定细节。框架记录了其应用领域的共同的设计决策。因
而框架更强调设计复用，尽管框架常包括具体的立即可用的子类。

这个层次的复用导致了应用和它所基于的软件之间的反向控制(inversion of control)。当
你使用工具箱(或传统的子程序库)时，你需要写应用软件的主体并且调用你想复用的代码。而
当你使用框架时，你应该复用应用的主体，写主体调用的代码。你不得不以特定的名字和调
用约定来写操作地实现，但这会减少你需要做出的设计决策。

你不仅可以更快地建立应用，而且应用还具有相似的结构。它们很容易维护，且用户看
来也更一致。另一方面，你也失去了一些表现创造性的自由，因为许多设计决策无须你来作
出。

如果说应用程序难以设计，那么工具箱就更难了，而框架则是最难的。框架设计者必须
冒险决定一个要适应于该领域的所有应用的体系结构。任何对框架设计的实质性修改都会大
大降低框架所带来的好处，因为框架对应用的最主要贡献在于它所定义的体系结构。因此设
计的框架必须尽可能地灵活、可扩充。

更进一步讲，因为应用的设计如此依赖于框架，所以应用对框架接口的变化是极其敏感
的。当框架演化时，应用不得不随之演化。这使得松散耦合更加重要，否则框架的一个细微
变化都将引起强烈反应。

《Webwork In Action》

在 Rickard berg（WebWork 的创造者和JBoss 创始人之一）构建最原始版本
WebWork 的时候，他曾经说过：“框架的强大之处不是源自它能让你做什么，而是它不
能让你做什么。”Rickard 所说的话解释了什么是框架：框架使混乱的东西变得结构化。
而Web 应用程序框架则鼓励开发人员使用一系列框架所提供的基础类和类库，从而避免
杂乱的JSP 所造成的混乱。

我们再来打个比方。框架就像是一间有很多屋梁的房子，当你需要扩建房子的时候，
譬如增加新的房间、窗户和过道或者在卧室增加一个壁炉，由于屋梁的限制，你并没有
什么其他的选择。虽然较少的屋梁和架构会让你有更多的选择，但是当台风来袭或者发
生地震的时候，你让家人住在这样一间只有屋顶的房子里，恐怕不会觉得安全吧。总之，
框架是在结构和创造力之间的一个精确的天平。

由于框架要求更多的结构，你的创造力所拥有的发挥空间开始收缩了。一种极端是
框架消失了，一片混乱；而另一种极端就是框架留给你的选择是如此之少，以至于你无
法完成你的应用程序。很明显，一种完美的中间状态存在于这两个极端之间的某一处，
而这种中间状态就是WebWork 和所有其他MVC 框架所梦寐以求的。

《应用框架的设计与实现——.NET平台》

框架通过预先把众多组件组织在一起的方式，封装了处理流程的控制逻辑；因此开发者就不用控制逻辑来组织组件之间的交互了

