---
title: "<% tp.file.cursor() %>"
date: 2023-04-19T15:26:53+0800
categories: ["技术"]
tags: ["obsibian", "hugo"]
image: https://ericgg-1313408779.cos.ap-nanjing.myqcloud.com/imgs/%E6%88%AA%E5%B1%8F2023-04-19%20%E4%B8%8B%E5%8D%883.27.40.png

---

hugo博客的自动化发文流程已经很熟练了，在编辑器里写好文章，在gitkraken里推送至仓库，cloudflare检测到仓库变更推送后自动生成页面。如果使用obsidian来编译文章其实效果也差不多，只是说可以通过git插件来方便push仓库，但是我觉得插件太复杂没耐心研究，还不如直接用girkraken推送。那其实就是换了个编译器的差别。当然也有方便的地方，例如加入了模版插件，对于加入头部信息来说很方便。

## obsibian插件
1. image auto upload plugin
很方便上传图片到picgo，本身我安装了picgo，安装好这个插件后，把图片拖进来后会自动上传图片，这跟typora的图片上传形式简直一样，从此不再用typora，哈哈哈。
![自动上传图片插件](https://ericgg-1313408779.cos.ap-nanjing.myqcloud.com/imgs/%E6%88%AA%E5%B1%8F2023-04-19%20%E4%B8%8B%E5%8D%883.37.52.png)

2. obsidian git 
初步理解为obsibian的一个git插件，跟vscode里的那个差不多，无非是推送或者拉取，再或者克隆？但是太多英文，我又懒得研究，就索性先下载了吧。先用gitkraken来推送。

3. Templater
是一个模版工具，我以为会内置很多模版，没想到需要自己创建模版，通过快捷键再插入文章内。这会有一个方便的地方，例如头部信息，我就可以先预设我要用的模版，到时候修改一些地方就可以了。更多实用场景还需要再研究一下。
![模版截图](https://ericgg-1313408779.cos.ap-nanjing.myqcloud.com/imgs/%E6%88%AA%E5%B1%8F2023-04-19%20%E4%B8%8B%E5%8D%883.45.04.png)
**模版场景**
![模版场景](https://ericgg-1313408779.cos.ap-nanjing.myqcloud.com/imgs/%E6%88%AA%E5%B1%8F2023-04-19%20%E4%B8%8B%E5%8D%883.47.59.png)

## 实操
在根目录添加.gitgnore添加.obsibian文件，避免把ob的文件配置也同步到仓库。
新增文章，使用gitkraken推送文章。
- 这段代码代表当前文件名为博客名
```
<% tp.file.cursor() %>
```
- 这段代码当前时间
```
<% tp.date.now("YYYY-MM-DDTHH:mm:ssZZ") %>

```

