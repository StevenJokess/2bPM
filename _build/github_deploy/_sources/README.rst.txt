
2bPM
====

学习如何成为AI产品经理并体系化总结生成书

https://stevenjokess.github.io/2bPM/

Docker里d2lbook2生成书
----------------------

利用项目：https://github.com/aieye-top/d2l-book2

.. code:: bash

   docker run --rm --name 2bPM -e HTTP_PROXY=127.0.0.1:1080 -ditv /d/onedrive/Documents/read/2bPM:/d2lbook2/2bPM registry.cn-shanghai.aliyuncs.com/csq-dl/d2l-book2:fix_deploy  /bin/bash;docker exec -it 2bPM /bin/bash

   cd 2bPM

   d2lbook2 build html

   d2lbook2 deploy html

声明
----

全部只作为自我求职路上的学习成果展示，我均注明出处，版权归原作者所有，感恩所有分享知识的创作者，可点击之后的【】查看原出处，是他们的乐于助人成就了现在的我，如果侵权请联系。

欢迎转载，帮我宣传下解决俺的就业就行，谢啦。

“能力、资源、机会是相互交叠，螺旋上升的。”

感谢世界相逢的一切，不过也不重要了，我们会死在“光明的未来”。

自我介绍
--------

人类幼儿园中班在读，超想读\ **超人类小学**\ ！人类都不过如此罢？

跨级才是人才，在巨变的时代，几年经验都是扯淡！见\ `25 岁网安 CEO 被判刑
12 年，技术隔离后，顶尖黑客被 out
了？ <https://www.infoq.cn/article/DtZRqGpYA1pfzsxtiD0C>`__

简历：https://stevenjokess.github.io/2bPM/get_started.html

TODO：https://my.oschina.net/u/4584889/blog/4394219
