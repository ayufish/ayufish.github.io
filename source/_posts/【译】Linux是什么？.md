---
title: 【译】Linux是什么？
date: 2018-05-27 20:20
tags:
---

![](http://upload-images.jianshu.io/upload_images/5613261-41bef76b4e6e161c.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  

原文链接： [https://www.linux.com/what-is-linux](https://www.linux.com/what-is-linux)

注：本文有删节，未翻译安装Linux及Linux软件部分。

从智能手机到汽车、超级电脑和家用电器，Linux操作系统无处不在。

Linux从90年代中期开始兴起，在各个行业和区域都达到了一定的用户基础。对于那些了解的人，Linux事实上遍布每个地方。它在你的手机，你的车上，你的电冰箱，以及在你的Roku（译者注：似乎是机顶盒品牌）设备中。它运行在大多数互联网、制造着科学突破的超级计算机以及全世界的股票交易所之中。但在Linux成为运行全世界桌面系统、服务器和嵌入式系统的平台之前，它是（并且现在仍然是）可用的最可靠、安全和无忧的操作系统之一。

对于不了解的人，别担心——这里有你开始快速了解Linux平台所需要知道的所有信息。

#### Linux是什么？

就像Windows XP, Windows 7, Windows 8和Mac OS X一样, Linux是一个操作系统。一个操作系统就是管理你的台式机或笔记本电脑所有硬件资源的软件。简而言之——操作系统管理所有你的硬件和软件之间的通讯。如果没有操作系统（通常被称为“OS”），软件将无法运行。

一个OS包括以下部分：

**The Bootloader(引导程序):**管理计算机开机的进程。对于大多数用户而言，这就是计算机最终进入操作系统之前的引导画面。

**The kernel(内核):**所有部分中这是唯一被称为“Linux”的部分。内核是系统的核心，管理着CPU、内存和外部设备，是OS的最底层。

**Daemons(后台程序):**后台服务（打印、音响、调度等），在开机期间或登录进桌面后启动。

**The Shell(壳):**你可能听说过Linux命令行。这就是shell——一个命令进程允许你在文字界面输入命令来控制计算机。这也是一度把人们吓得远远的东西（假如他们不得不去学习一门看起来很古老的命令行体系来使用Linux）。这已经不再是问题。拥有现代化桌面的Linux系统，甚至都不需要接触到命令行。

**Graphical Server（图形接口服务器）：**在显示器上显示图形界面的一个子系统。通常被称为X server或简称为“X”。

**Desktop Environment（桌面环境）：**这是实际上跟用户交互的部分。有很多桌面环境可供选择，如Unity, GNOME, Cinnamon, Enlightenment, KDE, XFCE等。每个桌面环境都包括了内置的应用，如文件管理器、设置工具、web浏览器、游戏等。

**Applications（应用）：**桌面环境没有提供全部所需的应用。就像Windows和Mac，Linux也提供了成千上万的高质量软件的下载和安装。很多现代化Linux发行版提供了类似的应用商店来集中和简化应用的安装。例如Uunbuntu的Software Center上架了许多app，你可以快速地搜索和安装它们。

![](http://upload-images.jianshu.io/upload_images/5613261-a8feb74723c3d374.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  

Ubuntu应用市场，拥有众多免费、付费应用

#### 为什么要使用Linux？

这是许多人会问的一个问题。我的台式机、笔记本、服务器运行地好好的，为什么要费工夫去学习一个完全不同的计算机环境呢？为了回答这个问题，我将抛出另一个问题。你现在的操作系统真的运行“良好”吗？还是说你经常要面对着病毒、恶意软件、缓慢、崩溃、昂贵的维护费和授权费呢？

如果你面临着以上问题，想要把自己从害怕数据丢失的恐惧或频繁地清理计算机中解脱，Linux可能是完美的平台。Linux已经演变成了这个星球上最可靠的计算机生态系统。结合这个系统入门零花费的优点，你能拥有一个完美的桌面平台解决方案。

是的，Linux可以免费使用...，你可以想把它装在多少台电脑上就装多少台，不需要为系统或服务授权费（包括像微软的客户端使用许可）花一分钱。

让我们来对比一下服务器端Linux和Windows Server 2012的花费。Windows Server单独版本价格最高需1200美元，这还不包括客户端使用许可费和其他你需要运行的软件（数据库、web扶服务器、邮件服务器等）授权费用。而Linux，完全免费，安装简单。想安装一个完整的web服务器（包括数据库），你只需要鼠标点几下或者输几条命令而已（参见“[Easy LAMP Server Installation](https://www.linux.com/learn/tutorials/288158-easy-lamp-server-installation)”）。

如果你是一个系统管理员，用Linux工作简直就是美梦成真的感觉。不需要每天照管服务器，事实上，你会发现Linux的体验接近于“设置一遍，然后忘了它”。只有很少的情况下服务器的一个服务需要重启、重新配置或升级等等，大多数情况下服务器的其余服务不会受到影响。

无论是桌面端还是服务器端，如果零花费还不足以打动你——那拥有一个不管你用多久都没多少麻烦的系统呢？我个人已经使用了将近20年的Linux（桌面和服务器都是），没有碰到过病毒、恶意软件或电脑不定时变慢的问题，就是这么稳定。服务器要重启？只有在内核升级的时候才需要。对于Linux来说，服务器运行几年都没有重启过是很正常的，这就是它的稳定性和可靠性。

Linux也是带有开源协议发行的。开源包含了以下主要宗旨：

•  任意不限用途地运行程序的自由

•  学习程序如何运行，并且根据个人意愿改变它的自由

•  重新发布副本，从而帮助到其他人的自由

•  发布修改版的副本给其他人的自由

以上对于理解共同打造Linux平台的社区至关重要。毫无疑问，这是一个“由每个人打造，为每个人而生”的操作系统。这个宗旨也是大部分人使用Linux的原因，关乎到自由与选择上的自由。

#### Linux发行版是什么？

Linux拥有许多适应各种类型用户的不同版本。从小白到硬核用户，你都能找到满足需求的“口味”。这些版本被称为发行版（distributions，简称为“distros”）。几乎所有Linux发行版都可以免费下载，烧录到硬盘（或USB设备）中，然后安装（无论装在多少台机器上）。

最流行的Linux发行版有：

![](http://upload-images.jianshu.io/upload_images/5613261-351298ce6986a22c.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  

Ubuntu Unity桌面

•  [Ubuntu Linux](http://www.ubuntu.com/)

•  [Linux Mint](http://www.ubuntu.com/)

•  [Arch Linux](https://www.archlinux.org/)

•  [Deepin](http://www.linuxdeepin.com/index.en.html)

•  [Fedora](http://fedoraproject.org/)

•  [Debian](https://www.debian.org/)

•  [openSUSE](http://www.opensuse.org/en/)

每一个发行版拥有不同的桌面。一些提供了非常现代化的界面（比如Ubuntu的Unity，Deepin的Deepin桌面），而其他则坚持传统的桌面环境（如openSUSE使用KDE）。如果想简单了解Linux桌面请点击[How to Find the Best Linux Desktop for You](https://www.linux.com/learn/tutorials/783109-how-to-choose-the-best-linux-desktop-for-you).

你可以在[Distrowatch](http://distrowatch.com/)查看排名前100名的发行版。

以及还有服务器端系统，比如：

•  [Red Hat Enterprise Linux](http://www.redhat.com/)

•  [Ubuntu Server](http://www.ubuntu.com/download/server)

•  [CentOS](https://www.centos.org/)

•  [SUSE Enterprise Linux](https://www.suse.com/products/server/)

上述服务器发行版中有一些是免费的（比如Ubuntu Server和CentOs），也有一些收取相关的费用（比如Red Hat Enterprise Linux和SUSE Enterprise Linux），技术支持也包括在费用内。

#### 哪款发行版适合你？

答案取决于下面三个简单的问题你给出的答案：

•  你操作计算机的技能怎么样？

•  你喜欢现代化的界面还是传统标准界面？

•  服务器环境还是桌面环境？

如果你的计算机技能非常基础，那么最好选择新手友好的发型吧，例如Linux Mint, Ubuntu, 或Deepin；如果你的计算机技能超过了平均水平，那么可以选择想Debian或Fedora这样的发行版；如果你精通计算机和系统管理，那么可以使用Gentoo这样的发行版。

如果你在寻找一个服务器端发行版，你必须决定是需要图形界面还是只要命令行即可。Ubuntu Server不会安装图形界面，这意味着两件事情——你的服务器不会因为加载图形界面而被拖累，而你需要对命令行有扎实的了解。但是（Linux永远会有“但是”），你可以通过一条命令比如_sudo apt-get install ubuntu-desktop_在Ubuntu Server之上安装图形包。系统管理员会想去知道一个发行版有哪些功能，你想要一个服务器专用、提供给你开箱即用满足你服务器需求的发行版吗？如果是，那么CentOs回事最好的选择。或者说，你想要一个可以在需要时自己添加功能的桌面发行版吗？如果是，Debian或Ubuntu也许能够满足你。

对于新用户，查看“[The Best Linux Distribution for New Users](https://www.linux.com/news/software/applications/775873-the-best-linux-distribution-for-new-users)”来更容易地做出选择。

#### 更多资源

如果你正在寻找一个在桌面和服务器端都醉可靠、最安全的平台，那么久选择一个Linux发行版吧。使用Linux你可以确保你的计算机把各种麻烦、服务器重启和频繁寻求技术支持的困扰降低到最小。

如果你正在寻找更多资源来指导你的Linux生涯，请查看一下网站：

•  [Linux.com](https://www.linux.com/): 关于Linux 的任何事情(新闻 、教程、问答、论坛等 )

•  [Linux.org](http://www.linux.org/): 关于Linux 内核的方方面面(大量的初、中、高级教程)

•  [Howtoforge](http://www.howtoforge.com/): Linux教程

•  [Linux Documentation Project](http://www.tldp.org/): 大量文档 (有一些可能已经过时)

•  [Linux Knowledge Base and Tutorial](http://www.linux-tutorial.info/): 大量教程
