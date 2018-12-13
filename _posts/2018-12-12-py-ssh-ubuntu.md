---
layout: post
title:  python连接ubuntu的ssh
date:   2018-12-12 17:11:00 +0800
categories: 教程
tag: python
---

* content
{:toc}


一 虚拟机连接  
===================================
如果是虚拟机的ubuntu，需要把VMware的虚拟网卡设置为和ubuntu的ip在一个网段。设置完以后可以ping一下看看能不能ping通

二 ubuntu上安装ssh服务  
===================================
默认情况下往往是没有安装的可以按照下面的步骤排查 

1.ps -e \| grep ssh

查看ssh有没有开启，如果没有sshd的字样，说明SSH服务未开启或者没有安装

2.sudo service ssh start

如果显示Fail to start 那么就说明没有安装

3.sudo apt-get install openssh-server

安装完之后一般默认是开启的，自己查看一下

三 查看防火墙  
===================================
如果还有问题则可能是防火墙的问题，可以使用下面几个命令
service iptables stop  //关闭防火墙
 
sudo ufw disable #关闭防火墙
 
sudo ufw enable #开启防火墙
 
sudo ufw status #查看防火墙状态

四 尽量不要使用root登陆           
===================================
如果使用root登陆的话，xshell会报以下错误：ssh服务器拒绝了密码，请再试一次
不建议使用root登陆，如果非要使用可以参考下面的文章[CDSN](https://blog.csdn.net/fanren224/article/details/70862346)
