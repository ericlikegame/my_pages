---
title: hugo+Twikoo+raliway部署教程
description: 为博客搭建评论服务
date: 2023-04-13
image: https://ericgg-1313408779.cos.ap-nanjing.myqcloud.com/imgs/%E6%88%AA%E5%B1%8F2023-04-13%20%E4%B8%8B%E5%8D%8812.44.37.png
categories:
    - 技术
tags:
    - twikoo
    - hugo
    - railway
---

### railway配置

根据[Twikoo官方文档](https://twikoo.js.org/quick-start.html#%E4%BA%91%E5%87%BD%E6%95%B0%E9%83%A8%E7%BD%B2)云函数部署方案腾讯云会收费，我选择了railway的免费方案，对于访问网速也还行。

照抄官方文档部署方式：

1. 在 [Railwayopen in new window](https://railway.app/dashboard) 申请并登录账号，点击 New Project - Provision MongoDB，名称随意
2. 打开 [imaegoo/twikoo-zeaburopen in new window](https://github.com/imaegoo/twikoo-zeabur) 点击 fork 将仓库 fork 到自己的账号下
3. 回到 Railway 点击 New - GitHub Repo - Configure GitHub App - 授权 GitHub - 选择刚才 fork 的仓库，等待部署完成
4. 点开环境卡片 - Variables - New Variable，左边输入 `PORT` 右边输入 `8080` 然后点 Add。
5. 点开环境卡片 - Settings - Environment - Domains，绑定一个域名（例如 `mytwikoo.up.railway.app`）
6. 到博客配置文件中配置 envId 为 `https://` 加域名（例如 `https://mytwikoo.up.railway.app`）

![railway操作步骤](https://ericgg-1313408779.cos.ap-nanjing.myqcloud.com/imgs/%E6%88%AA%E5%B1%8F2023-04-13%20%E4%B8%8B%E5%8D%8812.25.46.png)

![域名和配置](https://ericgg-1313408779.cos.ap-nanjing.myqcloud.com/imgs/%E6%88%AA%E5%B1%8F2023-04-13%20%E4%B8%8B%E5%8D%8812.27.04.png)

备注：域名可以系统生成也可以自定义，我选择自动生成。

### hugo配置

在config.yaml文件中修改评论配置找到comments(评论)修改是否允许，修改provider(供应商)改为twikoo，再修改envId为之前生成的域名。push代码即可实现评论。

![配置文件](https://ericgg-1313408779.cos.ap-nanjing.myqcloud.com/imgs/%E6%88%AA%E5%B1%8F2023-04-13%20%E4%B8%8B%E5%8D%8812.35.49.png)

## 效果

无服务搭建博客+加无服务的评论系统，真是够折腾的组合。Hugo博客系统这么复杂，这样定制化的程度较高，上手难度也很大。相比较而言，Wordpress真的太小白和方便。

![评论图片](https://ericgg-1313408779.cos.ap-nanjing.myqcloud.com/imgs/%E6%88%AA%E5%B1%8F2023-04-13%20%E4%B8%8B%E5%8D%8812.44.37.png)

## 参考

-  [Getting Started | Stack](https://stack.jimmycai.com/guide/getting-started) 主题的官方操作说明文档
-  [Twikoo 文档](https://twikoo.js.org/) 
- [Railway Docs](https://docs.railway.app/)  