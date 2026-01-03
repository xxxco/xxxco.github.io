---
layout: post
title: Regression Models
description: >
  Mathematical formula (from statistics and math perspective) and python implementation for different types of regression models
# image: 
#   path: /assets/img/blog/recommend.jpg
#   srcset:
#     1060w: /assets/img/blog/recommend.jpg
#     530w:  /assets/img/blog/recommend_50.jpg
#     265w:  /assets/img/blog/recommend_25.jpg
sitemap: false
hide_last_modified: true
---

# Regression Models in ML

* toc
{:toc .large-only}

## What is Regression?

Regression is a statistical approach used to analyze the relationship between a dependent variable (target variable) and one or more independent variables (predictor variables). The objective is to determine the most suitable function that characterizes the connection between these variables.

It seeks to find the best-fitting model, which can be utilized to make **predictions** or draw **conclusions**.

It is a supervised machine learning technique, used to predict the value of the dependent variable for new, unseen data. It models the relationship between the input features and the target variable, allowing for the estimation or prediction of numerical values.

## Simple Linear Regression (SLR)
This is the simplest form of regression, where the relationship between the independent and dependent variables is assumed to be linear. The goal is to find the best-fitting line (or hyperplane in higher dimensions) that minimizes the difference between predicted and actual values.

### Data
`y` is the response variable and `X` is the dependent variable in matrix format.

$$
y = \begin{vmatrix} y_1 \\ ... \\ y_n \end{vmatrix}， X = \begin{vmatrix} x_1^T \\ ... \\ x_n^T \end{vmatrix}$$

### Model
The formula for the linear regression model is:

$$
y = Xw + \epsilon, \text{where} \  y \in \mathbb{R}^n, X \in \mathbb{R}^{n \cdot d}, \epsilon \in \mathbb{R}^n $$

where `d` is the number of features of the input, `n` is the number of datapoints

### Criterion
The loss function:

$$
L(w) = \frac{1}{n} \sum_{i=1}^{n} (y_i - X_i w)^2
$$

The matrix format is:

$$
L(w) = (y - Xw)^T(y - Xw)
$$

### Optimization (Training)
The optimization procedure is to using [[gradient descent]] to set derivative to zero to obtain the parameters `w`. The derivation of closed form `w` obtained from gradient descent is:

$$
w = \underset{w \in \mathbb{R}^d}{\text{argmin}} L(w)$$

$$
w = \underset{w \in \mathbb{R}^d}{\text{argmin}} (y - Xw)^T(y - Xw)
$$

Derivation:

$$\begin{align*} 
\nabla_w L(w) &= -2X^T(y - Xw)\\
&= -2X^Ty + 2X^TXw \\
&= 0\end{align*}
$$

Thus, the closed form solution is:

$$
\begin{align*} 
\nabla_w L(w) &= 0\\
-2X^Ty + 2X^TXw &= 0 \\
w &= (X^TX)^{-1}X^Ty\end{align*}
$$

### Python Implementation

~~~python
import numpy as np

class LinearRegression:
    def __init__(self, print_cost=False):
        self.lr = 0.01
        self.epochs = 10000

    def y_hat(self, X, w):
        return np.dot(w.T, X)
    
    def cost(self, yhat, y):
        L = (1/self.m) * np.sum(np.power(yhat - y, 2))

    def gradient_descent(self, w, X, y, yhat):
        dCdW = 2 / self.m * np.dot(X, (yhat - y).T)
        w = w - self.lr * dCdW

        return w

    def main(self, X, y):
        # add x1 = 1
        ones = np.ones((1, X.shape[1]))
        X = np.append(ones, X, axis=0)

        self.m = X.shape[1]
        self.n = X.shape[0]

        w = np.zeros((self.n, 1))

        for it in range(self.total_iterations + 1):
            yhat = self.y_hat(X, w)
            cost = self.cost(yhat, y)

            if it % 2000 == 0 and self.print_cost:
                print(f"Cost at iteration {it} is {cost}")

            w = self.gradient_descent(w, X, y, yhat)

        return w

if __name__ == "__main__":
    X = np.random.rand(1, 500)
    y = 3 * X + 5 + np.random.randn(1, 500) * 0.1
    regression = LinearRegression()
    w = regression.main(X, y)
~~~

## Multiple Linear Regression (MLR)
Multiple linear regression (MLR), also known simply as multiple regression, is a statistical technique that uses several explanatory variables to predict the outcome of a response variable
Multiple linear regression is an extension of linear regression that uses just one explanatory variable
Multiple linear regression is used extensively in econometrics and financial inference.

### data
`y` is the response variable and `X` is the data matrix

$$
y = \begin{vmatrix} y_1 \\ ... \\ y_n \end{vmatrix}，  X = \begin{vmatrix} x_1^T \\ ... \\ x_n^T \end{vmatrix}
$$

### Model
The formula for the linear regression model is:

$$
y = Xw + \epsilon, \text{where} \  y \in \mathbb{R}^n, X \in \mathbb{R}^{n \cdot d}, \epsilon \in \mathbb{R}^n
$$

where `d` is the number of features of the input, `n` is the number of datapoints. Compared to linear regression, each data point contains `d` observations instead of 1 observation.

### Criterion (Loss)
The loss function:

$$ 
L(w) = \frac{1}{n} \sum_{i=1}^{n} (y_i - X_i w)^2 
$$

The matrix format is:

$$
L(w) = (y - Xw)^T(y - Xw)
$$

### Optimization (Training)
The optimization procedure is to using [[gradient descent]] to set derivative to zero to obtain the parameters `w`. The derivation of closed form `w` obtained from gradient descent is:

$$
w = \underset{w \in \mathbb{R}^d}{\text{argmin}} L(w)
$$

$$
w = \underset{w \in \mathbb{R}^d}{\text{argmin}} (y - Xw)^T(y - Xw)
$$

Derivation:

$$
\begin{align*} 
\nabla_w L(w) &= -2X^T(y - Xw)\\
&= -2X^Ty + 2X^TXw \\
&= 0\end{align*}
$$

Thus, the closed form solution is:

$$
\begin{align*} 
\nabla_w L(w) &= 0\\
-2X^Ty + 2X^TXw &= 0 \\
w &= (X^TX)^{-1}X^Ty\end{align*}
$$


### Discussion
- Advantages:
	- Explainable method
	- Interpretable results by its output coefficient
	- Faster to train than other machine learning models
- Disadvantages:
	- Assumes linearity between inputs and output
	- Sensitive to outliers
	- Can underfit with small, high-dimensional data