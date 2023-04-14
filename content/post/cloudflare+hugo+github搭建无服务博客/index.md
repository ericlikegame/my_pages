---
title: cloudflare+hugo+github搭建无服务博客
description: 通过三者实现无服务博客搭建
date: 2023-04-12
image: shortcut.png
categories:
    - 技术
tags:
    - github
    - hugo
    - cloudflare
---

## 实现方式
1. GitHub创建仓库并import主题
2. cloudflare中pages页面关联GitHub账号，创建页面并关联到新建的有主题仓库
3. cloudflare中框架选择hugo，环境变量中填写hugo版本值填写版本号
4. 自动化创建完成即可打开页面，可以自定义域名

## 效果
![截图](shortcut.png)

## 使用感受
静态网页的部署使用云空间，而不是服务器vps的形式。对于搭建者来说减轻了一个服务器的成本，同时利用github来同步网站的文章或者修改页面信息，这是一个很方便的形式。
### 问问chatgpt使用Cloudflare和GitHub来部署网页的优缺点
优点：

1. Cloudflare可以提供全球性的内容分发和防护服务，将网站的内容广泛发布到全球多个服务中心，从而提高了访问速度和稳定性。

2. GitHub Pages提供免费的网页托管服务，允许用户快速生成一个静态网站，并通过Git进行版本控制和管理。

3. Cloudflare提供的SSL证书可以使您的网站使用HTTPS协议，从而保护用户数据的安全性，增强了用户的信任感。

4. 通过使用Cloudflare的DNS服务，您可以更方便地管理您的网站域名，并且可以根据访问来源或其他因素对流量进行过滤或重定向。

缺点：

1. GitHub Pages只能托管静态网站，无法进行动态交互操作，例如登录验证、数据库访问等。

2. 部分高级功能需要额外的付费，例如Cloudflare的高级DDoS攻击防护和自定义规则等。

3. 对于一些复杂的网站，可能需要使用其他平台来进行API集成和后端处理任务。

综上所述，使用Cloudflare和GitHub来部署网站可以提高访问速度和用户体验，同时保护站点的安全性。但是，如果您需要更多的动态交互性和后端处理能力，您可能需要考虑其他的部署选项。
## 参考
-  [Hugo by Github with Cloudflare Pages :: 木木木木木](https://immmmm.com/hugo-github-cloudflare/) 
-  [使用Cloudflare Pages部署静态网站 | Do you remember?](https://wbuntu.com/deploy-static-site-with-cloudflare-pages/) 