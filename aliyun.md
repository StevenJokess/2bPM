

<!--
 * @version:
 * @Author:  StevenJokess https://github.com/StevenJokess
 * @Date: 2020-12-06 22:53:32
 * @LastEditors:  StevenJokess https://github.com/StevenJokess
 * @LastEditTime: 2020-12-06 23:23:56
 * @Description:
 * @TODO::
 * @Reference:https://help.aliyun.com/document_detail/143096.html?spm=a2c4g.11186623.6.548.1a4a53cblCY4Zg
 * https://developer.aliyun.com/article/778839?spm=a2c6h.12873581.0.dArticle778839.5de439932BzTaX&groupCode=viapi
 * https://help.aliyun.com/document_detail/182962.html?spm=a211p3.14020179.J_7524944390.13.738f4b58g1fD6Y
-->

阿里云视觉智能开放平台商业化提供了预付费QPS、后付费、预付费资源包、按量付费四种收费模式。
预付费QPS能力：人脸比对1:1、人脸检测定位、通用分割、商品分割、人体分割、人体检测、人体高清分割（即将发布）。
预付费资源包能力：物体检测（即将发布）、人体高清分割（即将发布）。
按量付费能力：物体检测（即将发布）、人体高清分割（即将发布）。
后付费能力：新冠病毒肺炎辅助诊断。
平台其他能力处于公测期可免费调用。

离线SDK介绍
阿里云视觉智能开放平台的离线SDK可以为终端设备提供AI能力，目前支持提供OCR、美颜、分割等常用AI能力的离线SDK。阿里云视觉智能开放平台通过license授权方式管理离线SDK。

离线SDK能力需求申请
如果您有业务场景需要使用阿里云视觉智能开放平台的离线SDK，请提交申请，我们将会尽快与您联系。


准备工作
在安装和使用阿里云SDK前，确保您已经注册阿里云账号并生成访问密钥（AccessKey）。详情请参见创建AccessKey。
安装Python SDK核心库。
说明 该SDK包为阿里云Java核心库，无论使用哪个产品的SDK，都必须先安装该核心库。
使用依赖包工具安装（推荐）。
执行如下命令，安装阿里云SDK核心库。
pip install aliyun-python-sdk-core
自行下载安装：使用git clone或其它方式从GitHub下载aliyun-python-sdk-core并自行添加解决方案。
安装视觉智能API相关服务Python SDK。
使用依赖包工具安装（推荐）。
执行以下命令，安装需要的SDK包。
说明 仅安装所需要的SDK包即可。
人脸人体：pip install aliyun-python-sdk-facebody
文字识别：pip install aliyun-python-sdk-ocr
商品理解：pip install aliyun-python-sdk-goodstech
内容安全：pip install aliyun-python-sdk-imageaudit
图像识别：pip install aliyun-python-sdk-imagerecog
图像生产：pip install aliyun-python-sdk-imageenhan
分割抠图：pip install aliyun-python-sdk-imageseg
目标检测：pip install aliyun-python-sdk-objectdet
图像分析处理：pip install aliyun-python-sdk-imageprocess
视觉搜索：pip install aliyun-python-sdk-imgsearch
视频理解：pip install aliyun-python-sdk-videorecog
视频生产：pip install aliyun-python-sdk-videoenhan
视频分割：pip install aliyun-python-sdk-videoseg
自行下载安装：使用git clone或其它方式下载SDK包并自行添加解决方案。详细下载地址如下所示。
AI类目	SDK链接	pypi链接
人脸人体	aliyun-python-sdk-facebody	aliyun-python-sdk-facebody
文字识别	aliyun-python-sdk-ocr	aliyun-python-sdk-ocr
商品理解	aliyun-python-sdk-goodstech	aliyun-python-sdk-goodstech
内容安全	aliyun-python-sdk-imageaudit	aliyun-python-sdk-imageaudit
图像识别	aliyun-python-sdk-imagerecog	aliyun-python-sdk-imagerecog
图像生产	aliyun-python-sdk-imageenhan	aliyun-python-sdk-imageenhan
分割抠图	aliyun-python-sdk-imageseg	aliyun-python-sdk-imageseg
目标检测	aliyun-python-sdk-objectdet	aliyun-python-sdk-objectdet
视觉搜索	aliyun-python-sdk-imgsearch	aliyun-python-sdk-imgsearch
图像分析处理	aliyun-python-sdk-imageprocess	aliyun-python-sdk-imageprocess
视频生产	aliyun-python-sdk-videoenhan	aliyun-python-sdk-videoenhan
视频理解	aliyun-python-sdk-videorecog	aliyun-python-sdk-videorecog
视频分割	aliyun-python-sdk-videoseg	aliyun-python-sdk-videoseg
