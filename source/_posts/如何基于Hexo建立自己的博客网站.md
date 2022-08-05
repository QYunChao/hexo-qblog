---
title: 如何基于Hexo建立自己的博客网站
date: 2022-07-14 22:21:05
tags:
  -	博客
---

介绍了什么是Hexo以及如何开始搭建博客项目

<!--more-->

**标签：**建站、Hexo、博客

**作者：**邱昀晁

**发布时间：**2022-07-06

<a name="15935252"></a>
# 什么是Hexo

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 [Markdown](http://daringfireball.net/projects/markdown/)（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。**官网地址：**[Hexo](https://hexo.io/zh-cn/index.html)

<a name="6faa3e4a"></a>
## 安装前提

安装 Hexo 相当简单，只需要先安装下列应用程序即可：

-  [Node.js](http://nodejs.org/) (Node.js 版本需不低于 10.13，建议使用 Node.js 12.0 及以上版本) 
-  [Git](http://git-scm.com/) 

如果您的电脑中已经安装上述必备程序，那么恭喜您！你可以直接前往 [安装 Hexo](https://hexo.io/zh-cn/docs/#%E5%AE%89%E8%A3%85-Hexo) 步骤。

如果您的电脑中尚未安装所需要的程序，请根据以下安装指示完成安装。

<a name="d9787e5d"></a>
## 安装 Git

-  Windows：下载并安装 [git](https://git-scm.com/download/win). 
-  Mac：使用 [Homebrew](http://mxcl.github.com/homebrew/), [MacPorts](http://www.macports.org/) 或者下载 [安装程序](http://sourceforge.net/projects/git-osx-installer/)。 
-  Linux (Ubuntu, Debian)：`sudo apt-get install git-core` 
-  Linux (Fedora, Red Hat, CentOS)：`sudo yum install git-core` 

> 如果在编译时可能会遇到问题，请先到 App Store 安装 Xcode，Xcode 完成后，启动并进入 **Preferences -> Download -> Command Line Tools -> Install** 安装命令行工具。


> 对于中国大陆地区用户，可以前往  下载 git 安装包。


<a name="8ce7a425"></a>
## 安装 Node.js

Node.js 为大多数平台提供了官方的 [安装程序](https://nodejs.org/en/download/)。对于中国大陆地区用户，可以前往 [淘宝 Node.js 镜像](https://npm.taobao.org/mirrors/node) 下载。

其它的安装方法：

-  Windows：通过 [nvs](https://github.com/jasongin/nvs/)（推荐）或者 [nvm](https://github.com/nvm-sh/nvm) 安装。 
-  Mac：使用 [Homebrew](https://brew.sh/) 或 [MacPorts](http://www.macports.org/) 安装。 
-  Linux（DEB/RPM-based）：从 [NodeSource](https://github.com/nodesource/distributions) 安装。 
-  其它：使用相应的软件包管理器进行安装，可以参考由 Node.js 提供的 [指导](https://nodejs.org/en/download/package-manager/)。 

对于 Mac 和 Linux 同样建议使用 nvs 或者 nvm，以避免可能会出现的权限问题。

> 使用 Node.js 官方安装程序时，请确保勾选 **Add to PATH** 选项（默认已勾选）


<a name="5eb35f54"></a>
## 安装 Hexo

所有必备的应用程序安装完成后，即可使用 npm 安装 Hexo。

```shell
$ npm install -g hexo-cli
```

<a name="a10ec5bf"></a>
## 进阶安装和使用

对于熟悉 npm 的进阶用户，可以仅局部安装 `hexo` 包。

```shell
$ npm install hexo
```

安装以后，可以使用以下两种方式执行 Hexo：

1.  `npx hexo <command>` 
2.  将 Hexo 所在的目录下的 `node_modules` 添加到环境变量之中即可直接使用 `hexo <command>`： 

```shell
echo 'PATH="$PATH:./node_modules/.bin"' >> ~/.profile
```

<a name="3aa76d26"></a>
# 实际搭建Hexo博客

Hexo安装结束后，下面我们开始实际博客项目的搭建。

<a name="39da6755"></a>
## 创建项目

使用`hexo init`初始化项目，我这里项目名称是 hexo-qblog，如下：

![1405cf50-ca0b-4750-82e2-677161463fb0.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681379034-3716f265-76a1-4f5b-a60b-1573a1513b6a.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=219&id=u099642f6&name=1405cf50-ca0b-4750-82e2-677161463fb0.png&originHeight=219&originWidth=868&originalType=binary&ratio=1&rotation=0&showTitle=false&size=37217&status=done&style=none&taskId=u55c9a93b-950c-4dc1-8a93-95200e7fd76&title=&width=868)

初始化的时候可能会有一个报错，是自动安装依赖失败，关系不大，进入项目目录hexo-qblog用命令`npm install`自己安装一下就行，如下：

![b691ce25-9e7c-4204-82e4-8d635ae0c42b.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681481903-cb2424ec-eed8-41c5-8fce-0ebe0e834bec.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=429&id=u9d1f03f5&name=b691ce25-9e7c-4204-82e4-8d635ae0c42b.png&originHeight=429&originWidth=1000&originalType=binary&ratio=1&rotation=0&showTitle=false&size=69711&status=done&style=none&taskId=u3acf57e9-c461-4024-b3ba-dc22b5874ea&title=&width=1000)

<a name="fa4aa1b9"></a>
## 运行项目

使用`hexo server --debug`运行本地项目，`--debug` 是输出调试日志：

![00b61fc5-72db-4a6b-a2bc-89bd7ac5e31d.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681504350-2fe767b6-d7d8-4d32-a557-bb91d42b890b.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=350&id=uad96d5df&name=00b61fc5-72db-4a6b-a2bc-89bd7ac5e31d.png&originHeight=350&originWidth=855&originalType=binary&ratio=1&rotation=0&showTitle=false&size=86587&status=done&style=none&taskId=u6fd52373-ef20-407f-8935-464a4862bbd&title=&width=855)

在日志的最后面会显示本地调试地址：

![5e8b86b9-c65c-4de1-acd4-e5aa78a30f2f.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681523219-f94aee1a-8b30-426d-9b7b-83eff45ab6de.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=238&id=ub92d7f2f&name=5e8b86b9-c65c-4de1-acd4-e5aa78a30f2f.png&originHeight=238&originWidth=900&originalType=binary&ratio=1&rotation=0&showTitle=false&size=53753&status=done&style=none&taskId=u6784a905-7637-4feb-a8bc-52e306d9335&title=&width=900)

然后我们在浏览器打开本地地址[**http://localhost:4000/**](http://localhost:4000/)，就可以看到自己的一个默认主题的博客了：

![7417b072-32ee-4a7c-8ce9-3ff2b0acec88.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681545230-df01e9f2-8411-4538-80e5-53c2d7288e5e.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=1000&id=ub2bbb600&name=7417b072-32ee-4a7c-8ce9-3ff2b0acec88.png&originHeight=1000&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=413264&status=done&style=none&taskId=u0a870313-2332-4df7-b7f9-5df3e6c2c14&title=&width=1920)

<a name="8e4a4d48"></a>
## 更换主题

前面说过，Hexo可以利用靓丽的主题生成静态网页，达到非常酷炫的网页效果，上面的默认主题也是比较丑的，所以我们给我们的博客先换个漂亮的主题。

![0de3cc28-6261-406b-a114-f5f25d6a4c43.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681562163-72a0335b-d8d0-43e7-9532-e1b94a03f3ec.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=893&id=u316bcde3&name=0de3cc28-6261-406b-a114-f5f25d6a4c43.png&originHeight=893&originWidth=1202&originalType=binary&ratio=1&rotation=0&showTitle=false&size=412588&status=done&style=none&taskId=u5f9f853b-a316-470f-8796-ac73ce88e02&title=&width=1202)

在官网中有非常多的主题供我们选择，这里我选了一个比较卡通可爱风的主题，叫做 [hexo-theme-tangyuxian](https://github.com/tangyuxian/hexo-theme-tangyuxian)，这个主题在GitHub上也有开源，感兴趣的小伙伴可以点击去看看。

我们先看看主题效果：

![bf3733a5-5ca2-4f21-bfa9-aad55e1c4edc.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681581644-9cc18fa8-e58c-4ca0-8349-0dd79f95f06c.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=959&id=u18a6430a&name=bf3733a5-5ca2-4f21-bfa9-aad55e1c4edc.png&originHeight=959&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=985198&status=done&style=none&taskId=u62ae3abf-d03b-470c-9fd6-c70b6c60220&title=&width=1920)

非常地可爱但又酷炫，下面把它运用到我们自己的博客上面来。

<a name="33e0e83e"></a>
### clone项目

```shell
git clone https://github.com/tangyuxian/hexo-theme-tangyuxian.git
```

clone下的项目如下，上面是前面新建的Hexo项目hexo-qblog，下面是主题项目：

![6ffc3de2-3dad-459a-b660-3b94efe2038c.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681600585-3b948c15-103d-4f36-b1fc-9287b96aa939.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=281&id=udfeb3e4c&name=6ffc3de2-3dad-459a-b660-3b94efe2038c.png&originHeight=281&originWidth=1014&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13992&status=done&style=none&taskId=u24f08060-f5f4-4305-baab-c3087fc1f3b&title=&width=1014)

将 hexo-theme-tangyuxian 重命名为 tangyuxian：

![13bbbcc8-f601-477a-b721-f8b9f437cc3e.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681623201-a8253b99-5449-462b-b30c-6790060ee6cc.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=268&id=ucb8ce3b4&name=13bbbcc8-f601-477a-b721-f8b9f437cc3e.png&originHeight=268&originWidth=974&originalType=binary&ratio=1&rotation=0&showTitle=false&size=14117&status=done&style=none&taskId=u9638393d-259f-40a7-9f40-fb5af4c2a80&title=&width=974)

然后将 tangyuxian 整个文件夹复制到 hexo-qblog\themes 文件夹下面，如下图：

![ad88922f-fae2-4a25-a2bd-202e2c308275.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681637822-995d09dc-f5d3-43b4-bb26-3fbba3c814b3.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=255&id=uc6c7d839&name=ad88922f-fae2-4a25-a2bd-202e2c308275.png&originHeight=255&originWidth=999&originalType=binary&ratio=1&rotation=0&showTitle=false&size=20522&status=done&style=none&taskId=u0d79e99c-1f1e-41f0-a09f-3f57f904200&title=&width=999)

然后进入hexo-theme-tangyuxian 文件夹删除 .git 目录，并复制 _config.yml 文件：

![c9fe9451-dd73-449c-9262-706ccdec7a13.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681653027-c19d1b75-a0d6-4998-ac53-ba214d41d773.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=412&id=uf13bc216&name=c9fe9451-dd73-449c-9262-706ccdec7a13.png&originHeight=412&originWidth=1019&originalType=binary&ratio=1&rotation=0&showTitle=false&size=49245&status=done&style=none&taskId=u79e7a87a-8215-49a0-bcb8-a810cb0f9d3&title=&width=1019)

将上面复制的文件 _config.yml 粘贴到项目根目录 hexo-qblog 文件夹下面，并重命名为_config.tangyuxian.yml，表示这是 tangyuxian 主题的配置文件：

![f59da27a-69db-4620-bc4e-2f2dbabbbfe6.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681677714-c5e0e34d-70b9-4c8d-a659-962f6333bebe.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=396&id=ubd376d31&name=f59da27a-69db-4620-bc4e-2f2dbabbbfe6.png&originHeight=396&originWidth=986&originalType=binary&ratio=1&rotation=0&showTitle=false&size=47215&status=done&style=none&taskId=u3f9091b8-3546-468a-9f43-757cdc765ec&title=&width=986)

打开 hexo-qblog 整个项目文件夹（我这里是用VS Code），修改项目根目录下的 _config.yml 文件，找到文件 theme 字段，修改为 tangyuxian：

![94e249cc-dc48-488e-a1d1-06e43ab371cb.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681693583-60653d76-f245-48af-a263-c3910089ed3b.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=1030&id=u58b0da0e&name=94e249cc-dc48-488e-a1d1-06e43ab371cb.png&originHeight=1030&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=158845&status=done&style=none&taskId=u4331e1dd-262e-4adb-b8b1-e3486bd58d6&title=&width=1920)

![cc107c22-f452-4a6c-b81f-933afe805cc7.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681708978-3b800238-1a0b-4dfc-ba7a-ae3a3109781e.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=1030&id=u0423326f&name=cc107c22-f452-4a6c-b81f-933afe805cc7.png&originHeight=1030&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=154744&status=done&style=none&taskId=u727305c6-b6be-46e3-8317-fd3729639ee&title=&width=1920)

这样整个主题就更换完成了，另外由于主题默认已经集成了文章【字数统计】、【阅读时长】统计功能，需要WordCount的支持，运行如下命令安装`npm i --save hexo-wordcount`：

![16c0c106-013b-4495-ab70-788143121fcb.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681733376-7e83d334-fec6-4c0e-8d17-114b094c4891.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=363&id=ue0fc3cdf&name=16c0c106-013b-4495-ab70-788143121fcb.png&originHeight=363&originWidth=847&originalType=binary&ratio=1&rotation=0&showTitle=false&size=34607&status=done&style=none&taskId=u286daa67-35cc-4cd2-bd37-8f00d3f3b2a&title=&width=847)

下面就可以按照前文所说运行项目了`hexo server --debug`：

![0345c964-83ad-4265-9384-dd7e6ad1b134.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681746396-7eb37b69-6e96-40d9-9992-dcb8b6c8b8c0.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=360&id=uc4745337&name=0345c964-83ad-4265-9384-dd7e6ad1b134.png&originHeight=360&originWidth=1199&originalType=binary&ratio=1&rotation=0&showTitle=false&size=113997&status=done&style=none&taskId=ud698032b-67f3-4e10-8d53-89ea5ba4bc1&title=&width=1199)

然后打开[**http://localhost:4000/**](http://localhost:4000/)就会发现我们的主题已经焕然一新了：

![441b2025-5a13-4651-ae7a-35ab50589f3f.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659681763699-9bcebffb-4fb5-414c-ae02-935404149cbf.png#clientId=u62f5ab03-c7ca-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=992&id=u9cd6cbaa&name=441b2025-5a13-4651-ae7a-35ab50589f3f.png&originHeight=992&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=933605&status=done&style=none&taskId=u6bd03e97-bbf2-41c9-976c-db3c8ddfa9e&title=&width=1920)

关于使用Hexo创建自己的博客项目并更换好看的主题就介绍完了，下期我们将介绍如何发布自己的博客，非常感谢大家的阅读。

---

