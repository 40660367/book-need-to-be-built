---
title: "sklearn线性建模之贝叶斯岭回归"
meta_title: ''
meta_description: ''
keywords: 
    - sklearn
    - sklearn线性建模之贝叶斯岭回归
    - bayis
sidebar: "sklearn"
---
# sklearn线性建模之贝叶斯岭回归

贝叶斯回归允许自然机制通过使用概率分布而不是点估计来制定线性回归来生存数据不足或分布不良的数据。假定输出或响应“ y”是从概率分布中得出的，而不是估计为单个值。

在数学上，为了获得完全概率模型，假定响应y是围绕X的高斯分布$X_{w}$如下





$$

p\left(y\arrowvert X,w,\alpha\right)=N\left(y\arrowvert X_{w},\alpha\right)

$$


贝叶斯回归最有用的一种类型是贝叶斯岭回归，它估计了回归问题的概率模型。在这里，系数w的先验由球面高斯给出，如下所示-



$$

p\left(w\arrowvert \lambda\right)=N\left(w\arrowvert 0,\lambda^{-1}I_{p}\right)

$$



## 参量

下表包含**BayesianRidge**模块使用的参数-

| 序号 | 参数及说明                                                   |
| ---- | ------------------------------------------------------------ |
| 1个  | ***n_iter** -int，可选*它表示最大迭代次数。缺省值是300，但用户定义的值必须大于或等于1。 |
| 2    | ***fit_intercept-**布尔值，可选，默认为True*它决定是否计算该模型的截距。如果将其设置为false，则不会在计算中使用截距。 |
| 3    | ***tol** -float，可选，默认= 1.e-3*它表示解决方案的精度，并且在w收敛时将停止算法。 |
| 4    | ***alpha_1-**浮动，可选，默认= 1.e-6*它是1个第一超参数是用于事先在阿尔法参数Gamma分布的形状参数。 |
| 5    | ***alpha_2** −浮动，可选，默认= 1.e-6*它是第二个超参数，它是相对于alpha参数而言Gamma分布的反比例参数。 |
| 6    | ***lambda_1-**浮点数，可选，默认值= 1.e-6*它是第一个超参数，它是先于lambda参数的Gamma分布的形状参数。 |
| 7    | ***lambda_2-**浮点数，可选，默认值= 1.e-6*它是第二个超参数，它是先于lambda参数的Gamma分布的反比例参数。 |
| 8    | ***copy_X-**布尔值，可选，默认= True*默认情况下为true，这意味着将复制X。但是，如果将其设置为false，则X可能会被覆盖。 |
| 9    | ***compute_score-**布尔值，可选，默认= False*如果设置为true，它将在优化的每次迭代时计算对数边际可能性。 |
| 10   | ***详细** -布尔值，可选，默认= False*默认情况下为false，但如果设置为true，则在拟合模型时将启用详细模式。 |

## 属性

followings表包含**BayesianRidge**模块使用的属性-

| 序号 | 属性和说明                                                   |
| ---- | ------------------------------------------------------------ |
| 1个  | ***coef_** −数组，shape = n_features*此属性提供权重向量。    |
| 2    | ***拦截** _-浮动*它代表决策功能中的独立项。                  |
| 3    | ***alpha_-**浮动*此属性提供了估计的噪声精度。                |
| 4    | ***lambda_-**浮点数*此属性提供重量的估计精度。               |
| 5    | ***n_iter_-**整数*它提供了算法达到停止标准所需的实际迭代次数。 |
| 6    | ***sigma_** -阵列，形状=（n_features，n_features）*它提供了权重的估计方差-协方差矩阵。 |
| 7    | ***scores_-**数组，形状=（n_iter_ + 1）*它提供了每次优化迭代的对数边际似然值。在所得到的得分，所述阵列具有用于的初始值所获得的对数边缘似然的值开始一个一个Ñ dλ一种一种ñdλ𝜆，并以估算出的a的值结尾一个Ñ dλ一种一种ñdλ。 |

### 实施实例

以下Python脚本提供了使用sklearn **BayesianRidge**模块拟合Bayesian Ridge回归模型的简单示例。

```python
from sklearn import linear_model
X = [[0, 0], [1, 1], [2, 2], [3, 3]]
Y = [0, 1, 2, 3]
BayReg = linear_model.BayesianRidge()
BayReg.fit(X, Y)
```

从上面的输出中，我们可以检查计算中使用的模型参数。

现在，一旦拟合，模型可以预测新值，如下所示：

```python
BayReg.predict([[1,1]])
```

类似地，我们可以如下访问模型的系数w-

```python
BayReg.coef_
```
<code class=backend-type backend-type=free></code>
<code class=gatsby-kernelname data-language=python></code>
<script type="text/javascript" src="https://cdn.freeaihub.com/asset/js/cell.js"></script>
