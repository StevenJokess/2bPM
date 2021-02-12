# 2bPM

学习如何成为AI产品经理并总结生成书

https://stevenjokess.github.io/2bPM/

## Docker里d2lbook2生成书


docker run --rm --name 2bPM -e HTTP_PROXY=127.0.0.1:1080 -ditv /d/onedrive/Documents/read/2bPM:/d2lbook2/2bPM registry.cn-shanghai.aliyuncs.com/csq-dl/d2l-book2:github  /bin/bash;docker exec -it 2bPM /bin/bash

d2lbook2 build html
d2lbook2 deploy html

## 声明

全部只作为自我求职路上的学习成果展示，如果侵权请联系。
不为抄袭而自豪，只是如果不知道历史，我们的原创都是浅薄导致无意义的。

TODO
