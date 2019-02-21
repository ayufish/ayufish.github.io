---
title: 【译】Node-js是什么？JavaScript运行时说明
date: 2018-06-05 22:32
tags:
---

原文链接：[https://www.infoworld.com/article/3210589/node-js/what-is-nodejs-javascript-runtime-explained.html](https://www.infoworld.com/article/3210589/node-js/what-is-nodejs-javascript-runtime-explained.html)

Node.js是一个精简、快速、跨平台的JavaScript运行时环境，被用在服务器端和桌面应用。

![](http://upload-images.jianshu.io/upload_images/5613261-ae44e156b03b2ff9.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  

伸缩性、延迟、吞吐量是web服务器的几个核心性能指标。当访问量增大时依旧能保持低延迟和高吞吐是不容易的。Node.js是一个通过对服务器请求“非阻塞”响应的方法实现低延迟和高吞吐的JavaScript运行时环境。换句话说，Node.js在等待I/O请求响应时不浪费时间和资源。

让我接着解释...

传统的创建web服务器方法，对于每一个进来的请求或连接服务器都产生一个执行线程甚至一个进程来处理请求和做出回应。从概念上说，这似乎非常完美，但实际上这产生了很大的开销。

尽管创建线程比分配进程花费更少的内存和CPU开销，但这依然是低效的。大量线程的存在使系统负担严重，在线程安排和上下文切换的循环中花费开销，这增加了延迟，同时也限制了服务器的伸缩性和吞吐量。

Node.js使用了一种不同的方法。它运行了一个单线程的事件循环地向系统注册来处理连接，每一个新连接都会触发JavaScript的回调函数开始执行。回调函数可以使用非阻塞的I/O调用处理请求，在必要时也可以从线程池中生产线程执行阻塞的或CPU密集型的操作并且跨CPU核心达到负载均衡。和利用多线程发挥最强效率的项目包括Apache HTTP Server、各种各样的Java应用服务器、IIS、ASP.NET、以及 Ruby on Rails相比，Node使用回调函数的方法花费更少的内存处理更多的连接。

Node.js已经被验证除了服务器端，它在桌面应用领域也十分有效。请注意Node应用不仅限于纯JavaScript。你可以使用任何语言替换JavaScript，例如TypeScript和CoffeeScript。Node.js结合了Google Chrome V8 JavaScript引擎，支持ECMAScript 2015 (ES6)语法，并且不需要任何像Babel那样转换ES6和ES5的编译器。

大量Node的功能来自于它庞大的打包库，可以通过npm命令使用。NPM，the Node package manager，是标准Node.js安装的一部分，尽管它拥有自己独立的主页。

#### 一些JavaScript的历史

1995年，Brendan Eich作为Netscape公司的承包商创造了JavaScript语言运行在Web浏览器上——据说，只花了十天。JavaScript最初是被用于在浏览器的文件对象模型(DOM)上启用动画效果和其他控制功能。不久后，一个用在Netscape Enterprise Server上的JavaScript版本问世了。

JavaScript的命名在当时是出于市场目的，因为彼时Sun公司的Java语言正被广泛地宣传。实际上JavaScript酷似Java语法的外表下主要依赖的是其自身的语言体系。

起初很多程序员认为JavaScript在“真实工作”中是无用的，因为它的解释器比编译语言慢了一个数量级。这在之后的几个专注于使JavaScript更快的研究中得以改变。显而易见的是，开源的Google Chrome V8 JavaScript引擎，做到了即时编译、内联以及动态代码优化，实际上可以在一些加载时超过C++的代码，大多数情况超过Python的性能。

基于JavaScript的Node.js诞生于2009年，由Ryan Dahl创造，面向Linux和MacOS，作为一个更具伸缩性的Apache HTTP Server替代品。NPM,由Isaac Schlueter编写，发起于2010年。原生的Node.js Windows版本初次发行于2011年。

Joyent公司拥有、管理以及支持了Node.js的开发许多年。从2015年开始，Node.js归属于Node.js基金会，由基金会的技术指导委员会管理。同时Node.js也被收录作为Linux基金会协作项目。

#### Node.js基本结构

在上层，Node.js结合了Google V8 JavaScript引擎，一个单线程非阻塞的事件循环，和一个底层的I/O接口。下面基本的代码示例说明了基本的HTTP服务器模式，使用ES6箭头函数（公开的匿名Lambda函数，使用大箭头运算符，=>）进行回调。

![](http://upload-images.jianshu.io/upload_images/5613261-cab8bfc3dfb8eaf8.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  

代码开头加载了HTTP模块，设置服务器hostname变量为localhost(127.0.0.1)，设置port变量为3000。然后创建了一个服务器和一个回调函数，示例中对于任何请求，大箭头的回调函数永远返回同样的response：statusCode 200（代表成功），content type plain text，以及一个文本回应“Hello World\\n”。最后，告诉服务器去监听localhost的3000端口（通过Socket），并且定义一个回调函数当服务器开始舰艇后在控制台打印一条日志信息。如果你使用node命令将这些代码运行在终端或控制台，然后用任意浏览器访问localhost:3000在同一台机器上，你将会看到“Hello World”在你的浏览器上。如果想停止服务器，在终端窗口按下Control-C即可。

注意在这个例子中实现的每一次调用都是异步、非阻塞的。回调函数在响应事件中执行。createServer回调函数处理一个客户端请求，返回一个响应。listen回调处理listening事件。

#### Node.js库

你可以在下图的左边栏看到，在Node.js的库中有大量的功能函数。在下图右边，你可以看到我们在代码示例中所使用的HTTP模块在早期就包含了客户端和服务器端类。使用TLS或SSL协议的HTTP服务器功能函数放在不同的模块中。

![](http://upload-images.jianshu.io/upload_images/5613261-8a435258f8030128.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  

单线程事件循环的一个内在问题是缺少纵向上的伸缩性，因为事件循环只使用一颗CPU核心。而现代CPU核心已经达到了八核心，现代服务器设备往往拥有多个CPU芯片。单线程应用无法充分利用一个拥有24个核心的强健服务器设备的性能。

你可以弥补这个缺点，尽管需要一些额外的编码。Node.js可以使用[child_process.spawn()](https://nodejs.org/api/child_process.html#child_process_child_process_spawn_command_args_options)相关方法创建子进程并且维持两个进程之间的连接，与系统的[popen(3)](http://man7.org/linux/man-pages/man3/popen.3.html)调用类似。

相比子进程模块，簇模块对于创建一个具伸缩性的服务器更加吸引人。 cluster.fork() 方法创建共享父进程服务器端口的工作进程，实际上在底层就是使用 child_process.spawn() 方法。主进程簇将进来的链接在工作进程间分配，默认情况下，循环的算法与工作线程的负载相关。

注意，Node.js不提供路由逻辑。如果你想在簇中保持跨连接的状态，你需要在工作进程之外保持住session和登陆对象。

#### Node.js包生态系统

NPM软件中心拥有将近50万个免费、可复用的Node.js代码包，这使它成为全世界最大的软件中心。需要注意的是，大多数NPM包（本质上是包含一个由package.json文件描述项目的文件夹或NPM项目）包含多个模块（你需要使用声明语句加载的程序）。很容易将这两个术语混淆，但在这个语境下它们各自有指定的含义，而不应该互换。

NPM可以管理本地依赖的特定项目，也可以管理通过网络安装的JavaScript工具。作为本地项目的依赖管理工具时，NPM可以只用一个命令安装，因为项目的所有依赖都通过package.json 文件指明；当作为网络工具管理工具时，NPM通常需要系统级（sudo）权限。

你无须使用NPM命令行去访问公共NPM软件中心。其他如Facebook的Yarn提供了客户端的体验。同样你还可以在[NPM website](https://www.npmjs.com/)上搜索和浏览工具包。

你为什么会想用NPM包？大多数情况下，要想得到你运行环境中最新稳定版本的包，通过NPM命令行安装是最快最便捷的方式，尤其是和克隆库源文件后再安装相比。如果你想要最新的版本，你可以向NMP指定一个版本号，这在一个包依赖另一个包并且依赖可能在最新版本下出错时是非常有用的。

举个例子，Express框架，一个小巧灵活的Node.js web应用框架，提供了一组强大的功能构建单页、多页、和混合式的web应用。最简单、可克隆的库提供在[https://github.com/expressjs/express](https://github.com/expressjs/express)，而Express文档在[https://expressjs.com/](https://expressjs.com/)，一个快捷的使用方式是使用npm命令将它安装进一个已经初始化好的本地工作开发目录，例如：

> $  npm install express —save

-save选项，在NPM 5.0之后已经是默认选项，通知给包管理器在安装完成后将Express模块添加进package.json文件中的依赖列表。

另一个快速使用Express的方式是全局安装可执行的生成器 express(1) ，然后使用它在一个新的工作文件夹中创建应用：

> $ npm install -g express-generator@4 $ express /tmp/foo && cd /tmp/foo

如果这些都已完成，你可以使用NPM安装所有依赖，启动服务器，这依靠生成器创建的package.json文件中的内容：

> $ npm install
>
> $ npm start

很难在NPM的50万软件包中挑选出绝对出色的工具，但有一些类别脱颖而出。Express是Node.js框架中最老最棒的一个例子，我最近在这篇[文章](http://www.infoworld.com/category/node-js/)中谈论到。NPM仓库中另一大类是JavaScript开发工具包，包括browserify，一个模块打包器；bower，浏览器打包管理器；grunt，JavaScript任务运行器；以及gulp，流构建系统。最后，对于Node.js企业开发者来说一个重要的分类是数据库客户端，包括流行的模块像redis、mongoose,firebase和pg(PostgreSQL 客户端)。

总结一下，Node.js是为服务器端和应用服务的一个跨平台JavaScript运行时环境。它基于一个单线程、非阻塞的事件循环、Google Chrome V8 JavaScript引擎和一个底层的I/O接口构建。拥有各种各样的技术，包括簇模块，允许Node.js的应用在多CPU的核心上也具有伸缩性。在它的核心功能之外， Node.js已经培育了一个在NPM仓库上拥有50万发行和迭代软件包的生态系统，所有软件包可以使用NPM命令行或一个如Yarn这样的替代品安装。
