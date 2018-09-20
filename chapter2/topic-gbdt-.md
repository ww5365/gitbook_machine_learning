#GBDT - gradient boosting decision tree

## 一、GBDT

* 什么是GBDT？

gradient： 梯度 -》负梯度就是残差 
boosting： k个基本模型的叠加
DT: 回归决策树

* 为什么需要GBDT？

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



* 损失函数:$$L(y_i,r) = \frac{1}{2}(y_i-r)^2$$ 

  计算损失函数的导数，最小损失时，r=y
  
*  初始值的确定？
初始值$$f_0$$,是L取最小值时(y=r),r的均值；$$f_0 = \frac{1}{N}\sum_{i=1}^{N} y_i$$

* 步骤a，计算本轮每个样本的残差；也就是损失函数L的负梯；
cart回归树划分切割点，实际使用的是残差(负梯度)进行数据的拟合？
因为$$f_0 + 残差拟合值f_m + 最终剩余残差r_m$$ 等于真实y值；

* 步骤b，是回归树进行(j,s)切分点过程？切分依据方差最小：$$min\{\frac{1}{N_1}\sum_{x_i\in R1}(y_i-c_1)^2 +\frac{1}{N_2} \sum_{x_j\in R2}(y_j-c_2)^2\}$$

* 步骤c，计算了使损失和最小的拟合值。。 

* 步骤d 最难理解的是定义域x的空间划分$$R_{jm}$$？

* 最终值：$$f_M(x)$$  
$$f(x)=f_M(x)=f_0(x) + \sum_{m=1->M}\sum_{j=1->J}r_{jm}I(x\in R_{jm})$$

* 算法另一个难点：怎么了理解用残差来拟合数据？为什么用残差？
 
 
 
 ## 三、实例演示GBDT算法

![](/assets/2-gdbt-jibenyuanli-2.jpeg)


训练数据有4条，2个特征(age,weight),结论是训练模型预测身高？










## 参考：


1、https://plushunter.github.io/2017/01/22/%E6%9C%BA%E5%99%A8%E5%AD%A6%E4%B9%A0%E7%AE%97%E6%B3%95%E7%B3%BB%E5%88%97%EF%BC%887%EF%BC%89%EF%BC%9AGBDT/

这篇文章：总结了回归树，BDT，GBDT

2、https://blog.csdn.net/zpalyq110/article/details/79527653
这篇文章：有实例演示GBDT算法的创建过程


3、http://aandds.com/blog/ensemble-gbdt.html

GBDT: 梯度提升算法 + CART回归树

gradient： 梯度  -》负梯度就是残差 
boosting： k个基本模型的叠加
DT: 回归决策树

4、http://www.cnblogs.com/bentuwuying/p/6667267.html

基于GBDT的景点论文的博文：《Greedy Function Approximation：A Gradient Boosting Machine》










