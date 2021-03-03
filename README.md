# 2bPM

学习如何成为AI产品经理并体系化总结生成书

https://stevenjokess.github.io/2bPM/

## Docker里d2lbook2生成书

```bash
docker run --rm --name 2bPM -e HTTP_PROXY=127.0.0.1:1080 -ditv /d/onedrive/Documents/read/2bPM:/d2lbook2/2bPM registry.cn-shanghai.aliyuncs.com/csq-dl/d2l-book2:github  /bin/bash;docker exec -it 2bPM /bin/bash

cd 2bPM

d2lbook2 build html

d2lbook2 deploy html
```

## 声明

全部只作为自我求职路上的学习成果展示，如果侵权请联系。

感谢世界相逢的一切，不过也不重要了，我们会死在“光明的未来”。

## 自我介绍

人类幼儿园中班在读，超想读**超人类小学**！人类都不过如此罢？

跨级才是人才，在巨变的时代，几年经验都是扯淡！

简历：https://stevenjokess.github.io/2bPM/get_started.html


TODO：https://my.oschina.net/u/4584889/blog/4394219
