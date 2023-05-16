
特征工程
========

并非所有的数据都对我们用，所以我们要甄别，这个过程叫特征工程\ `2 <https://mp.weixin.qq.com/s/URwrV1WjKC6y_UH_5IWHyQ>`__

特征工程主要包含如下几个环节：数据观察—>数据清洗—>特征加工—>特征选择—>特征规约。好的特征工程不仅需要我们对模型算法有深入的理解，还要有较强的专业领域知识。我们将特征工程主要涵盖的环节以及各环节需要解决的问题总结在下方的导图中，以供大家参考。
`1 <https://zhuanlan.zhihu.com/p/144488073>`__

.. figure:: ../img/feature_engineer.png

   特征工程

Python
------

选定了特征之后，我们来生成特征矩阵X，把刚才我们决定保留的特征都写进来。

常用代码\ `2 <https://mp.weixin.qq.com/s/URwrV1WjKC6y_UH_5IWHyQ>`__\ ：

import numpy as np import pandas as pd df =
pd.read_csv(‘customer_churn.csv’) X = df.loc[:,[‘CreditScore’,
‘Geography’, ‘Gender’, ‘Age’, ‘Tenure’, ‘Balance’, ‘NumOfProducts’,
‘HasCrCard’, ‘IsActiveMember’, ‘EstimatedSalary’]]
