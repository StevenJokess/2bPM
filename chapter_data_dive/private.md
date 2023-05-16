# 隐私




## 机器学习隐私泄露：

- 不可靠的数据收集者泄露信息（直接泄露）
- 攻击者分析机器学习模型输出结果，逆向推出训练数据中的用户敏感信息（间接泄露）

## 法律

在法律层面，欧盟《通用数据保护条例》（GDPR）规范了企业收集、管理、删除客户和个人数据[3]

华为小冰虚拟男友是安全的吗，怎么看待有网友爆料会自动开启摄像头窃取用户隐私的事情？是可信的吗？ - 知乎
https://www.zhihu.com/question/418430367

当我们的技术团队，就是机器语义理解的团队，说我们自己做输入法可能会做的更好的时候，我当然很赞成。因为至少，在安全性方面，我们可以做的足够好。[2]

个人信息保护：正会同相关部门制定出台《移动互联网应用程序个人信息保护管理暂行规定》，推动治理工作制度化、常态化。技术检测手段也将进一步强化，运用人工智能、大数据等新技术新手段，加快推进全国App技术检测平台建设，2021年力争具备全年检测180万款的覆盖能力。[9]

2021年日本《个人信息保护法》修正案概要[10]

## 解决方案

隐私计算是一门综合技术，具体来说，目前主要包括三个方向。[7]

其一为基于密码学的多方安全计算（MPC：Multi-party Computation）技术。通过秘密分享、遗忘传输、混淆电路或同态加密等特殊的加密算法和协议，从而支持在加密数据上直接进行计算。理论上，在不考虑代价的“理想”情况下，多方安全计算技术能实现任意的计算“功能”，并且达到比较高的安全性。但是由于数据通信量骤增，计算效率损失大和需要极高的算力要求等因素，MPC的技术产品化还有一定的限制，相关的技术解决方正在积极探索。

其二为基于人工智能的联邦学习技术。在横向维度，每个参与者在本地训练计算自己的样本，只分享模型训练的梯度；纵向维度，各参与者训练各自的embedding（“向量映射”），共同训练上层模型。两个维度的融合，从而让多个相互不信任的数据拥有方不必共享数据的基础上联合进行模型训练。

其三为基于可信硬件的安全沙箱计算（TEE： Trusted Execution Environment[5]）技术。其核心思想是构建一个硬件安全区域，数据仅在该安全区域内进行计算，利用可信任执行环境TEE防止操作系统恶意地查看应用执行环境的内容；利用安全沙箱防止恶意应用通过特殊调用控制操作系统。

业界解决隐私泄露和数据滥用的数据共享技术路线主要有两条。一条是基于硬件可信执行环境（TEE： Trusted Execution Environment）技术的可信计算，另一条是基于密码学的多方安全计算（MPC：Multi-party Computation）。[5]

### 深度学习隐私保护

- 宽松差分隐私：绝对的差分隐私会导致天平倾向隐私，而导致系统不可用
- 集成模型：一种基于知识迁移的深度学习隐私保护框架。引入学生模型和教师模型[8]

不足：隐私性降低，泄露风险的可能性变大。另外，差分隐私仅能实现单点的隐私保护，若不同记录之间存在关联，攻击者仍可对满足差分隐私的算法进行攻击。

### 对金融领域的重要意义

无论是联邦学习还是共享智能，很多技术实践都优先选择了在金融领域落地。相较于其他领域，金融领域对数据的管控更为严格，对数据隐私更加重视，因此也是最需要通过技术手段解决数据孤岛问题的领域。

周俊表示，在金融领域，共享智能侧重在解决“开放”这个大领域中的问题，比如联合营销、联合风控等，这两个场景相对更容易看到具体实施效果。相比其他领域，金融领域对数据保护看的更重，数据的流转在该领域中更难，因此采用共享智能技术，可以做到更好的隐私保护，实现数据可用不可见，是一个关键的助推器。

举例来说，通过数据融合，蚂蚁金服的共享智能帮助中和农信大幅度提高了风控性能，把原来传统的线下模式，变成线上自动过审模式，完成授信只需5分钟，8个月累计放款31.9亿，授信成功人数44万人，业务覆盖20多个省区，300多县城，10000多个乡村。

[2]: https://www.uisdc.com/wechat-10-years
[3]: https://www.msra.cn/zh-cn/news/features/privacy-protection-in-machine-learning
[4]: https://segmentfault.com/a/1190000023428141
[5]: http://gaocegege.com/Blog/fedlearn
[6]: https://tech.antfin.com/community/articles/810
[7]: https://www.ofweek.com/security/2020-09/ART-510006-8900-30458012.html
[8]: https://segmentfault.com/a/1190000023428141
[9]: https://www.jingpt.com/article/064f8c94-2c2a-4738-9146-b5aca6864479
[10]: https://zhuanlan.zhihu.com/p/382647433