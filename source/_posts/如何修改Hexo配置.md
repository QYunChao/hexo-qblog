---
title: 如何修改Hexo配置
date: 2022-07-14 23:12:08
tags:
  -	博客
---

修改Hexo配置并为线上部署做准备

<!--more-->

**标签：**建站、Hexo、博客

**作者**：邱昀晁

**发布时间：**2022-07-12

上次我们说到，修改主题为 tangyuxian，该主题基于 [**hexo-theme-nexmoe**](https://github.com/tangyuxian/hexo-theme-nexmoe) 深度定制，使用前需要做一些基本配置，具体教程如下。

---

# 删除无用的配置文件

修改配置之前，我们先删除一些无用的文件，如图：

![](https://www.yuque.com/api/filetransfer/images?url=https%3A%2F%2Ftcs.teambition.net%2Fstorage%2F312jcf4a05c95ef55e60a2bf3e42988ad194%3FSignature%3DeyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1ODg5NDEyNSwiaWF0IjoxNjU4Mjg5MzI1LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmpjZjRhMDVjOTVlZjU1ZTYwYTJiZjNlNDI5ODhhZDE5NCJ9.Qovt5_vwKr3Y52MGL5pD_4wzMyQpuYAEDA5hmeOAclg%26download%3Dimage.png&sign=067ba8ac4a46631838f27a7c598ba5a36c08459e2b60d755b726c6333150d713)

这个文件是默认主题 landscape 的配置文件，对我们来说已经没有意义，删除即可。

![](https://www.yuque.com/api/filetransfer/images?url=https%3A%2F%2Ftcs.teambition.net%2Fstorage%2F312jb5b7789dd0e9e175925a5877ab4fb0f3%3FSignature%3DeyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1ODg5NDEyNSwiaWF0IjoxNjU4Mjg5MzI1LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmpiNWI3Nzg5ZGQwZTllMTc1OTI1YTU4NzdhYjRmYjBmMyJ9.pynOdkG3zfuARXHv0-1uwiCgFp2bkxSJye6a3viTPRg%26download%3Dimage.png&sign=45e24e6e30191e669636dabb4431520c433c66bf1b08bc1fe1e4309b3a981d0a)

由于我们在根目录中已经有了_config.tangyuxian.yml，所以themes\tangyuxian中的_config.yml也可以删除了。

# 主题教程

1.  使用本主题包前请阅读 [HEXO官方文档](https://hexo.io/zh-cn/docs/)，本主题包仅适用于HEXO,请确认您已安装HEXO相关依赖 
2.  开始使用本主题 
   -  注意安装`wordcount`插件,用来激活字数统计功能:`npm i --save hexo-wordcount` 
   -  请修改位于您项目根目录的`_config.yml`的文件,将默认代码高亮关闭处理 

```shell
highlight:  
	enable: false
```

这点非常重要，不然在写文章的时候如果有代码会高亮异常，如下：

![](https://www.yuque.com/api/filetransfer/images?url=https%3A%2F%2Ftcs.teambition.net%2Fstorage%2F312j6aa378beb96df3c762a11c4e4b2d0c04%3FSignature%3DeyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1ODg5NDEyNSwiaWF0IjoxNjU4Mjg5MzI1LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmo2YWEzNzhiZWI5NmRmM2M3NjJhMTFjNGU0YjJkMGMwNCJ9.2VxK_UmzSpqkGvhB9im_TGcHr9uh5AVALSKje8Iecb0%26download%3Dimage.png&sign=336699c9360b2e39692d6cb942093063ac491393f7dbb69924737406a1d91fca)

配置正确则是这样的：

![](https://www.yuque.com/api/filetransfer/images?url=https%3A%2F%2Ftcs.teambition.net%2Fstorage%2F312j00aa3e284af6916f83ad7e51d9faad70%3FSignature%3DeyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1ODg5NDEyNSwiaWF0IjoxNjU4Mjg5MzI1LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmowMGFhM2UyODRhZjY5MTZmODNhZDdlNTFkOWZhYWQ3MCJ9.GbX4O3v1XBKIvGqCwVE_zQ3EafjSpBwt3aO7_hovU00%26download%3Dimage.png&sign=8c528100b1f67ff0e44752a027f30e99ab557435e96ad5d19eee557c35208619)

   - 设置文章信息

```yaml
---
title: 此处为标题
date: 此处为时间
tags:
- 标签1
- 标签2
categories:
- 分组名
cover: /images/post/markerdown.jpg(可选:封面地址,可以是相对也可以是绝对路径)
coverWidth: 1200(可选:封面宽度)
coverHeight: 320(可选:封面高度)
author:文章作者(可选)
from:文章来源(可选)
---
```

   - 自动通过标签来匹配封面(beta)

目前标签名对应的封面配置位置在主题根目录(`/source/js/postcover.js`),可在该文件下配置标签对应的封面,文章封面的优先级是(文章md文件配置的封面>自动匹配的封面>在主题包`_config.yml`全局设置的背景图)

   - 文章归档

为了让文章归档到一个页面,请在项目的根目录`/source/`下创建`archives.md`文件,文件内填写如下内容即可:

```
---
title: 文章归档
layout: archives
permalink: archives.html
---
```

   - 更多...

      1. 将本主题下载后放至您的hexo项目根目录的 `themes` 下,并开启使用本主题 
      1. 以下是本主题包的目录结构图 

```
├── languages       //国际化语言包
├── layout			//ejs模板布局文件夹
├── scripts         //自定义执行脚本		
├── source          //静态资源文件夹
├── _config.styl	//样式配置文件
├── _config.yml		//主题配置文件
├── package.json    //node配置项
└── README.md       //说明文档
```

`_config.yml`属于本主题核心配置项,本主题的所有功能性内容将在本主题中配置注:静态立绘板的配置图在 `background character` 中

3. 即时通讯插件

`daovoice`需要您到[daovoice官网](http://dashboard.daovoice.io/)申请key并配置

4. 主题色个性化配置

`_config.styl`属于本主题个性化配置项,主题色和部分插件的自定义图案可在该配置项中配置,未来版本会不断扩展可配置内容

5. 本地搜索功能依赖

参考[hexo-generator-search](https://www.npmjs.com/package/hexo-generator-search),配置相关参数,用于生成`search.xml`,本地搜索依赖该文件进行检索

6. 看板娘配置方法

参考[hexo-helper-live2d](https://github.com/tangyuxian/hexo-helper-live2d)配置看板娘插件.附赠更多丰富的看板娘插件[live2D大礼包](https://github.com/tangyuxian/live2D)(ps:里面有超级萌小埋哦)

# 配置Git

关于什么是Git，这里我不再赘述，在本项目中我选择的存储库是GitHub。

## 配置.gitignore

在.gitignore文件中加上一些忽略文件，如.log等。

## 完成初次代码提交

初始化提交代码

# 个性化配置博客

## 基础配置

修改 _config.yml 中的网站基础配置，如下：

![](https://www.yuque.com/api/filetransfer/images?url=https%3A%2F%2Ftcs.teambition.net%2Fstorage%2F312jdf13044e9d8a69bc71aead53e4ad17a4%3FSignature%3DeyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1ODg5NDEyNSwiaWF0IjoxNjU4Mjg5MzI1LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmpkZjEzMDQ0ZTlkOGE2OWJjNzFhZWFkNTNlNGFkMTdhNCJ9.t8CT5jJDStIwiTRMap6sviUChoME4lyfBsANtTT5qPY%26download%3Dimage.png&sign=8af61f968b7ae8bfd9d1abccb1810fc7b8f5b8ba0067ec7457b0ed9adfd19f3f)

如果对这些配置有不明白的地方，参考文档：[**https://hexo.io/docs/configuration.html**](https://hexo.io/docs/configuration.html)

## **博客侧边栏目配置**

修改 _config.tangyuxian.yml 中的网站个性化配置，如下：

![](https://www.yuque.com/api/filetransfer/images?url=https%3A%2F%2Ftcs.teambition.net%2Fstorage%2F312j4e15159b33713a82c85f85ac614db4e1%3FSignature%3DeyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1ODg5NDEyNSwiaWF0IjoxNjU4Mjg5MzI1LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmo0ZTE1MTU5YjMzNzEzYTgyYzg1Zjg1YWM2MTRkYjRlMSJ9.jPKEZp38aerlk7XCDsCq8Vu6LIVxg4F1bYYdKLunTHA%26download%3Dimage.png&sign=ca302450dcc0e66c45e09d74ded631d25313301aa28877ba57e00e7d664118e1)

在 source 文件夹下依次新建archives.md、about.md、friend.md、download.md四个Markdown文件表示我的四个边栏内容文章归档、关于作者、我的朋友、下载中心，并按上图所示修改menu配置，编译后如图所示：

![](https://www.yuque.com/api/filetransfer/images?url=https%3A%2F%2Ftcs.teambition.net%2Fstorage%2F312j1823c005c7ee942f7f567d479fb2946f%3FSignature%3DeyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1ODg5NDEyNSwiaWF0IjoxNjU4Mjg5MzI1LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmoxODIzYzAwNWM3ZWU5NDJmN2Y1NjdkNDc5ZmIyOTQ2ZiJ9.8AZhedymvGoUl77C_NvK1qYNWaQ887B62zR9ZVbFZFs%26download%3Dimage.png&sign=3b7e309603381fd107f0b27de95ae1acad504156d63738f2fb6d74eacc98113b)

## 个人相关链接配置

由于我的其他相关网站比较少，所以这里只配置了一个GitHub，其他的注释处理：

![](https://www.yuque.com/api/filetransfer/images?url=https%3A%2F%2Ftcs.teambition.net%2Fstorage%2F312j3c79e33f56afd185118edd6d7f5999fc%3FSignature%3DeyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1ODg5NDEyNSwiaWF0IjoxNjU4Mjg5MzI1LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmozYzc5ZTMzZjU2YWZkMTg1MTE4ZWRkNmQ3ZjU5OTlmYyJ9.dqm2V8gYtvF53A7Q0usVEaUstp5kGSYsLrHwj3g9fZk%26download%3Dimage.png&sign=6d4873d3bf7a1104551ce4542842b96012ebf01ac7a4b76848e704a2fdc18094)

实际效果：

![](https://www.yuque.com/api/filetransfer/images?url=https%3A%2F%2Ftcs.teambition.net%2Fstorage%2F312j0f709a1e3317993754cc63560e8eee52%3FSignature%3DeyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJBcHBJRCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9hcHBJZCI6IjU5Mzc3MGZmODM5NjMyMDAyZTAzNThmMSIsIl9vcmdhbml6YXRpb25JZCI6IiIsImV4cCI6MTY1ODg5NDEyNSwiaWF0IjoxNjU4Mjg5MzI1LCJyZXNvdXJjZSI6Ii9zdG9yYWdlLzMxMmowZjcwOWExZTMzMTc5OTM3NTRjYzYzNTYwZThlZWU1MiJ9.jjzuf_AnTQvo7u6E-bcBOtGkvAvmx_l_qBXdGt33_eo%26download%3Dimage.png&sign=77b0c55019f5e5cdf3ae9f5a2c2d17bfa4e25721255a1bd3bdbbfbb3ef9fc435)

配置相关的介绍就到这里，还有其他许多的配置可以自定义，这些内容在配置文件中都有注释，包括相关文档，非常详尽，大家可以自行探索。
