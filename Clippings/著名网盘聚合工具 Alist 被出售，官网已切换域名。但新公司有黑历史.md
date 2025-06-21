---
标题: 著名网盘聚合工具 Alist 被出售，官网已切换域名。但新公司有黑历史
来源: https://www.appinn.com/alist-ownership-change/
发布者: 青小蛙
发布日期: 2025-06-11T11:26:04+08:00
创建日期: 2025-06-21T20:20:59+08:00
描述: Alist 是一个开源项目，它可以将 40 多款主流网盘聚合到一个网页上，进行文件管理、视频播放等操作。来自多个方面的消息，大概2025年4月份左右易手。不过原开发者持续更新代码，但对于这件事保持沉默。@Appinn
tags:
  - clippings
  - 青小蛙
  - 小众软件
文章作者: 青小蛙
---
**[Alist](https://www.appinn.com/alist-file-list-program/)** 是一个开源项目，它可以将 40 多款主流网盘聚合到一个网页上，进行文件管理、视频播放等操作。来自多个方面的消息，大概2025年4月份左右易手。不过原开发者持续更新代码，但对于这件事保持沉默。@ [Appinn](https://www.appinn.com/alist-ownership-change/)

需要注意，虽然 Alist 是开源项目，但其使用了私有的 API，可能会「不更新就不能用」。

**更新** ：原开发者 [回应](https://t.me/alist_news/85) ：

> 项目已交由公司运营，之后我会帮忙审查开源版本仓库的代码，以及确保 release 的分发由 ci 自动构建，main 分支已开启分支保护，后续所有的提交都会经过 pr 审核。

![[images/著名网盘聚合工具 Alist 被出售，官网已切换域名。但新公司有黑历史/13288c22ac33003c2fbca8b4f113e595_MD5.avif]]



![[images/著名网盘聚合工具 Alist 被出售，官网已切换域名。但新公司有黑历史/4ce8cbaecb69b2b0a4dceca823c74eb9_MD5.jpg]]



今天早上论坛的 @tempUserName 同学发布了新主题： [https://meta.appinn.net/t/topic/72174](https://meta.appinn.net/t/topic/72174)

## 【提醒】AList 用户请暂缓升级版本

![[images/著名网盘聚合工具 Alist 被出售，官网已切换域名。但新公司有黑历史/70170ddbc0ad95078c1934762baee34d_MD5.avif]]



最早， **Alist** 的官网是 `alist.nn.ci` ，目前其更换为 `alistgo.com` ：

![[images/著名网盘聚合工具 Alist 被出售，官网已切换域名。但新公司有黑历史/fe80130f97b6a76e4cda75e1f48cdf24_MD5.avif]]

原主页

![[images/著名网盘聚合工具 Alist 被出售，官网已切换域名。但新公司有黑历史/c20d10a54c3dfe6702d6db5319e9bd65_MD5.avif]]

新主页

原开发者最近一次更新在5月11日：

![[images/著名网盘聚合工具 Alist 被出售，官网已切换域名。但新公司有黑历史/00cbf85da35acf16fe465132adf56220_MD5.avif]]


从最早质疑这件事情的 issue # [8649](https://github.com/AlistGo/alist/issues/8649) 来看：

![[images/著名网盘聚合工具 Alist 被出售，官网已切换域名。但新公司有黑历史/138c9c270d5c4f21e056ff617a3f3cca_MD5.avif]]



![[images/著名网盘聚合工具 Alist 被出售，官网已切换域名。但新公司有黑历史/494e71867d03338fadf89528a555fa92_MD5.avif]]

新开发者回复

以及上周添加用户设备统计代码（但被撤销）：

![[images/著名网盘聚合工具 Alist 被出售，官网已切换域名。但新公司有黑历史/3e284b121809f2396cd844f94f185b06_MD5.avif]]

## 目前该怎么办？

鉴于目前有些混乱的情况，包括这家公司的黑历史，请各位 Alist 用户不要更新现有部署，新部署就更不推荐了。

等待社区解决（如果能的话）。

另外，Alist 使用了私有的 API 服务（原开发者提供的 `api.nn.ci` ），所以未来不更新可能会导致无法使用。（该 API 提供了很多网盘的 token 申请服务，如果不在提供服务，就需要用户手动申请各网盘 API）

以及，青小蛙将持续关注。

另外，小雅也是基于 Alist，头大一阵子吧。

---

原文：https://www.appinn.com/alist-ownership-change/