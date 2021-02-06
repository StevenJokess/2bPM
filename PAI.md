

<!--
 * @version:
 * @Author:  StevenJokess https://github.com/StevenJokess
 * @Date: 2020-12-06 22:39:30
 * @LastEditors:  StevenJokess https://github.com/StevenJokess
 * @LastEditTime: 2020-12-06 22:47:59
 * @Description:
 * @TODO::
 * @Reference:https://www.aliyun.com/price/product?spm=5176.14094290.1334604.2112pai.14f373dbeRCF6U#/pai/detail
 * https://www.aliyun.com/product/bigdata/product/learn
-->


机器学习PAI Studio
PAI-Studio为开发者提供可视化的机器学习实验开发环境，帮助用户实现0代码开发人工智能相关服务。内置数百个成熟的机器学习算法，覆盖商品推荐、金融风控、广告预测等场景。


## PAI-EAS 机器学习模型在线服务计费详情

PAI平台提供将常规机器学习模型/深度学习模型一键发布为Restful API的功能，支持用户通过http请求调用模型服务做实时预测，并且提供蓝绿部署、模型版本管理、在线调试等服务功能。 每个模型在部署的时候由用户选择占用的资源：CPU部署单位为Quota，GPU部署目前支持P4卡(NVidia Tesla P4 GPU卡)，部署单位为P4Quota

部署单位说明：
1Quota为1核CPU、4G内存
1P4quota为1P4卡、8核CPU、32G内存

每个模型服务费用=部属单位数量*部属单位单价*时长

模型一旦部署并处于running状态就会开始计费，请切记及时停止无用的模型服务，以免造成不必要的费用开销
后付费服务类型	价格	区域
CPU服务	0.4元/Quota/小时	华东2、华北2
GPU服务（P4卡）	8元/P4Quota/小时	华东2、华北2
