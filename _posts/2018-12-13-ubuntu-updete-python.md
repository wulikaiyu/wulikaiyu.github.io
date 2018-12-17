---
layout: post
title:  ubuntu升级python 
date:   2018-12-13 T18:20:00
categories: 教程 
tag: Linux
---

* content
{:toc}

更新版本
===================================
正常情况下，你安装好ubuntu16.04版本之后，系统会自带 python2.7版本，如果需要下载新版本的python3.5，就需要进行更新。下面给出具体教程：

1.首先在ubuntu的终端ternimal输入命令：
	
```shell
1 sudo apt-get install python3
```
	
（博主选择的是安装python3.5,命令为：sudo apt-get install python3.5）

输入你的密码后会下载，刚才下载的Python程序被安装在usr/localb/python3.5 中。

2.指定默认打开的是python3.5版本（你新安装的python版本）。

安装完成之后，你在终端中输入python，输出的信息里面会提示是2.7版本的，也就是说默认打开的并不是刚才安装好的3.5，所以还需要我们重新修改一下链接。方法如下：

第一步：先备份原来的链接（在对系统执行删除之前进行备份是个好的习惯）。在ternimal下输入命令：

```shell
1 sudo cp /usr/bin/python /usr/bin/python_bak 
```

第二步：删除原来默认指向python2.7版本的链接。在ternimal下输入命令：

```shell
1 sudo rm /usr/bin/python 
```

第三步：重新指定新的链接给python3.5版本。输入命令：

```shell
1 sudo ln -s /usr/bin/python3.5 /usr/bin/python 
```

至此，python版本更新已经完成。

回到原来版本
===================================
另：python2.7和3.5版本之间随意切换（这里3.5切换回2.7版本）：

```shell
1 sudo rm /usr/bin/python
2 sudo ln -s /usr/bin/python2.7 /usr/bin/python
```

使用声明 
===================================
该教程原作者老王头，具体链接为
[CSDN](https://www.cnblogs.com/wmr95/p/7637077.html)