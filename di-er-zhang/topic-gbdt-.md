#GBDT - gradient boosting decision tree

## 一、为什么还需要GBDT？

原因就是过拟合。过拟合就是模型在训练数据集上表现的过于好，分的过于细。以致于容错能力很低，也可以称作”泛化能力“低。这就会导致在实际测试数据中表现明显差很多


回归的目标？

1、找个一个函数f，使得f(x)趋近于y真实值；
2、要在损失最小的条件下，得到f。



## 二、GBDT算法描述

arg max f(x): 当f(x)取最大值时，x的取值

arg min f(x)：当f(x)取最小值时，x的取值

I: 指标函数，属于定义域时，取值1；不属于时，取值0；


![](/assets/2-gbdt-jibenyuanli-1.png)

TIPS：

*  初始值的确定？常用的损失函数：$$L(y_i,r) = \frac{1}{2}(y-r)^2$$ 初始值$$f_0$$,是L取最小值时(y=r),r的均值；$$f_0 = \frac{1}{N}\sum_{i=1}^{N} y_i$$

* cart回归树划分切割点，实际使用的是残差(负梯度)进行数据的拟合？因为$$f_0 + 残差拟合值f_m + 最终剩余残差r_m$$ 等于真实y值；

* 步骤b，是回归树进行(j,s)切分点过程？切分依据： 













## 参考：
1、https://juejin.im/post/5a16bd40f265da430c117d64

经典决策树算法

2、https://juejin.im/post/5a1624d9f265da43310d79d5
GBDT(Gradient Boosting Decision Tree)基本原理

思路：

* gbdt的基本原理：主要参考2

* 里面穿插了决策树，所以插入：决策树的介绍，主要参考1


3、https://plushunter.github.io/2017/01/22/%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E7%AE%97%E6%B3%95%E7%B3%BB%E5%88%97%EF%BC%887%EF%BC%89%EF%BC%9AGBDT/

这篇文章：总结了回归树，BDT，GBDT


4、https://blog.csdn.net/zpalyq110/article/details/79527653
这篇文章：有实例演示GBDT算法的创建过程


5、http://aandds.com/blog/ensemble-gbdt.html

GBDT: 梯度提升算法 + CART回归树

gradient： 梯度  -》负梯度就是残差 
boosting： k个基本模型的叠加
DT: 回归决策树









