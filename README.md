# 2bPM

学习如何成为AI产品经理并体系化总结生成知识库：知识库(Knowledge Base)是指一个易操作、易利用、全面有组织的知识集群，针对某些领域问题求解的需要，采用某种知识表示方式在计算机中存储、组织、管理和使用的互相联系的知识片集合。这些知识可以包括与该领域相关的理论知识、事实数据以及常识性知识，或者是专家经验得到的启发式知识。简而言之，知识库就是储存某一领域的知识，可以理解为知识管理。[3]

https://stevenjokess.github.io/2bPM/

## Docker里d2lbook2生成书

利用项目：https://github.com/aieye-top/d2l-book2

```bash
docker run --rm --name 2bPM -e HTTP_PROXY=127.0.0.1:1080 -ditv /d/onedrive/Documents/read/2bPM:/d2lbook2/2bPM registry.cn-shanghai.aliyuncs.com/csq-dl/d2l-book2:communism_c  /bin/bash;docker exec -it 2bPM /bin/bash

cd 2bPM

d2lbook2 build html

d2lbook2 deploy html
```

## 声明

全部为非谋利性质，我均注明出处的版权归原作者所有，感恩所有分享知识的创作者，可点击之后的【】查看原出处（看不了的请自行翻墙），是他们的乐于助人成就了现在的我，如果侵权请联系。而作为书的整体来说，我希望的是其版权**属于人民**[1]。

欢迎转载，宣传国际共产主义精神。

```
@misc{2bPM,
  author = {Shuqi Cai},
  title = {2bPM},
  year = {2020},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/StevenJokess/2bPM}},
}
```

“能力、资源、机会是相互交叠，螺旋上升的。”

感谢世界相逢的一切，不过也不重要了，我们会死在“光明的未来”。

## 自我介绍

人类幼儿园中班在读，超想读**超人类小学**！人类都不过如此罢？(幻想一个超越现人类的存在体说的)

跨级才是人才，在巨变的时代，几年经验都是扯淡！见[25 岁网安 CEO 被判刑 12 年，技术隔离后，顶尖黑客被 out 了？](https://www.infoq.cn/article/DtZRqGpYA1pfzsxtiD0C)

同志不要靠老资格吃饭，要靠解决问题正确吃饭。靠正确，不靠资格。靠资格吃不了饭，索性不靠它，等于还是什么官都没有做，就是不摆老爷架子，不摆官僚架子，把架子收起来，跟人民见面，跟下级见面。

简历：https://stevenjokess.github.io/2bPM/get_started.html

## Markdown入门

https://markdown.com.cn/basic-syntax/links.html

## 更新log

修改日期	修改内容

2021-8-18 +log

---

[1]: https://www.bilibili.com/video/BV13b41117AU?p=1&share_medium=android&share_plat=android&share_source=COPY&share_tag=s_i&timestamp=1607577815&unique_k=cGtmx5
[2]: https://www.bilibili.com/read/cv8910438/?from=readlist
[3]: https://www.zhihu.com/question/304499668/answer/2095028899
TODO：https://my.oschina.net/u/4584889/blog/4394219
