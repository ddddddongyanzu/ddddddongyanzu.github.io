---
Layout: post
desc: chapter2-线性模型
title:  线性模型
tag:  study
---



## 线性模型

### 基本形式

给定的d个属性描述的$\pmb{x}$= $(x_1;x_2;...;x_d)$,其中的$x_i$为$ \pmb{x}$ 在第i个元素上的取值。
$$
f(x)=w_1 x_1 + w_2 x_2+ ...+w_dx_d + b
$$
一般向量形式写成$ f(x) = w^Tx+b$，其中$\pmb{w}$= $(w_1;w_2;...;w_i)$,所以$\pmb{w^T}$= $(w_1,w_2,...,w_i)$

当我们面对上面模型时，将$w$和$b$学得了之后，模型也就确定了下来，试图学得：$ f(x_i)=w x_i+ b$ 使$f(x_i) \simeq y_i$.

### 线性回归

给定数据集$D = {(\pmb{x_1},y_1),(\pmb{x_2},y_2),...,(\pmb{x_m},y_m)}$，其中$\pmb{x_i}$= $(x_{i1};x_{i2};...;x_{id})$，$ y_i ∈ R$.

**对于离散属性**

若属性值间存在序关系，可通过连续化将其转化为连续值。(若将无序属性连续化，会不恰当地引入序关系，对后续处理造成误导。)

1. 存在序关系，转化为连续值。例如：高，矮 : {(1.0,0.0};高，中，低 : {1.0 , 0.5 , 0.0}

2. 不存在序关系，假定有k个属性值，通常转为k维向量。例如："西瓜" , "南瓜" , "黄瓜" : (0,0,1) ,(0,1,0),(1,0,0).  

**性能度量**

回归任务中，均方误差是最常用的性能度量，因此我们试图让均方误差最小化(要让其对数似然函数的值越大越好，这样概率越大越能说明模型越符合)。
$$
J(\theta) = \frac{1}{2}\sum_{i=1}^m(y^{(i)}-w^Tx^{(i)})^2
$$


证明:对于误差服从正态分布:
$$
p(\varepsilon^{(i)})=\frac{1}{\sqrt{2\pi}\sigma}\exp(-\frac{(\varepsilon^{(i)})^2}{2\sigma^2})\\\\y^{(i)}=w^Tx^{i}+\varepsilon^{i}\\\\p=\frac{1}{\sqrt{2\pi}\sigma}\exp(-\frac{(y^{(i)}-w^Tx^{(i)})^2}{2\sigma^2})\\\\logL(\theta)=log\prod_{i=1}^m\frac{1}{\sqrt{2\pi}\sigma}\exp(-\frac{(y^{(i)}-w^Tx^{(i)})^2}{2\sigma^2})\\\\\sum log\frac{1}{\sqrt{2\pi}\sigma}\exp(-\frac{(y^{(i)}-\theta^Tx^{i})^2}{2\sigma^2})=mlog\frac{1}{\sqrt{2\pi}\sigma}-\frac{1}{\sigma^2}\frac{1}{2}\sum_{i=1}^m(y^{(i)}-\theta^Tx^{(i)})^2
$$
得出来让该式子越大，也就让减号右边的内容越小。

试图让均方误差最小：
$$
(w^*,b^*) = \mathop{arg min}\limits_{(w,b)}\sum_{i=1}^m(f(x_i)-y_i)^2=\mathop{arg min}\limits_{(w,b)}\sum_{i=1}^m(y_i-wx_i-b)^2
$$
最小二乘法也就是找出一条直线，使所有样本到直线上的欧式距离之和最小。也就是之前看到的求偏导，通过梯度下降找到**w**与b。

一般来说，我们会得到最终的结果:
$$
w = (X^TX)^{-1}X^Ty
$$
此时就要分情况讨论:

1. $ X^TX$不是满秩矩阵，我们可以解除多个$\overset{-}{w}$,此时选择哪一个解作为输出，要由算法的**归纳偏好**决定，常用的做法是引入**正则化**项。

2. 若 $X^TX$满秩，那么结果$ w = (X^TX)^{-1}X^Ty$ 。为学习到的多元线性回归模型。

**对数线性回归**

我们可以对线性模型进行变化，若我们认为示例所对应的输出标记是在指数尺度上变化的，那么此时将输出标记的对数作为线性模型逼近的目标。
$$
lny = w^Tx+b
$$
这样就让我们试图用$ e^{w^Tx+b} $去逼近y，同时在形式上仍保持线性回归，但实际上是**求取输入空间到输出空间的非线性函数映射**。

> 这里对数函数起到了将线性回归模型的预测值和真实标记联系起来的作用

更为一般,考虑单调可微函数$g(·)$：
$$
y = g^{-1}(w^Tx+b)
$$
这样我们就得到了**广义线性模型**，其中$g(·)$称为联系函数，上面的对数线性回归也即广义线性模型在$g(·)=ln(·)$的一个特例。

### 对数几率回归

当面对分类任务时，我们只需找一个单调可微函数，将分类任务的**真实标记y**与线性回归模型的预测值联系起来。

对于二分类任务,其输出标记y∈{0，1}，线性回归模型的$z=w^Tx+b$是实值，所以我们需要利用联系函数，将实值z转化为0/1值。

最理想的是采用单调阶跃函数，但是单调阶跃函数并不连续，无法达到$g(·)$单调可微的条件。

单调阶跃函数:

![image-20240424144752794](https://github.com/ddddddongyanzu/m_learning/blob/main/pic/image-20240424144752794.png)

所以找了一个能在一定程度上近似单位阶跃函数的替代函数:

对数几率函数:
$$
y = \frac{1}{1+e^{-z}}
$$


![image-20240424145257270](https://github.com/ddddddongyanzu/m_learning/blob/main/pic/image-20240424145257270.png)

对数几率函数是一种"Sigmoid"函数，将z值转化为一个接近0或1的y值。
$$
y = \frac{1}{1+e^{-(w^Tx+b)}}\\\\ln(\frac{y}{1-y}) = w^Tx+b
$$
若此时将y视为样本 **x** 为正例的可能性，则1-y是其反例可能性，二者的比值:$\frac{y}{1-y}$称为几率，反映x作为正例的相对可能性。对几率取对数得到**对数几率**。

将上式y视为概率估计$ p(y=1|x)$,则上式可以改写为:
$$
ln(\frac{p(y=1|x)}{p(y=0|x)}) = w^Tx+b
$$
显然有
$$
p(y=1|x) = \frac{e^{w^Tx+b}}{1+e^{w^Tx+b}}\\\\
p(y=0|x) = \frac{1}{1+e^{w^Tx+b}}
$$
通过极大似然法，来估计$w,b$,给定数据集，对率回归模型最大化"对数似然",让每一个样本属于其真实标记的概率越大越好。
$$
\ell(w,b) = \sum_{i=1}^mlnp(y_i|x_i;w;b;)
$$

> ***做了一系列变化，暂时没看懂如何变换的，先记录下结果$\ell(\beta) = \sum_{i=1}^m(-y_i\beta^T\overset{-}{x_i}+ln(1+e^{\beta^T\overset{-}{x_i}}))$。***

得到了上述式子后，利用经典的数值优化算法，梯度下降算法，牛顿法都可以求得最优解。
$$
\beta^* = \mathop{arg min}\limits_{(\beta)}\ell(\beta)
$$

### 线性判别分析

给定训练样例集，设法将样例投影到一条直线上，使得**同类样例的投影点尽可能接近**、**异类样例的投影点尽可能远离**；而后在对新样本进行分类时，将其投影到同样的这条直线上，根据**投影点的位置**来**确定样本的类别**。

![image-20240426154405499](https://github.com/ddddddongyanzu/m_learning/blob/main/pic/image-20240426154405499.png)

对于绿色的为一类，红色的为二类：

1. 当$ P(Y=1|X=x) > P(Y=2|X=x)$此时应该将投影到x的点分为一类。
2. 当$ P(Y=1|X=x) < P(Y=2|X=x)$此时应该将投影到x的点分为二类。
3. 当$P(Y=1|X=x) =P(Y=2|X=x)$此时x的值为阈值，要进行进一步判定再分类。

所以我们的目的是找 **类内的方差小，类间的均值差别大**

由于向量在某一向量上的投影式子为

为向量x在u方向投影的长度:


$$
cos\theta = \frac{\pmb{xu}}{\lvert\lvert{x}\rvert\lvert{u}\rvert\lvert}\\\\
xcos\theta = xu
$$

> **通常考虑u长度为1**(这里还没很理解)

**可以得到 $ y = w^Tx $**

先求二者的均值
$$
\pmb{m_1} = \frac{1}{N_1}\sum_{n∈C_1} \pmb{x^n} , \pmb{m_2} = \frac{1}{N_2}\sum_{n∈C_2} \pmb{x^n}
$$
然后可以计算投影：
$$
m_2 - m_1 = \pmb{w^T(m2-m1)}
$$


$w^T$也即是我们所需要求得的目标的方向

> 通常还需要引入 $ w^Tw = 1$，然后解这个问题

$$
w^T(m_2 - m_1) + \lambda(w^Tw - 1)\\
\frac{ \partial L(w) }{ \partial w } = (m_2-m_1)+\lambda w = 0
$$

此时可以知道
$$
m_2-m_1\propto w
$$
![image-20240426162012047](https://github.com/ddddddongyanzu/m_learning/blob/main/pic/image-20240426162012047.png)

可以求得直线的方向，完成条件的第一步，但是可以从图中看出，投影有重叠，不方便我们进行分类，所以我们的目标还得让类间方差越小：

![image-20240426162128070](https://github.com/ddddddongyanzu/m_learning/blob/main/pic/image-20240426162128070.png)
$$
J(w) = \frac{(m_2-m_1)^2}{s_1^2+s_2^2}\\
s_k^2 = (y^i-m_k)^2
$$
**类间散度$S_b$矩阵与类内散度矩阵$S_w$**
$$
S_b = (m_2-m_1)(m_2-m_1)^T\\
S_w = \sum_0+\sum_1=\sum_{x∈X_0}(x-m1)(x-m1)^T+\sum_{x∈X_1}(x-m2)(x-m2)^T
$$
此时上式$J(w)$可以重写为:
$$
J(w) = \frac{w^TS_bw}{w^TS_ww}
$$

> 这段数学推导还要好好看看，最终结果

$ S_bW = \lambda S_wW$

### 多分类问题

有些二分类学习方法可直接推广到多酚类，更多情况，我们基于一些基本策略，利用二分类学习器来解决多分类问题。

**基本思路**

将多分类任务拆解成若干个二分类任务求解。所以如何拆解就是我们需要关注的重点:

1. 一对一 OvO
2. 一对多 OvR
3. 多对多 MvM