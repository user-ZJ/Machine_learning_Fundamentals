# 机器学习基础

## 环境配置
请在环境配置目录下查看  


## 机器学习中的两类问题

    分类：把数据划分成不同的类别
    回归：建立数据间的连续关系

## 方差和协方差区别
均值：
![](image/junzhi.png)

方差：
![](image/fangcha.png)

协方差：
![](image/xiefangcha.png)

方差和协方差区别：
1. 方差的计算公式，我们知道方差的计算是针对一维特征，即针对同一特征不同样本的取值来进行计算得到；而协方差则必须要求至少满足二维特征。可以说方差就是协方差的特殊情况。  　
2. 方差和协方差的除数是n-1，这样是为了得到方差和协方差的无偏估计


## 梯度下降法

批量梯度下降  
随机梯度下降  
小批量梯度下降  

https://github.com/user-ZJ/Supervised-learning/tree/master/%E7%BA%BF%E6%80%A7%E5%9B%9E%E5%BD%92

## 正则化
https://github.com/user-ZJ/Supervised-learning/tree/master/%E7%BA%BF%E6%80%A7%E5%9B%9E%E5%BD%92


## 熵
参考：https://blog.csdn.net/tsyccnh/article/details/79163834  

物理学熵表示粒子移动的自由度，熵越大，自由度越高；在此，表示数据离散程度  
![](https://i.imgur.com/THAEr6Y.png)

### 信息熵
信息熵（information_entropy）是度量样本集合纯度最常用的指标  
![](https://i.imgur.com/yR7Ttvc.png)  
n代表事件发生的n种可能性  
**信息熵值越小，样本纯度越高**

### 信息增益
信息增益为分类前的信息熵减去分类后的信息熵；  
假定离散属性a有V个可能的取值，若使用a来对样本集X进行划分，则会产生V个分支节点，其中第v个分支节点包含了X中所有在属性a上取值为av的样本，记为![样本集](https://i.imgur.com/aB0VWKW.png)，![样本数](https://i.imgur.com/wBNljom.png)为![样本集](https://i.imgur.com/aB0VWKW.png)中样本数，信息增益公式如下：  
![](https://i.imgur.com/LyNq1Ub.png)  
**信息增益越大，使用属性a来进行划分所获得的纯度提升越大**


### 相对熵（KL散度）
相对熵又称KL散度,如果我们对于同一个随机变量 x 有两个单独的概率分布 P(x) 和 Q(x)，我们可以使用 KL 散度（Kullback-Leibler (KL) divergence）来衡量这两个分布的差异  
![](https://i.imgur.com/F2jfD2w.png)  
n为事件的所有可能性
** DKL的值越小，表示q分布和p分布越接近 **

### 交叉熵
对相对熵变形可以得到  
![](https://i.imgur.com/uOmh5A7.png)  
等式的前一部分恰巧就是X在P(x)分布上的信息熵，等式的后一部分，就是交叉熵  
![](https://i.imgur.com/TU1cnB8.png)  
在机器学习中，我们需要评估label和predicts之间的差距，使用KL散度刚刚好，由于KL散度中的前一部分−H(X)不变，故在优化过程中，只需要关注交叉熵就可以了。所以一般在机器学习中直接用用交叉熵做loss，评估模型。











