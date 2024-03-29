# 灰度发布

灰度发布是指在黑与白之间，能够平滑过渡的一种发布方式，一级一级的发布逐渐的**扩大发布范围**，最后达到系统的完全上线。 [1]

灰度发布可以保证整体系统的稳定，在初始灰度的时候就可以发现、调整问题，以保证其影响度。

灰度期：灰度发布开始到结束期间的这一段时间，称为灰度期。

好处：

1. 提前获得目标用户的使用反馈；
2. 根据反馈结果，做到查漏补缺；
3. 发现重大问题，可回滚“旧版本”；
4. 补充完善产品不足；
5. 快速验证产品的 idea。

## 灰度发布 VS A/B测试

灰度发布于互联网公司常用A/B测试似乎比较类似，老外似乎并没有所谓的灰度发布的概念。按照wikipedia中对A/B测试的定义，A/B测试又叫：A/B/N Testing、Multivariate Testing，因此本质上灰度测试可以算作A/B测试的一种特例。只不过为了术语上不至于等同搞混淆，谈谈自己理解的两者的差异。

- 灰度发布是对某一产品的发布逐步扩大使用群体范围，也叫灰度放量
- A/B测试重点是在几种方案中选择最优方案[5]

### A/B testing [3]

一种统计方法,用于将两种或多种技术进行比较,通常是将当前采用的技术与新技术进行比较。A/B测试不仅旨在确定哪种技术的效果更好,而且还有助于了解相应差异是否具有显著的统计意义。AB测试通常是采用一种衡量方式对两种技术进行比较,但也适用于任意有限数量的技术和衡量方式。

A/B测试，在基于web的软件开发中经常使用，对于在生产中**评估模型性能**非常有用。

![A/B测试[2]](../img/A_B_Testing.png)

A/B测试基本思想：

- 单一变量
- 2个方案
- 以某一方面的标准进行评估，例如转化率

A/B测试面向的问题不是战略方案，而是某些产品设计的细节或者设计趋向的问题。例如Airbnb的收藏功能，Airbnb的收藏功能名字叫做”心愿单“，在进行A/B测试中，把收藏图标由收藏星型改成了爱心，使得收藏使用率提高了30%，倘若没有进行A/B测试，产品设计人员是绝对不敢轻易的改动该图标的。

A/B测试是**对经验主义的抨击，它是数据驱动。**

例如：在百姓网的移动APP设计中，关于付费购买增值服务的广告主信息问题有过争执。广告部同事认为应该置顶该信息，因为这可以为广告部门带来收入，而产品设计部门则基于经验认为该改动会影响用户体验，使得用户每次都看到这个东西，失去新鲜感。然而，经过A/B测试得出的数据，两者的核心数据相差的量级仅仅在千分位之后，这个改动竟然对用户体验几乎没有影响。这与产品设计的经验是相悖的。

但是，A/B测试有的时候也会出现问题。例如百姓网在求职服务的按钮设计中，“拨打电话”和“投递简历”两个按钮只能放一个，因此将其进行了测试，最后得出的结论是两者的数据不相上下，结合情景我们知道，针对不同的职位，意愿也不同。最后，技术部门更改了产品架构，把按钮的位置进行了更改，放入两个按钮，超脱了A/B测试的范围却更好的解决了问题。

A/B测试并不是个新兴的概念，自2000年谷歌工程师将这一方法应用在互联网产品以来，A/B测试在国内外越来越普及，已成为互联网产品运营精细度的重要体现。简单来说，AB实验在产品优化中的应用方法是：在产品正式迭代发版之前，为同一个目标制定两个（或以上）方案，将用户流量对应分成几组，在保证每组用户特征相同的前提下，让用户分别看到不同的方案设计，根据几组用户的真实数据反馈，科学的帮助产品进行决策。

互联网领域常见的A/B测试，大多是面向C端用户进行流量选择，比如**基于注册用户的UID或者用户的设备标识（移动用户IMEI号/PC用户Cookie）**进行随机或者哈希计算后分流。此类方案广泛应用于搜索、推荐、广告等领域，体现出千人千面个性化的特点。此类方案的特点是实现简单，假设请求独立同分布，流量之间独立决策，互不干扰。此类AB实验之所以能够这样做是因为：C端流量比较大，样本足够多，而且不同用户之间没有相互干扰，只要分流时足够随机，即基本可以保证请求独立同分布。[7]

[Trustworthy Online Controlled Experiments : A Practical Guide to A/B Testing](https://experimentguide.com/)

## 灰度策略

灰度策略一般有三种方式，可以应用于不同的场景[6]

- 随机灰度：一般在发布适合全局用户的新功能或新特性时使用，也就是在全局用户中随机测试一批用户来观察效果。
- 定向灰度：它适用于在产品中根据细分群体去发布的一些新功能。就像前面课中讲到的QQ厘米秀的案例，就是巧妙地对目标用户群进行灰度，从而推广创新产品。
- 邀请灰度：它通常适用于一款新产品的诞生，并且具备一定的社交或社区属性。一方面，能在产品诞生之初，更加聚焦于典型的种子用户群体；同时，还通过邀请码的方式，让用户形成自传播，为产品带来自增流量和口碑效应。

[1]: https://blog.csdn.net/liwei16611/article/details/90176044
[2]: https://time.geekbang.org/column/intro/100065501
[3]: https://www.yunyingpai.com/user/94.html
[4]: https://baike.baidu.com/item/%E7%81%B0%E5%BA%A6%E5%8F%91%E5%B8%83/7100322
[5]: http://www.woshipm.com/pd/706.html
[6]: https://g.yuque.com/amir/pm/ozyyed?language=zh-cn
[7]: https://tech.meituan.com/2020/01/23/meituan-delivery-machine-learning.html
