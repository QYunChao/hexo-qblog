---
title: 如何基于Hexo建立自己的博客网站
date: 2022-07-06
cover: https://cdn.jsdelivr.net/gh/nexmoe/nexmoe.github.io@latest/images/cover/compress/5c3aec85a4343.jpg
coverWidth: 920
coverHeight: 613
tags: 
  -	博客
---

介绍了什么是Hexo以及如何开始搭建博客项目

<!--more-->

**URL：**博客地址

**标签：**建站、博客

**作者：**邱昀晁

**发布时间：**2022-07-06



# 什么是Hexo

Hexo 是一个快速、简洁且高效的博客框架。Hexo 使用 [Markdown](http://daringfireball.net/projects/markdown/)（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。**官网地址：**

[Hexo](https://hexo.io/zh-cn/index.html)



## 安装前提

安装 Hexo 相当简单，只需要先安装下列应用程序即可：

- [Node.js](http://nodejs.org/) (Node.js 版本需不低于 10.13，建议使用 Node.js 12.0 及以上版本)

- [Git](http://git-scm.com/)

如果您的电脑中已经安装上述必备程序，那么恭喜您！你可以直接前往 [安装 Hexo](https://hexo.io/zh-cn/docs/#%E5%AE%89%E8%A3%85-Hexo) 步骤。

如果您的电脑中尚未安装所需要的程序，请根据以下安装指示完成安装。



## 安装 Git

- Windows：下载并安装 [git](https://git-scm.com/download/win).

- Mac：使用 [Homebrew](http://mxcl.github.com/homebrew/), [MacPorts](http://www.macports.org/) 或者下载 [安装程序](http://sourceforge.net/projects/git-osx-installer/)。

- Linux (Ubuntu, Debian)：`sudo apt-get install git-core`

- Linux (Fedora, Red Hat, CentOS)：`sudo yum install git-core`

> 如果在编译时可能会遇到问题，请先到 App Store 安装 Xcode，Xcode 完成后，启动并进入 **Preferences -> Download -> Command Line Tools -> Install** 安装命令行工具。

> 对于中国大陆地区用户，可以前往  下载 git 安装包。



## 安装 Node.js

Node.js 为大多数平台提供了官方的 [安装程序](https://nodejs.org/en/download/)。对于中国大陆地区用户，可以前往 [淘宝 Node.js 镜像](https://npm.taobao.org/mirrors/node) 下载。

其它的安装方法：

- Windows：通过 [nvs](https://github.com/jasongin/nvs/)（推荐）或者 [nvm](https://github.com/nvm-sh/nvm) 安装。

- Mac：使用 [Homebrew](https://brew.sh/) 或 [MacPorts](http://www.macports.org/) 安装。

- Linux（DEB/RPM-based）：从 [NodeSource](https://github.com/nodesource/distributions) 安装。

- 其它：使用相应的软件包管理器进行安装，可以参考由 Node.js 提供的 [指导](https://nodejs.org/en/download/package-manager/)。

对于 Mac 和 Linux 同样建议使用 nvs 或者 nvm，以避免可能会出现的权限问题。

> 使用 Node.js 官方安装程序时，请确保勾选 **Add to PATH** 选项（默认已勾选）



## 安装 Hexo

所有必备的应用程序安装完成后，即可使用 npm 安装 Hexo。

```shell
$ npm install -g hexo-cli
```

## 进阶安装和使用

对于熟悉 npm 的进阶用户，可以仅局部安装 `hexo` 包。

```shell
$ npm install hexo
```

安装以后，可以使用以下两种方式执行 Hexo：

1. `npx hexo <command>`

1. 将 Hexo 所在的目录下的 `node_modules` 添加到环境变量之中即可直接使用 `hexo <command>`：

```shell
echo 'PATH="$PATH:./node_modules/.bin"' >> ~/.profile
```



# 实际搭建Hexo博客

Hexo安装结束后，下面我们开始实际博客项目的搭建。

## 创建项目

使用`hexo init`初始化项目，我这里项目名称是 hexo-qblog，如下：

![](https://tcs.teambition.net/storage/312j9ef3f813b25a9de82eded978683c2452?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IjVmYTJhOWU2ODU2ODU1MWI0ODM5ZTEwNSIsImV4cCI6MTY1NzA3MzQwNiwiaWF0IjoxNjU3MDY5ODA2LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmo5ZWYzZjgxM2IyNWE5ZGU4MmVkZWQ5Nzg2ODNjMjQ1MiJ9.5tyS_l34RsY3gNrO4vzRdADaLuzybUleaeEwYwSmKyE&download=image.png "")

初始化的时候可能会有一个报错，是自动安装依赖失败，关系不大，进入项目目录hexo-qblog用命令`npm install`自己安装一下就行，如下：

![](https://tcs.teambition.net/storage/312j443d35718a0d106be6fe260f1341ecc6?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1NzYxNDA2MiwiaWF0IjoxNjU3MDA5MjYyLCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmo0NDNkMzU3MThhMGQxMDZiZTZmZTI2MGYxMzQxZWNjNiJ9.LihMTMBUbLVFSjD22jZ1nD50AahXchtBXFP8iK3GfUI&download=image.png "")



## 运行项目

使用`hexo server --debug`运行本地项目，`--debug` 是输出调试日志：

![](https://tcs.teambition.net/storage/312j3a349ee847ea0ce157d30f7054a9b17e?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1NzYxNDA2MiwiaWF0IjoxNjU3MDA5MjYyLCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmozYTM0OWVlODQ3ZWEwY2UxNTdkMzBmNzA1NGE5YjE3ZSJ9.D5HIG7kXknm6FZ3k9Z9ttXpoRe3WX40vYXiA0-qMjAI&download=image.png "")

在日志的最后面会显示本地调试地址：

![](https://tcs.teambition.net/storage/312j1f3bc19d159f7582d171aee4a63a43b7?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1NzYxNDA2MiwiaWF0IjoxNjU3MDA5MjYyLCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmoxZjNiYzE5ZDE1OWY3NTgyZDE3MWFlZTRhNjNhNDNiNyJ9.twmqD2h8lc0Z5cSFZmHXNHMPGhYvqK71XLXnFu4XJmU&download=image.png "")

然后我们在浏览器打开本地地址[__http://localhost:4000/__](http://localhost:4000/)，就可以看到自己的一个默认主题的博客了：

![](https://tcs.teambition.net/storage/312je79c75685dc613f23d4a10c076ef5fa6?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1NzYxNDA2MiwiaWF0IjoxNjU3MDA5MjYyLCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmplNzljNzU2ODVkYzYxM2YyM2Q0YTEwYzA3NmVmNWZhNiJ9.SJNft9xzYWQFgfLtoEDy0fL_ZmeUe4FonG2a8iM6gj4&download=image.png "")



## 更换主题

前面说过，Hexo可以利用靓丽的主题生成静态网页，达到非常酷炫的网页效果，上面的默认主题也是比较丑的，所以我们给我们的博客先换个漂亮的主题。

![](https://tcs.teambition.net/storage/312j46b24fa0c733468076f402a8d9f5cde0?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1NzYxNDA2MiwiaWF0IjoxNjU3MDA5MjYyLCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmo0NmIyNGZhMGM3MzM0NjgwNzZmNDAyYThkOWY1Y2RlMCJ9.DdqaFGYWo6Wg8mZAj4MqLwFZKWDg6Bd4Sp9vicUo5FU&download=image.png "")

在官网中有非常多的主题供我们选择，这里我选了一个比较卡通可爱风的主题，叫做 [hexo-theme-tangyuxian](https://github.com/tangyuxian/hexo-theme-tangyuxian)，这个主题在GitHub上也有开源，感兴趣的小伙伴可以点击去看看。

我们先看看主题效果：

![](https://tcs.teambition.net/storage/312jb301ae0e6f284f5ec12745937add0c70?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1NzYxNDA2MiwiaWF0IjoxNjU3MDA5MjYyLCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmpiMzAxYWUwZTZmMjg0ZjVlYzEyNzQ1OTM3YWRkMGM3MCJ9.rMDHJegrQv9wlYSrbNAC0E03DqzittW2kU72ZNK1g6k&download=image.png "")

非常地可爱但又酷炫，下面把它运用到我们自己的博客上面来。



### clone项目

```shell
git clone https://github.com/tangyuxian/hexo-theme-tangyuxian.git
```

clone下的项目如下，上面是前面新建的Hexo项目hexo-qblog，下面是主题项目：

![](https://tcs.teambition.net/storage/312j7153d07af99f5dd030c3fc89840ff439?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IjVmYTJhOWU2ODU2ODU1MWI0ODM5ZTEwNSIsImV4cCI6MTY1NzEyMzQ1OSwiaWF0IjoxNjU3MTE5ODU5LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmo3MTUzZDA3YWY5OWY1ZGQwMzBjM2ZjODk4NDBmZjQzOSJ9.wdGpkYKlWnwQsS9JBpx0tllgacGJgyq8i09KSdynB2w&download=image.png "")

将 hexo-theme-tangyuxian 重命名为 tangyuxian：

![](https://tcs.teambition.net/storage/312j883800c2662ca4827f7b8091d086e679?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IjVmYTJhOWU2ODU2ODU1MWI0ODM5ZTEwNSIsImV4cCI6MTY1NzEyMzU1NCwiaWF0IjoxNjU3MTE5OTU0LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmo4ODM4MDBjMjY2MmNhNDgyN2Y3YjgwOTFkMDg2ZTY3OSJ9.SN5a03mxI325scEgPQkHar_Bz1Rc4hUWl65naNkzxyI&download=image.png "")

然后将 tangyuxian 整个文件夹复制到 hexo-qblog\themes 文件夹下面，如下图：

![](https://tcs.teambition.net/storage/312j3ed0cb8ee26d87ef5ce81b90d18f65f2?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IjVmYTJhOWU2ODU2ODU1MWI0ODM5ZTEwNSIsImV4cCI6MTY1NzEyNDc1MiwiaWF0IjoxNjU3MTIxMTUyLCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmozZWQwY2I4ZWUyNmQ4N2VmNWNlODFiOTBkMThmNjVmMiJ9.YLOCwQd9jwTK9iMbfMiecuLde8YChZpOY8441OzKvAg&download=image.png "")

然后进入hexo-theme-tangyuxian 文件夹删除 .git 目录，并复制 _config.yml 文件：

![](https://tcs.teambition.net/storage/312j09943e0630ef456b25d3fdb65560fca6?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IjVmYTJhOWU2ODU2ODU1MWI0ODM5ZTEwNSIsImV4cCI6MTY1NzEyNDcxOCwiaWF0IjoxNjU3MTIxMTE4LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmowOTk0M2UwNjMwZWY0NTZiMjVkM2ZkYjY1NTYwZmNhNiJ9.2n3tpxxESnoHtG_f8rF4HY_FEiUFfPLj9FnLvLVi39E&download=image.png "")

将上面复制的文件 _config.yml 粘贴到项目根目录 hexo-qblog 文件夹下面，并重命名为_config.tangyuxian.yml，表示这是 tangyuxian 主题的配置文件：

![](https://tcs.teambition.net/storage/312j834872a69fccbf595a2a3fec3e11e285?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IjVmYTJhOWU2ODU2ODU1MWI0ODM5ZTEwNSIsImV4cCI6MTY1NzEyNDg3NCwiaWF0IjoxNjU3MTIxMjc0LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmo4MzQ4NzJhNjlmY2NiZjU5NWEyYTNmZWMzZTExZTI4NSJ9.q0eeTw9908g52M0dszt_AwJg_DKwcvka0V7j32nXRbE&download=image.png "")

打开 hexo-qblog 整个项目文件夹（我这里是用VS Code），修改项目根目录下的 _config.yml 文件，找到文件 theme 字段，修改为 tangyuxian：

![](https://tcs.teambition.net/storage/312jd2dd6a2df9aa79d2905a8dd8bcc9e275?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IjVmYTJhOWU2ODU2ODU1MWI0ODM5ZTEwNSIsImV4cCI6MTY1NzEyNTA2NCwiaWF0IjoxNjU3MTIxNDY0LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmpkMmRkNmEyZGY5YWE3OWQyOTA1YThkZDhiY2M5ZTI3NSJ9.vT6AApUI9fzwwj1uj2Hl7AyALJwR4yXfRi4i0dAxxqI&download=image.png "")

![](https://tcs.teambition.net/storage/312j34aff379590e0a9d023c699a9765c891?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IjVmYTJhOWU2ODU2ODU1MWI0ODM5ZTEwNSIsImV4cCI6MTY1NzEyNTA4NywiaWF0IjoxNjU3MTIxNDg3LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmozNGFmZjM3OTU5MGUwYTlkMDIzYzY5OWE5NzY1Yzg5MSJ9.not5Hx6hcqCutlTkfPXs5PrkQeDj4-9g3uSnCkvhB9s&download=image.png "")

这样整个主题就更换完成了，另外由于主题默认已经集成了文章【字数统计】、【阅读时长】统计功能，需要WordCount的支持，运行如下命令安装`npm i --save hexo-wordcount`：

![](https://tcs.teambition.net/storage/312j187e681a44144a6ef30c4f0c268b91fb?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IjVmYTJhOWU2ODU2ODU1MWI0ODM5ZTEwNSIsImV4cCI6MTY1NzEyNTQwMiwiaWF0IjoxNjU3MTIxODAyLCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmoxODdlNjgxYTQ0MTQ0YTZlZjMwYzRmMGMyNjhiOTFmYiJ9._p3q57Xrlia3VrrRe6P9fzevDe0z5zUTC3D7Cl5Y7x8&download=image.png "")

下面就可以按照前文所说运行项目了`hexo server --debug`：

![](https://tcs.teambition.net/storage/312j93273f040f455b3bd15efc0bacf1ece2?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IjVmYTJhOWU2ODU2ODU1MWI0ODM5ZTEwNSIsImV4cCI6MTY1NzEyNTU3MSwiaWF0IjoxNjU3MTIxOTcxLCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmo5MzI3M2YwNDBmNDU1YjNiZDE1ZWZjMGJhY2YxZWNlMiJ9.KV2G9MQXTT61CW9Dj-mtwhYLe8dmbWJJmoyCCrKYuA4&download=image.png "")



然后打开[__http://localhost:4000/__](http://localhost:4000/)就会发现我们的主题已经焕然一新了：

![](https://tcs.teambition.net/storage/312j7285d87e368cf4feed6fdbaaaa21c74d?Signature=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IjVmYTJhOWU2ODU2ODU1MWI0ODM5ZTEwNSIsImV4cCI6MTY1NzEyNTUzNywiaWF0IjoxNjU3MTIxOTM3LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmo3Mjg1ZDg3ZTM2OGNmNGZlZWQ2ZmRiYWFhYTIxYzc0ZCJ9.Fr4SFKmtjstpdmauHSxYyJGA4Pom8zsrdhmDZmdrhSc&download=image.png "")



关于使用Hexo创建自己的博客项目并更换好看的主题就介绍完了，下期我们将介绍如何发布自己的博客，非常感谢大家的阅读。

***






