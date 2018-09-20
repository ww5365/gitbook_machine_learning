#topic-LTR-玉面初识

## 一、为什么提出LTR？

LTR： learning to rank

相关度的排序模型：布尔模型 向量空间模型，隐语义分析\(latent semantic analysis\),BM25, LMIR模型

主要是query召回相关文档时使用，bs召回阶段。。

重要性排序模型：pagerank，HITS。。

以上传统模型的缺陷？只能考虑一种特征\(相关性，重要性\)，使用LTR，可以考虑多种特征，来训练模型。





## 二、LTR

### 2.1 算法分类

* pointwise:
* pairwise: RankSVM, GBRank, LambdaRank
* listwise:

### 2.2 排序问题转化到分类/回归问题？

GBRank算法描述：

![](/assets/2-ltr-1.png)

算法说明：

* 输入，是偏序对集合；如何建模？同一个query，不同排序重要度；有先有后；

* 每轮都会通过负样本，生成一颗回归树$$g_k(x)$$;进入到下轮使用，用来划分正负样本。

算法的自我理解图：

![](/assets/2-ltr-2.png)

### 2.3 代码实现

[https://github.com/ww5365/my-gbrank/blob/master/gbrank.py](https://github.com/ww5365/my-gbrank/blob/master/gbrank.py)

代码实现可能存在的两个大问题：

* gbdt 回归数据的实现，没有使用boosting思想。。

* 模拟算法生成回归数据pair时，有问题？对应create regression data步骤，如下：

```python
if ys_predict_1 < ys_predict_2 + self.tau:
  X_train_for_n_tree.append(X_target_in_qid[ind_1])
  ys_train_for_n_tree.append(ys_target_in_qid[ind_1] + self.tau)
  X_train_for_n_tree.append(X_target_in_qid[ind_2])
  ys_train_for_n_tree.append(ys_target_in_qid[ind_2] - self.tau)
```

## 参考

1、《机器学习算法-初识Learning to Rank》[https://jiayi797.github.io/2017/08/30/机器学习算法-初识Learning-to-Rank/](https://jiayi797.github.io/2017/08/30/机器学习算法-初识Learning-to-Rank/)

这篇文章基本是综述，能对LTR有初步了解；

* 为什么LTR?
* LTR 算法分类？如何将排序问题转化成机器学习的分类或回归问题？

* 文章中对pairwise原理的介绍中，有个插图参考了：  
  《机器学习排序之Learning to Rank简单介绍》：[https://yq.aliyun.com/articles/26127](https://yq.aliyun.com/articles/26127)

2、Learning to Rank简介  
[http://www.cnblogs.com/bentuwuying/p/6681943.html](http://www.cnblogs.com/bentuwuying/p/6681943.html)  
这篇文章，LTR介绍，体现功底的介绍；

3、《机器学习算法-L2R进一步了解》  
[https://jiayi797.github.io/2017/09/25/机器学习算法-L2R进一步了解/](https://jiayi797.github.io/2017/09/25/机器学习算法-L2R进一步了解/)

这篇文章剪辑到everynote，里面最终要是介绍各个算法时，参考的文章。

重点参考下面的两篇：

* 《GBRank:一种基于回归的学习排序算法》:  
  [http://kubicode.me/2016/05/08/Machine Learning/GBRank-A-PairWsie-LTR-Base-on-Regression-Framework/?utm\_source=tuicool&utm\_medium=referral](http://kubicode.me/2016/05/08/Machine Learning/GBRank-A-PairWsie-LTR-Base-on-Regression-Framework/?utm_source=tuicool&utm_medium=referral)  
  这篇文章，进行基本的说明；

* 《Learning to Rank算法介绍：GBRank》  
  [http://www.cnblogs.com/bentuwuying/p/6684585.html](http://www.cnblogs.com/bentuwuying/p/6684585.html)  
  写的很简洁，清晰；  
  这个博主其它文章，涉及GDBT及搜索引擎相关的，也非常值得参考，简明扼要；

没有书？论文？

> 思路：？  
> LTR的 基础介绍基本理论说明，参考 1 及里面的参考文章
>
> LTR的算法思想？参考  
> 里面还有穿插了对GBDT算法使用，索引又介绍了GBDT。。
>
> LTR的实际应用?项目



