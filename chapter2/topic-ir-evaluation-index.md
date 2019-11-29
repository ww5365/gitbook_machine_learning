# IR Evaluation Index 

## NDCG

* NDCG: normalized discount cumulative gain

* NDCG(normalize DCG)计算的是一个标准化后值，是实际排序的DCG值比上理想排序DCG值，范围是0~1

* 用户对query和url的匹配关系进行打分（实际情况中，就是人工标注），假如人工打分为4档：0/1/2/3。例如有7条url，根据模型预测的排序结果，他们的人工标注打分依次是：2 3 2 3 1 1 1，那么这一组的理想排序是：3 3 2 2 1 1 1。 NDCG会先计算理想排序3 3 2 2 1 1 1的DCG值，


![](/assets/2_IR_evalation_index.png)


这个评估指标说明：计算NDCG需要先计算dcg，cg

* CG： cumulation gain  累积收益  
gain即是每条结果的质量的定义，NDCG把所有结果相加最终相加保证，整体质量越高的列表NDCG值越大
* DCG：这个计算体现了位置对获得收益的影响，打了折扣  Discounted的设计使得越靠前的结果权重越大，这保证了第一条，更相关的排在靠前的结果会有更大的NDCG值；

* 总结：以NDCG为优化目标，保证了搜索引擎在返回结果总体质量好的情况下，把更高质量结果排在更前面


## Reference

1、https://www.cnblogs.com/HappyAngel/p/3535919.html

2、http://wiki.baidu.com/pages/viewpage.action?pageId=34306813