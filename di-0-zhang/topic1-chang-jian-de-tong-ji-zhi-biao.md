# topic1 - 常见的统计指标





| 指标 | 计算 | 意义 |
| :--- | :--- | :--- |
|  |  |  |
|  |  |  |
|  |  |  |
| pearson 相关系数 |$$r_{xy} = cov(x,y)/𝛅_{x}𝛅_{y}$$|  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |



* 期望:

$$E(x) = \sum_{N}(x_i* p_i) = 1/N * \sum(x_i)$$

意义：随机变量的平均值；

* 方差：

$$var(x) = D(x) = 1/(n-1)\sum(x-E(x)^2)$$

除以：n-1 部分样本，保持无偏估计；
除以：n，是全部样本


* 协方差

$$cov(x,y) = E((E(x)-x)(E(y)-y))$$

如果x=y,协方差就是方差；


```python

# Sample Date - SH000300 Earning in 2017-03

datas = [0.16, -0.67, -0.21, 0.54, 0.22, -0.15, -0.63, 0.03, 0.88, -0.04, 0.20, 0.52, -1.03, 0.11, 0.49, -0.47, 0.35, 0.80, -0.33, -0.24, -0.13, -0.82, 0.56]

mean1 = sum(datas)/len(datas) # result =  0.0060869565217391355

square_datas = []

for i in datas:

square_datas.append((i-mean1)*(i-mean1))

variance = sum(square_datas)/len(square_datas)

print(str(variance))

# result = 0.25349338374291114

 

# 当然如果你使用了numpy，那么求方差将会十分的简单：

import numpy as np

datas = [0.16, -0.67, -0.21, 0.54, 0.22, -0.15, -0.63, 0.03, 0.88, -0.04, 0.20, 0.52, -1.03, 0.11, 0.49, -0.47, 0.35, 0.80, -0.33, -0.24, -0.13, -0.82, 0.56]

variance = np.var(datas)

print(str(variance))

# result = 0.253493383743


```


* pearson 相关系数

$$p_{xy} = cov(x,y)/𝛅_x𝛅_y$$










