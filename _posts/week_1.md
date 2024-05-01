## 机器学习算法原理

### 回归问题

$$
y=\theta_1 x_1 + \theta_2 x_2 + \theta_0
$$

#### 例子

对于已有数据的两个特征（工资年龄），目标得到银行能给予的贷款数（标签)。

| 工资 | 年龄 | 额度  |
| ---- | ---- | ----- |
| 4000 | 25   | 20000 |
| 8000 | 30   | 70000 |

考虑两个特征对结果的影响不同，所以我们要求出最合适的两个参数θ来表示该回归方程（找出最合适的线，能拟合可能多的数据点）。

所以构建拟合平面
$$
h_\theta(x)=\theta_1 x_1 + \theta_2 x_2 + \theta_0 \\
偏置项 \theta_0（只影响平面的上下移动，不对结果造成较大影响）\\
$$
为了转换成矩阵的处理,把x0全设为1

| x0   | x1    | x2   |
| ---- | ----- | ---- |
| 1    | 4000  | 25   |
| 1    | 8000  | 30   |
| 1    | 12000 | 24   |

可整合为：
$$
h_\theta(x)=\sum_{i=0}^n\theta_i x_i=\theta^Tx
$$

**误差**

对于每一个样本真实值y和预测值h(x)之间存在的差异：
$$
y^{(i)}=\theta^Tx^{i}+\varepsilon^{i}
$$
我们希望误差越小越好。

由于误差服从高斯分布:
$$
p(\varepsilon^{(i)})=\frac{1}{\sqrt{2\pi}\sigma}\exp(-\frac{(\varepsilon^{(i)})^2}{2\sigma^2})
$$
我们需要求的是参数θ，所以将这个式子带入上式，得到一个关于θ的式子
$$
p=\frac{1}{\sqrt{2\pi}\sigma}\exp(-\frac{(y^{(i)}-\theta^Tx^{(i)})^2}{2\sigma^2})
$$
样本之间***独立同分布***，所以**联合概率密度**可以用**边缘概率密度**的乘积，所以此时有似然函数：
$$
L(\theta)=\prod_{i=1}^m\frac{1}{\sqrt{2\pi}\sigma}\exp(-\frac{(y^{(i)}-\theta^Tx^{(i)})^2}{2\sigma^2})
$$
此时为了方便求出最合适的θ，取对数转为对数似然。
$$
logL(\theta)=log\prod_{i=1}^m\frac{1}{\sqrt{2\pi}\sigma}\exp(-\frac{(y^{(i)}-\theta^Tx^{(i)})^2}{2\sigma^2})
$$
此时要得到似然函数的值越大越好（概率越大越接近真实值），对上式子展开化简有：
$$
\sum log\frac{1}{\sqrt{2\pi}\sigma}\exp(-\frac{(y^{(i)}-\theta^Tx^{i})^2}{2\sigma^2})=mlog\frac{1}{\sqrt{2\pi}\sigma}-\frac{1}{\sigma^2}\frac{1}{2}\sum_{i=1}^m(y^{(i)}-\theta^Tx^{(i)})^2
$$
所以我们希望右边越小越好，即最小二乘法:
$$
J(\theta) = \frac{1}{2}\sum_{i=1}^m(y^{(i)}-\theta^Tx^{(i)})^2
$$
此时对矩阵进行展开
$$
J(\theta) = \frac{1}{2}\sum_{i=1}^m(y^{(i)}-\theta^Tx^{(i)})^2=\frac{1}{2}(X\theta-y)^T(X\theta-y)
$$
此时求偏导
$$
\frac{\partial J}{\partial \theta} = X^TX\theta - X^Ty=0
$$
得到(在X'X可逆时)：
$$
\theta = (X^TX)^{-1}X^Ty
$$
对于我们上面得到的**目标函数**，对于**线性回归可解**而言仅是一个特例，大部分的目标函数不一定可解，所以真正机器学习上的一种思路（让**损失函数**越小越好）：

#### 梯度下降

我们目标是得到偏导为0的参数θ，所以我们希望沿着梯度的反方向找到那个最低点（偏导为0），此时的参数是最优的。

目标函数：
$$
J(\theta_0,\theta_1) = \frac{1}{2m}\sum_{i=1}^m(h_\theta(x^{(i)})-y^{(i)})
$$
按照方向和步伐去更新两个θ，分别去求他们的最优（样本之间独立，参数之间亦独立）。

**目标函数**
$$
J(\theta) = \frac{1}{2m}\sum_{i=1}^m(y^{(i)}-h_\theta(x^{(i)})^2
$$

1. ##### 批量梯度下降

$$
\frac{\partial J(\theta)}{\partial \theta_j} = -\frac{1}{m}\sum_{i=1}^m(y^i-h_\theta(x^i))x_j^i\\
\theta_j{'} = \theta + \frac{1}{m}\sum_{i=1}^m(y^i-h_\theta(x^i))x_j^i
$$

通过这种对全体样本进行考虑，很容易得到最优解，**但在样本数量太大的时候会有速度慢的缺点。**

2. ##### 随机梯度下降

$$
\theta_j{'} = \theta + (y^i-h_\theta(x^i))x_j^i
$$

该方法每次只找一个样本，迭代速度确实很快，但不一定都朝着收敛的方向

3. ##### 小批量梯度下降

最常用的方法,每次更新选择一小部分数据来算。（batch 一般设64 128 256等）
$$
\theta_j{'} = \theta -\alpha \frac{1}{10}\sum_{k=i}^{i+9} (y^i-h_\theta(x^i))x_j^i
$$
其中\alpha 表示步长（学习率） ， 学习率对结果会产生巨大的影响，一般小一些。

## 线性回归代码

例 对不同变量得到Happiness

```
"Happiness.Rank","Happiness.Score","Whisker.high","Whisker.low","Economy..GDP.per.Capita.","Family","Health..Life.Expectancy.","Freedom"
```

#### 数据处理

首先对数据进行处理

```python
#预处理数据
(data_processed,
         features_mean, 
         features_deviation)  = prepare_for_training(data, polynomial_degree, sinusoid_degree,normalize_data=True)
#更新得到的data以及其它labels等
self.data = data_processed
#self.~ = ~

#\theta参数的个数是data列的数，所以通过shape[1]得到
num_features = self.data.shape[1]
#最终初始化参数矩阵
self.theta = np.zeros((num_features,1))
```

#### 梯度下降

上述步骤完成后进行训练模块，执行梯度下降：

```python
def train(self , alpha , num_iterations = 500):
    #还未完善
def gradient_descent(self,alpha,num_iterations):
    for _ in range(num_iterations):
        #每次循环都去执行gradient_step函数
        self.gradient_step(alpha)
def gradient_step(self,alpha):
    #拿出样本个数
    num_examples = self.data.shape[0];
    #预测值等于数据的属性乘以参数
    prediction = LinearRegression.hypothesis(self.data , self.theta)
	#预测值-真实值label
    delta = predction - self.labels
    #delta 和 self.data 均是num_expamples行1列的矩阵，所以对delta进行转置
    #此时得到的theta 可能按顺序θ_1..均是num_expamples行1列的矩阵一行展示，对结果再进行转置
    theta = self.theta - alpha*(1/num_examples)*(np.dot(delta.T*self.data)).T
    #此时再更新theta
    self.theta = theta
	@staticmethod
    def hypothesis(data , theta):
    predictions = np.dot(data , theta)
    return predictions
```

#### 损失与预测

在上述梯度下降函数里，添加cost_history,看每次变化的展示

```python
def gradient_descent(self,alpha,num_iterations):
    cost_history = []
    for _ in range(num_iterations):
        #每次循环都去执行gradient_step函数
        self.gradient_step(alpha)
        cost_history.append(self.cost_function(self.data,self.labels))
        return cost_history
    	cost_history.append(self.cost_function(self.data , self.labels))
def cost_function(self , data, labels):
    num_examples = data.shape[0]
    #预测值减去真实值
    delta = LinearRegression.hypothesis(self.data , self.theta) - labels
    cost = (1/2)*np.dot(delta.T,delta)
    # 观察 合适的cost print(cost.shape) 并return
    return cost[0][0]
def predict(self,data):
        data_processed = prepare_for_training(data,
         self.polynomial_degree,
         self.sinusoid_degree,
         self.normalize_data
         )[0]
        predictions = LinearRegression.hypothesis(data_processed,self.theta)
        return predictions
```

此时把梯度下降代码逻辑完成，开始完善train函数逻辑

```python
def train(self , alpha , num_iterations = 500):
    cost_history = self.gradient_descent(alpha,num_iterations)
    return self.theta,cost_history
```

切割训练集测试集经过前面训练，将得到的**cost_history**打印出来：

```python
#num_iterations = 500
#learning_rate = 0.01
linear_regression = LinearRegression(x_train,y_train)
(theta,cost_history) = linear_regression.train(learning_rate,num_iterations)

print ('开始时的损失：',cost_history[0]) #开始时的损失： 14.704882632577782
print ('训练后的损失：',cost_history[-1]) #训练后的损失： 0.2051154002094022
```

得到一个收敛的结果：

![image-20240412164909325](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240412164909325.png)

梯度下降符合预期，损失函数不断变小。

最终模拟出回归曲线:

```python
predictions_num = 100
x_predictions = np.linspace(x_train.min(),x_train.max(),predictions_num).reshape(predictions_num,1)
y_predictions = linear_regression.predict(x_predictions)

plt.scatter(x_train,y_train,label='Train data')
plt.scatter(x_test,y_test,label='test data')
plt.plot(x_predictions,y_predictions,'r',label = 'Prediction')
plt.xlabel(input_param_name)
plt.ylabel(output_param_name)
plt.title('Happy')
plt.legend()
plt.show()
```

结果：

![image-20240412165109501](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20240412165109501.png)

```
PS: 学习了 动态规划 大盗阿福 数字三角形 01背包问题
```

