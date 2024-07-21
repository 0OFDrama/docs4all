# 线性模型

本页用于记录机器学习里面的线性模型，

在理论上，我们会介绍这些模型的数学定义-定理-证明过程，

在实现上，我们采用sklearn库为模板，同时基于Numpy，pandas，SciPy，matplotlib给出写法。

在写法上，我们会分为实现部分和数据导入与测试部分，并且附上github连接。

We assume that predicted value is a vector $\hat{y}$:
$$
\hat{y}(w, x)=w_0+w_1x_1+...+w_px_p
$$

## Ordinary Least Squares

In the context of linear regression, a widely used method to fit models involves minimizing the sum of squared residuals between the observed targets and the predicted values. This is achieved by optimizing the coefficients \( w = (w_1, ..., w_p) \).
$$
\min\limits_{w}\Vert Xw-y\Vert_2^2
$$

普通最小二乘法（OLS）的系数估计依赖于特征（自变量）的独立性。当特征之间存在相关性，且设计矩阵（即特征矩阵）的列具有近似线性依赖关系时，设计矩阵会变得接近奇异（即行列式接近于零）。这种情况下，最小二乘估计对观察目标中的随机误差变得非常敏感，导致估计的方差很大。这种多重共线性的情况可能发生，例如，当数据是在没有实验设计的情况下收集的。