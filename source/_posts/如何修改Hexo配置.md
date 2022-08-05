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

<a name="d388e0a5"></a>
# 删除无用的配置文件

修改配置之前，我们先删除一些无用的文件，如图：

![96234624-a822-4905-9e7c-f8fb59580d31.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659682142418-3b835639-dc83-4ff1-95c3-f49a790474ad.png#clientId=u7da53f51-ebc3-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=339&id=u2b97a5bb&name=96234624-a822-4905-9e7c-f8fb59580d31.png&originHeight=339&originWidth=664&originalType=binary&ratio=1&rotation=0&showTitle=false&size=35880&status=done&style=none&taskId=u5433ed35-c115-437c-a9f1-0f7dc516c23&title=&width=664)

这个文件是默认主题 landscape 的配置文件，对我们来说已经没有意义，删除即可。

![210d99e2-86c8-4cd0-b134-783ccb91a5cc.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659682171326-3f13cc2f-c830-4215-b639-7b26fbe70550.png#clientId=u7da53f51-ebc3-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=372&id=u42535f9c&name=210d99e2-86c8-4cd0-b134-783ccb91a5cc.png&originHeight=372&originWidth=876&originalType=binary&ratio=1&rotation=0&showTitle=false&size=37191&status=done&style=none&taskId=u46221f24-a27a-4fd7-9348-b5a23479268&title=&width=876)

由于我们在根目录中已经有了_config.tangyuxian.yml，所以themes\tangyuxian中的_config.yml也可以删除了。

<a name="71615235"></a>
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

![6e15be58-71e0-4239-bc4a-8a97c5ee50e8.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659682192983-f5f7fc95-d00d-4c14-aef7-5869bfe4368d.png#clientId=u7da53f51-ebc3-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=208&id=u02c2ae24&name=6e15be58-71e0-4239-bc4a-8a97c5ee50e8.png&originHeight=208&originWidth=495&originalType=binary&ratio=1&rotation=0&showTitle=false&size=15027&status=done&style=none&taskId=u4ffdb1ee-b257-4c8f-986a-b54ba3fb42b&title=&width=495)

配置正确则是这样的：

![81543f99-9f43-4936-93af-9e8358f86081.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659682213407-0f738766-ef3b-4eef-b651-89dd82c46256.png#clientId=u7da53f51-ebc3-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=195&id=u634112de&name=81543f99-9f43-4936-93af-9e8358f86081.png&originHeight=195&originWidth=865&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9647&status=done&style=none&taskId=ud232ad3c-ce7d-487c-be6a-cc0d472a51d&title=&width=865)

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

<a name="151b7e64"></a>
# 配置Git

关于什么是Git，这里我不再赘述，在本项目中我选择的存储库是GitHub。

<a name="e9830f26"></a>
## 配置.gitignore

在.gitignore文件中加上一些忽略文件，如.log等。

<a name="0eb902d6"></a>
## 完成初次代码提交

初始化提交代码

<a name="78dc92e2"></a>
# 个性化配置博客

<a name="b6453aea"></a>
## 基础配置

修改 _config.yml 中的网站基础配置，如下：

![77c4ab5d-e889-4e00-bb9c-1513757ef3f9.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659682242804-c43f4126-6dc5-4aa3-879b-c209574077df.png#clientId=u7da53f51-ebc3-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=746&id=u803278f8&name=77c4ab5d-e889-4e00-bb9c-1513757ef3f9.png&originHeight=746&originWidth=1162&originalType=binary&ratio=1&rotation=0&showTitle=false&size=82962&status=done&style=none&taskId=u735905b0-4478-4422-8a88-88dc55fec66&title=&width=1162)

如果对这些配置有不明白的地方，参考文档：[**https://hexo.io/docs/configuration.html**](https://hexo.io/docs/configuration.html)

<a name="277603e9"></a>
## **博客侧边栏目配置**

修改 _config.tangyuxian.yml 中的网站个性化配置，如下：

![9634e145-d5b0-43cd-919b-58112b213a57.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659682256529-2d3cda99-0efb-4d7d-8701-aeef6349e0ba.png#clientId=u7da53f51-ebc3-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=669&id=u1cad705a&name=9634e145-d5b0-43cd-919b-58112b213a57.png&originHeight=669&originWidth=1348&originalType=binary&ratio=1&rotation=0&showTitle=false&size=88711&status=done&style=none&taskId=u22660611-73f7-44db-8a9e-5e02dc7dcca&title=&width=1348)

在 source 文件夹下依次新建archives.md、about.md、friend.md、download.md四个Markdown文件表示我的四个边栏内容文章归档、关于作者、我的朋友、下载中心，并按上图所示修改menu配置，编译后如图所示：

![4e6ecace-0c97-4d14-9e6f-54b556d66d16.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659682270069-93caec97-a1bb-47f0-a427-e6c1fa197349.png#clientId=u7da53f51-ebc3-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=679&id=u96cd70dd&name=4e6ecace-0c97-4d14-9e6f-54b556d66d16.png&originHeight=679&originWidth=1469&originalType=binary&ratio=1&rotation=0&showTitle=false&size=972585&status=done&style=none&taskId=uf4a82633-ffab-4774-aa7b-21b763fe1c0&title=&width=1469)

<a name="773d8b29"></a>
## 个人相关链接配置

由于我的其他相关网站比较少，所以这里只配置了一个GitHub，其他的注释处理：

![3ec0cc58-020f-4180-a91b-8db601ede864.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659682282952-31ba701e-f16b-4f92-8678-a18ab3a9de78.png#clientId=u7da53f51-ebc3-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=561&id=u0e897c62&name=3ec0cc58-020f-4180-a91b-8db601ede864.png&originHeight=561&originWidth=1192&originalType=binary&ratio=1&rotation=0&showTitle=false&size=79319&status=done&style=none&taskId=uab6da5c0-317e-4bc8-a736-6140d5a0c9f&title=&width=1192)

实际效果：

![636eea3f-2e4b-49c5-ab51-ceaa7d4f38b3.png](https://cdn.nlark.com/yuque/0/2022/png/376691/1659682296742-c5d08b0e-28ed-4d4b-97ea-287f9d3646a3.png#clientId=u7da53f51-ebc3-4&crop=0&crop=0&crop=1&crop=1&from=paste&height=937&id=ubffa559b&name=636eea3f-2e4b-49c5-ab51-ceaa7d4f38b3.png&originHeight=937&originWidth=1920&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1496810&status=done&style=none&taskId=u5695a457-0ea8-431f-aa6c-5e34928a930&title=&width=1920)

配置相关的介绍就到这里，还有其他许多的配置可以自定义，这些内容在配置文件中都有注释，包括相关文档，非常详尽，大家可以自行探索。
