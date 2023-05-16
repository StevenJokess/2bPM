
GAN
===

https://atcold.github.io/pytorch-Deep-Learning/en/week09/09-3/

Generator 实际在做的事情就是，对于给定样本分布 Pdata(x)，我们希望的我们
PG(x;θ），能够尽可能地接近 Pdata(x)，这里的 θ 就是控制 G
的参数，如果是神经网络的话，对应就是各层的
Weights。衡量接近的指标就是上面的 L，其含义就是如果我们从 Pdata(x) 中
采样 m 个 x_i，那么在给定 θ 的情况下，我们可以计算出从 PG 中 采样出 x_i
的几率，将它们连乘得到 L。我们的目的就是找到一个 θ_star，使得 L
能够最大。

将 log(1-D(x)) 改换为 -log(D(x))

DCGAN
-----

1. 去掉了G网络和D网络中的pooling layer。
2. 在G网络和D网络中都使用Batch Normalization
3. 去掉全连接的隐藏层
4. 在G网络中除最后一层使用RELU，最后一层使用Tanh
5. 在D网络中每一层使用LeakyRELU。
   `2 <https://blog.csdn.net/xiaoqianlizhen/article/details/81536537?spm=1001.2014.3001.5501>`__

生成对抗网络在各领域应用研究进展：
http://www.aas.net.cn/cn/article/doi/10.16383/j.aas.c180831

GAN为什么在文本上效果不佳？
---------------------------

-  图像和文本的核心区别在于图像的 Pixel 表示是连续的，而文本是由离散的
   token 组成
-  参数的微小改变不能对结果产生影响，或者说影响的方向也不对，这就导致
   Discriminator 的梯度回传变得没有意义

Generative Adversarial Networks for Text\ `1 <https://www.reddit.com/r/MachineLearning/comments/40ldq6/generative_adversarial_networks_for_text/>`__
----------------------------------------------------------------------------------------------------------------------------------------------------

GAN for NLG
~~~~~~~~~~~

SeqGAN
^^^^^^

算的上是开山之作，具体的解读可以看我之前的一篇文章 SeqGAN – GAN + RL +
NLP，其通过引入强化学习中的 Policy Gradient 来解决因为离散 token
生成前采样动作造成的不可微。后面的文章也都是基于这个框架来进行深一步地探索。SeqGAN
在 Oracle
和古诗生成任务上做了测试，回过头来看，效果只能说一般。但其开创性的将文本生成看做序列决策问题，
并且将 RL 和 GAN
进行了有机的结合，令人佩服。\ `3 <https://tobiaslee.top/2018/04/22/GAN-in-NLP-Notes/>`__

腾讯研究院：2020年AI生成内容发展报告\ `5 <http://www.199it.com/archives/1049428.html>`__
