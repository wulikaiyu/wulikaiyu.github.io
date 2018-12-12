---
layout: post
title:  pymysql使用总结 
date:   2018-12-10 17:11:00 +0800
categories: document 
tag: 教程
---

* content
{:toc}


一 数据库编码  {#start}
===================================
我们常见的编码形式有unicode，utf-8等等，pymysql目前版本用到的编码形式是utf8mb4。如果编码错了会有很大麻烦，数据库里的文字都会变成一些意想不到的乱码。当然如果只使用英文应该问题不大

二 输入密码  {#start}
===================================
如果不想把密码用明文表示，可以使用如下代码
pwd = input('password:').strip()

三 con.ping(reconnect=True)  {#start}
===================================
执行sql语句之前上面的代码，不然会报一下错误
pymysql.err.InterfaceError: (0, '')

四 con.commit()            {#start}
===================================
sql语句之后，需要加入提交这行代码，不然增删改查的语句不会生效。