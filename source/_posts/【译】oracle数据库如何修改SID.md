---
title: 【译】oracle数据库如何修改SID
date: 2017-11-24 22:52
tags:
---

今天回家想继续做项目，发现电脑系统重装后没有装上oracle，于是下载了express edition的oracle，由于是首次用这个版本，碰到了一个问题，SID默认是XE，而我项目中jdbc的SID是orcl，于是上网搜索修改SID的教程，搜了很多中文的教程发现几乎都是一样的内容，一股脑儿复制粘贴，也不管别人看了文章是否能真正的解决问题，也许是我水平不够，并没能看懂到底如何修改。于是尝试在google搜索英文教程，最终在stackoverflow上找到了答案成功修改了SID，在此翻译一下分享教程，希望可以真正帮到需要的人。

原文链接：[How can I change the SID of an Oracle XE instance](https://stackoverflow.com/questions/410951/how-can-i-change-the-sid-of-an-oracle-xe-instance)

_注1： \[XE_HOME\] 指： C:\\oraclexe\\app\\oracle\\product\\10.2.0\\server （视oracle安装目录不同有所差异）_

_注2：所有语句均在windows命令行进行_

#### 一.配置SPFILE（旧文件可以删除）

> 1.copy \[XE\_HOME\]\\dbs\\spfileXE.ora \[XE\_HOME\]\\dbs\\spfileNEW\_SID\_NAME.ora
>
> 2.copy \[XE\_HOME\]\\database\\initXE.ora \[XE\_HOME\]\\database\\initNEW\_SID\_NAME.ora
>
> 3.编辑\[XE\_HOME\]\\database\\initNEW\_SID_NAME.ora：里面内容应该是：
>
> SPFILE='\[XE\_HOME\]\\server\\dbs/spfileNEW\_SID_NAME.ora'

#### 二.停止旧service，以新的替代

> 1.sqlplus / as sysdba 然后执行 shutdown
>
> 2.lsnrctl stop
>
> 3.oradim -new -sid NEW\_SID\_NAME -startmode auto -pfile \[XE\_HOME\]\\database\\initNEW\_SID_NAME.ora
>
> 4.oradim -delete -sid XE
>
> 5.lsnrctl start

#### 三.更新环境变量中的ORACLE_SID

#### 四.使oracle为监听器注册

> 1.sqlplus / as sysdba
>
> 2.execute alter system register;
>
> 这一步可能会遇到ora-12560错误，可以尝试通过以下语句解决：
>
> oradim -start -sid NEW\_SID\_NAME

#### 最后，可以通过以下语句查看是否修改成功

> select instance_name from v$instance;