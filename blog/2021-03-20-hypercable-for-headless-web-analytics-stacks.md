---
slug: Hypercable for Headless Web Analytics Stacks
title: Hypercable for Headless Web Analytics Stacks
author: Hooopo Wang
author_title: Hypercable Team
author_url: https://github.com/hooopo
author_image_url: https://avatars.githubusercontent.com/u/63877?s=460&v=4
image: "https://l.ruby-china.com/photo/hooopo/805b6e0a-658a-4327-b4c4-29b599956c5b.png!large"
description: "MPP Database or SQL-MR（bigquery、clickhouse、presto） + self service BI（metabase、chartio、cubejs）= Headless Web Analytics Stacks"
tags: [analytics, bi, headless, hypercable]
---


## 什么是 Headless CMS

[Headless CMS](https://jamstack.org/headless-cms/) 是最近很流行的一个概念，是前后端分离浪潮的一个产物，一般配合JAMStack一起，可以快速搭建WEB应用。典型代表是Strapi和GraphCMS。特点是灵活，低耦合，配合各种开源组件和云服务可以有巨大的想象空间。

![](https://l.ruby-china.com/photo/hooopo/85a7decd-f0ff-427f-ab81-6a6c78a6d11b.png!large)


## 什么是Headless Analytics

其实并没有Headless Analytics 这个概念。但和Headless CMS与JAMStack的流行有着相似的地方，我觉得把这种趋势的BI技术栈，MPP Database or SQL-MR（bigquery、clickhouse、presto） + self service BI（metabase、chartio、cubejs）称为Headless Analytics是很恰当。

前面提到，促成Headless CMS和JAMStack流行的两个因素是前后端分离和云服务设施的普及。

那么，Headless Analytics流行的几个因素：

* SQL成为数据分析领域的第一语言，大数据领域的组件无论底层实现是什么，都会提供SQL接口，比如各种SQL on hadoop、SQL on HDFS，甚至SQL on kafka。还有一些坚持造自己的查询语言的组件，比如elastic和influxdb，不过这都成为了永久的遗留问题。
* 分析型数据库的扩展能力和性能有了很大提升，像bigquery、clickhouse、greenplum、timescaledb等开源产品和云服务的数据处理能力足够强大，在PB级数据量，Ad Hoc查询也可以秒级响应，不需要像传统数仓预聚合之类的方案，也不需要很重的ETL。ELT和Data Lake成为新的趋势。
* [Self Service BI](https://chartio.com/learn/business-intelligence/self-service-bi-what-you-need-to-know/) 开源项目和云服务的流行，由于SQL的标准化接口和普及，才有了像metabase、superset、chartio、mode analytics、cubejs等开源和商业的自助式BI可视化工具的流行。SQL作为统一的接口功不可没。

## Hypercable Analytics
最近在做一个项目 [Hypercable](https://github.com/HyperCable/hypercable) ，用timescaledb和openresty实现一个开源的Google Analytics，基本上复制了GA的大部分功能。但最近想法有些变化，打算做成一个Headless Web Analytics集成工具，就是存储可以自由切换，可视化部分也可以由用户自己选择，Hypercable只提供行为数据收集和Data Model定义的工作，当然对于没有耐心去定制的用户，Hypercable还会提供默认的存储和UI，只不过是以插件或SaaS的形式。

![](https://l.ruby-china.com/photo/hooopo/584c419c-54dc-46aa-b8fb-9c6ef1f8e2c7.png!large)

理论上，GA + BigQuery + datastudio 也是类似的效果，不过使用谷歌这套的特点就是贵，并且运营商锁定，并不是所有人都能用谷歌云。



