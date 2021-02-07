# 2bPM

学习如何成为AI产品经理并总结生成书

## Docker里d2lbook2生成书


docker run --rm --name 2bPM -e HTTP_PROXY=127.0.0.1:1080 -ditv /d/onedrive/Documents/read/2bPM:/d2lbook2/2bPM registry.cn-shanghai.aliyuncs.com/csq-dl/d2l-book2:github  /bin/bash;docker exec -it 2bPM /bin/bash

d2lbook2 build html
d2lbook2 deploy html

## TODO


