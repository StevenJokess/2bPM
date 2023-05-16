# MLOps

## 什么是MLOps[^1]

MLOps就是机器学习时代的DevOps。它的主要作用就是连接模型构建团队和业务，运维团队，建立起一个标准化的模型开发，部署与运维流程，使得企业组织能更好的利用机器学习的能力来促进业务增长。

最近几年，大家对于机器学习项目落地愈发重视起来，对业务的理解，模型应用流程等都做的越来越好，也有越来越多的模型被部署到真实的业务场景中。但是当业务真实开始使用的时候，就会对模型有各种各样的需求反馈，算法工程师们就开始需要不断迭代开发，频繁部署上线。随着业务的发展，模型应用的场景也越来越多，管理和维护这么多模型系统就成了一个切实的挑战。

回顾这个发展，是不是感觉似曾相识？20年前软件行业在数字化演进道路上也遇到过类似的挑战。我们从部署一个Web服务到要部署几十甚至上百个不同的应用，在各种规模化交付方面的挑战之下，诞生了DevOps技术。像虚拟化，云计算，持续集成/发布，自动化测试等软件工程领域的各类最佳实践基本都跟这个方向有关。在不远的将来，或许智能模型也会与今天的软件系统一样普遍。一个企业需要使用非常多的业务系统来实现数字化流程，同样也需要非常多的模型来实现数据驱动的智能决策，衍生出更多与模型相关的开发运维，权限，隐私，安全性，审计等企业级需求。

因此最近几年，MLOps也逐渐成为了一个热门话题。有了好的MLOps实践，算法工程师一方面能更专注于擅长的模型构建过程，减少对模型部署运维等方面的“感知”，另一方面也让模型开发迭代的方向更加清晰明确，切实为业务产生价值。就像今日的软件工程师很少需要关注运行环境，测试集成，发布流程等细节，但却做到了一天数次发布的敏捷高效，未来算法工程师应该也能更专注于数据insights获取方面，让模型发布成为几乎无感又快速的自动化流程。


## MLOps的原则

### Automation

在整个workflow中所有可以自动化的环节，我们都应该进行自动化，从数据的接入到最后的部署上线。Google那篇经典的MLOps指导中就提出了3个层级的自动化，非常值得借鉴，后面我们会详细介绍。

### Continuous

一说起DevOps，大家就很容易联想到CI/CD，也从侧面印证这条原则的重要性。MLOps在持续集成，持续部署，持续监控的基础上，还增加了持续训练的概念，即模型在线上运行过程中可以持续得到自动化的训练与更新。我们在设计开发机器学习系统时，要持续思考各个组件对“持续”性的支持，包括流程中用到的各种artifacts，他们的版本管理和编排串联等。

### Versioning

版本化管理也是DevOps的重要最佳实践之一，在MLOps领域，除了pipeline代码的版本管理，数据，模型的版本管理属于新涌现的需求点，也对底层infra提出了新的挑战。

### Experiment Tracking

实验管理可以理解为version control中commit message的增强。对于涉及模型构建相关的代码改动，我们都应该能记录当时对应的数据，代码版本，以及对应的模型artifacts存档，作为后续分析模型，选择具体上线的版本的重要依据。

### Testing

机器学习系统中主要涉及到3种不同的pipeline，分别是数据pipeline，模型pipeline和应用pipeline（类似于模型与应用系统的集成）。针对这3个pipeline，需要构建对应的数据特征测试，模型测试以及应用infra测试，确保整体系统的输出与预期的业务目标相符，达到将数据insights转化为业务价值的目的。这方面Google的ML test score是一个很好的参考。

### Monitoring

监控也是一项软件工程的传统最佳实践。上面提到的ML test score中也有一部分是与监控相关。除了传统的系统监控，例如日志，系统资源等方面外，机器学习系统还需要对输入数据，模型预测进行监控，确保预测的质量，并在出现异常情况时自动触发一些应对机制，例如数据或模型的降级，模型的重新训练与部署等。



## 模型部署

通过测试后，我们就可以把模型部署上线啦。这里又根据业务形态的不同分成很多不同的类型，例如：

- Batch预测pipeline
- 实时模型服务
- Edge device部署，如手机app，浏览器等

这方面涉及到的话题也非常多，包括模型的序列化，推理性能优化，模型压缩等等。

模型部署的assets除了模型本身外，也需要包含end-to-end测试用例, 测试数据和相应的结果评估等。可以在模型部署完成后再执行一遍相关测试用例，确保开发和部署环境中得到的结果一致。

对于输出较为critical的模型，还需要考虑一系列model governance的需求满足。例如在模型部署前需要进行各类人工审核，并设计相应的sign-off机制。顺带一提responsible AI近年来也是越来越受到重视，在MLOps中的各个环节也需要关注相应功能的支持。

## 模型监控

最后，对于线上模型的运行，我们需要持续进行监控，包括：

- 模型依赖组件的监控，例如数据版本，上游系统等
- 模型输入数据的监控，确保schema与分布的一致性
- 离线特征构建与线上特征构建输出的一致性监控，例如可以对一些样本进行抽样，比对线上线下结果，或者监控分布统计值
- 模型数值稳定性的监控，对NaN和Inf等情况进行记录
- 模型计算资源开销方面的监控
- 模型metric方面的监控
- 模型更新周期的监控，确保没有长时间未更新的模型
- 下游消费数量的监控，确保没有处于“废弃”状态的模型
- 对于排查问题有用的日志记录
- 对于提升模型有用的信息记录
- 外界攻击预防监控
- 上述的各类监控都要配合相应的自动/人工应对机制。

以模型效果监控为例，当效果出现下降时，我们需要及时介入排查处理，或触发重训练。对于重训练来说，需要综合考虑模型效果变化，数据更新频率，训练开销，部署开销，重新训练的提升度等，选择合适的时间点进行触发。虽然有很多模型也支持在线实时更新，但其稳定性控制，自动化测试等都缺少标准做法的参考，大多数情况下，重新训练往往比在线更新训练的效果和稳定性更好。

TODO:https://cloud.google.com/solutions/machine-learning/mlops-continuous-delivery-and-automation-pipelines-in-machine-learning?hl=zh-cn

## 运维管理[^2]

人工智能运维与传统的 IT 运维，出发点是一致的 ，”运“就是要让业务处于稳定、高效的运行状态，而“维”就是运行过程当中一切和维护系统有关的工作，使业务保持继续运转的能力。人工智能的工程实践应在稳定的基础上，继续追求运维成本最低化和效率最高化。

评价人工智能产品的运维能力有如下评判标准。


系统能否在第一时间发现异常（即异常检测），当异常被发现后能否找出发生异常的原因，从原因是否能定位到具体的问题，这些具体的问题是否能够很快被修复或自动修复，未来再出现这样的问题之前是否可以提前预警。人工智能体系的运维能力和效果主要取决于体系化或平台化的程度是否够高 人工智能的平台化程度可以从如下几个方面进行衡量：模块化、插件化、配置可视化、系统化监控、自动化部署等。正所谓“磨刀不误砍柴工”，完善产品的体系化和平台化是提升运维能力的前提。

系统运维技术从早期工具时代（实现了计算机化，但运维流程尚属摸索阶段，没有规范），到 Pre-DevOps 阶段（ ITIL 体系， DevOps 等理念被提出 ），再到 DevOps阶段（该阶段追求运维流程、运维手段等角度实现完全的自动化，最终实现无人干预的运维过程）， 一直到今天的 AlOps ( Artificial Intelligence for IT Operations ）阶段（人工智能技术与 IT 运维技术相结合）


这样的发展过程在人工智能时代是一种必然，理由如下。

*复杂、多变的软／硬件架构故障本身就难以避免

*人工智能的业务本身对于系统响应速度和安全运转稳定性提出了更高的要求，当出现异常时需要对运维方案进行快速的决策和部署

*由于架构复杂、数据来源多（各类传感器、 IoT 设备等）导致的运维规则复杂、多变，很难依靠人工去维护和升级

*人工智能产品体系中蕴藏了海量、多样、高价值的监控数据

AIOps是Gartner 公司在 2016 年正式提出的概念，是一种结合了机器学习和大数据技术的运维管理软件体系。相比于传统运维体系，它可以提供类人交互、主动决策、理解执行等能力。


首先 AIOps 的两个核心组成元素是机器学习和大数据技术，这就需要去除 IT 数据孤岛，将观测数据（包括应用画像、服务图语、业务指标、应用性能、基础设施性能、日志、调用链、基础设施 ）和在大数据平台中的工单、异常事件中的数据结合起来 然后通过各种机器学习策略去分析。AIOps融合了 IT 服务管理、 IT 性能管理和自动化运维三种不同领域的技术，提供针对运维的改进和修复的决策建议

目前 AIOps 尚处于落地实践的初期，自然语言处理、智能搜索、知识图谱、监督学习、在线学习、深度学习等技术在运维场景下的工程化应用仍旧处于探索阶段。AI Ops 的工程化流程


第1步：来自监控、配置和变更的各种运行数据会给 AIOps 提供训练数据

第2步：AIOps 引擎（包括多个智能运维模型）会接受运维专家（至少对监控、容器技术、 CI/C D、故障诊断等技术非常精通）知识和反馈的不断训练，最终形成一个集异常检测、异常定位、根因分析、异常预测于一体的综合模型。在模型并不成熟之前，整个流程扮演了辅助专家进行运维的角色，即提供警告、预测、止损、修复、规避建议。

第3步，运维专家看到这些警告和建议后可以快速根据已有的预案采取止损和规避操作

第4步，接下来通过执行自动化的脚本完成回卷、动态扩缩容、切流量等目标

随着模型在识别、推理和决策上的逐步完善， AIOps 会实现常规运维工作的智能化操作，包括：运行状况监控、问题定位、业务需求梳理、需求变更、操作指导、数据应用、模块分配、参数设置等

[1]: https://zhuanlan.zhihu.com/p/357897337
[2]: https://zhuanlan.zhihu.com/p/433048716