# 迭代优化

## 需求管理

需求管理——加深对业务和产品的理解；需求优先级、工作迭代计划——业务准确判断力

需求排序[1]——第一要务就是分清产品需求的主次，解决问题的顺序：

## 需求来源部分

不同方向的需求来源略有不同，总体来说，产品经理的需求来源有以下几个方面：

- 业务需求：由业务方，比如 BD、编审、运营等，直接提出的业务需求；
- 数据挖掘：通过数据挖掘和分析，发现的问题或需求；
- 竞对调研：通过分析竞对的产品，发现竞对比我们有优势或值得学习借鉴的地方；
- 实地观察：不论是 B 端产品还是 C 端产品，其实都有大量的机会实地观察用户行为。比如直接陪访城市运营等；
- 战略需要：俗话说「老大拍的」，这类是由公司 leader 直接安排的需求，通常表示公司未来发展方向或急需解决的关键问题；
- 其他还包括客服、商服反馈的问题，通过在线渠道或用户访谈获得的需求，还有微博、朋友圈吐槽等各种 SNS 途径。不论哪种途径获取的需求，产品经理都应该有一个自己的需求池，统一记录各种想法。

在不同需求来源中，最看重的产品经理自己发现/评估的需求，这是评价产品经理需求决策能力的重要指标。

## 收集和整理需求

收集和整理需求，就是将需求统一记录到需求池，方便团队内/间的传播。每个团队建议维护自己的需求池地址。

需求池只是一个备忘，记录下来的需求不一定都要做，也未必是值得做的需求才记录下来。

### 需求收集

- 需求来源：见上。
- 需求内容：交互体验优化、业务调整要求、业务管理要求
- 需求采集：1V1面谈、问卷调研、轮岗实习
- 需求背后的 **真实问题** 以及 **需求的价值**
- 需求背后的真正问题是什么？
- 问题是否有简单快速的解法？
- 问题影响面有多大？个案问题是否值得研究解决
- 共性问题，优先级和紧急程度？

### 需求池管理

1. 目的：实现清晰准确的需求管理、迭代计划管理，使项目进度透明
1. 需求池管理模板：

- 业务线/对应的系统
- 需求类型：产品需求、产品需求（插入）、技术需求、技术需求（插入）、线上bug
- 主题：需求概述
- 内容：需求具体描述
- 来源：需求提出者
- 提出时间
- 优先级：重要紧迫度、目标、作用对象；需要与业务方在原则上达成一致
- 迭代版本
- 业务负责人
- 产品经理
- 研发负责人
- 测试负责人
- 状态
- 计划上线时间
- 实际上线时间
- 前端开始/结束日期
- 前端研发工作量
- 发版计划

## 如此困难

- 相比去做更普适的项目，做那些你最喜欢的、自己会用的产品更令人满足。
- 相比去做直接对你的目标产生影响的项目，把注意力集中在那些聪明有趣的主意上更有诱惑力。
- 相比去做自己已经有信心的项目，去钻研新的想法更令人兴奋。（有些情况也可能反过来）

## RICE

RICE SCORE = R*I*C/E
Reach（接触数量）
Impact（影响程度）
Confidence（信心指数）
Effort（投入精力）

## MoSCoW

美其名曰“全面”，以全面来打入市场。最终却是“样样做，样样差”。must have、should have、could have、won’t have模型。

![MoSCoW](../img/MoSCoW.png)

- 位于“1”（Must have）:用户价值高,难度低,优先制作
- 位于“2”（won’t have）:用户价值低,难度高,延后制作甚至不做;
- 位于“3"、“4":如果交货时间紧，“可以有”将第一批被删除，“应该有”紧随其后。

## Kano帮你找到用户满意度[2]

一种在不同阶段按产品目标倒退需求优先级的思维方式，它将需求分为三类：

它将需求分为三类：

1. 基础功能。代表产品进入市场的基本门槛，保证能够满足用户普遍需求的最低标准。然而在后续的研发若投入大量精力，并不会显著提高用户的满意度或建立产品的竞争门槛，因此此类需求优先级较低。
2. 性能需求。即在实现基础功能后，为了提升和优化产品性能的需求。这类需求可以在一定程度上提升用户满意度，但其他竞争对手同时也会在这方面持续投入，ROI通常为线性。
3. 尖叫（兴奋）功能。用户使用产品后能够感受到喜悦和兴奋，这种产品可能是非常有创造性的，也有可能带来

属性的成熟程度和情绪反应之间呈线性关系，主要针对于如易用性、成本、娱乐价值和安全性这样的产品特征。

狩野纪昭(Noriaki Kano)将五种情绪反应可视化为图中的曲线，其中，y轴是情绪反应，x轴是特征的成熟程度。情绪反应的强度由特征如何充分呈现和其成熟程度驱动。

----

## 产品迭代管理

软件的持续优化、升级：充分利用研发资源，正确认识技术优化所需的资源，升级研发效率

1. 研发资源管理：研发人力资源安排图（时间、负责人、项目模块）
1. 技术优化资源分配

- 初创：权利开发业务功能，10%用来技术优化
- 瓶颈：业务需求满足疲态，技术架构、设计缺陷出现问题，50%技术优化
- 重构：80%资源做技术重构
- 稳定：10%-20%资源持续做技术优化

1. 双周迭代
局限性：MVP不一定能在迭代周期内交付、跨端项目复杂研发节奏相互依赖、难以准确预估工作投入



[1]: http://www.woshipm.com/pd/1887717.html
[2]: https://www.huaweicloud.com/articles/280202e7d83cd36df93e5f027939cbaa.html
[3]: https://zhuanlan.zhihu.com/p/38387218