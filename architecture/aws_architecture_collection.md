# 亚马逊的架构
更新日期：2016年4月25日

【亚马逊CTO总结的10个教训】里面，amazon提到了API的重要性。我觉得AWS应该跟我们类似依赖了amazon的一些基础的比如账号，另外的一些可能是自己AWS自己做的，也有可能是依赖Amazon的中台系统的比如资金账户、订单交易等等。不管是哪种方式，aws/amazon都要面对一个将一个大的业务系统关联起来的问题。[亚马逊的云服务会吞噬美国的IT产业吗](http://www.d1net.com/cloud/xaas/397122.html) 这篇文章虽然不是讲amazon的系统架构的，但其中一段话谈到了Amazon是如何通过API治理他们的架构的。我的结论就是 *API是Amazon解决系统架构的问题一个抓手*


### 亚马逊的技术架构是怎么样的？

原文地址:[http://www.zhihu.com/question/20105139](http://www.zhihu.com/question/20105139)


### 亚马逊的云服务会吞噬美国的IT产业吗

原文地址:[http://www.d1net.com/cloud/xaas/397122.html](http://www.d1net.com/cloud/xaas/397122.html)

	2002年 前后，贝索斯给所有员工发布了一个命令，关于内部软件设计的命令：

	1）所有团队，要把他们的数据和软件功能通过服务接口对外公开

	2）团队之间的沟通只能通过这些接口。

	3）不允许通过任何别的方式通讯：不能直接连接，走后门，不能直接读别的团队的数据，不能共享内存。

	4）服务接口的后端的软件技术的选择，没有关系。

	5）所有的服务接口设计时，都必须具备一个能力，允许日后让外界第三方开发者调用。没有任何例外。
	

### 亚马逊CTO总结的10个教训
原文地址：[http://blog.jobbole.com/99540/](http://blog.jobbole.com/99540/)

	1. 搭建可进化的系统
	2. 接受一切意外
	3. 用原语，不用框架
	4. 自动化是关键
	5. 恒久的API
	6. 了解你的资源使用情况
	7.  自底向上内建安全机制
	8.  加密是一等公民
	9.  网络的重要性
	10.  没有看门人

