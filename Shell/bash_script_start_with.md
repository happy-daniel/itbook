# bash脚本文件中为什么以#!开头
原文地址[http://blog.csdn.net/jubincn/article/details/7281174](http://blog.csdn.net/jubincn/article/details/7281174)

在每个bash脚本的开头都使用"#!"，这用来告诉系统此文件的执行需要指定一个解释器。在“#!”之后接着是一个路径名，这个路径名指定了一个解释脚本中命令的程序，这个程序可以是 shell，其它编程语言或任意一个通用程序。这个指定的程序从头开始解释并且执行脚本中的命令(从#!行下边的一行开始)

\#! 后边给出的路径名必须是正确的，否则将会出现一个错误消息,通常是"Command not found"，这将是你运行这个脚本时所得到的唯一结果。当然"#!"也可以被忽略,不过这样你的脚本文件就只能是一些命令的集合，不能够使用 shell 内建的指令了。

在#!后边需要一个空格#! /bin/sh
