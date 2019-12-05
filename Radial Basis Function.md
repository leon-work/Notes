# Radial basis function interpolation
## Introduction
Given $n$ distinct points $x_{1},x_{2},...,x_{n}\in\mathbb{R^{d}}$ where the objective function values $f(x_{1}),f(x_{2}),...,f(x_{n})$ are known.

Radial Basis interpolation:
$$
s_{n}(x)=\sum_{i=1}^{n}\lambda_{i}\phi\left(\parallel x-x_{i}\parallel\right)+p\left(x\right),x\in\mathbb{R^{d}} \\
\phi(r)=r^3
$$
where $\parallel x-x_{i}\parallel$ is the Euclidean norm, $\lambda_{i}\in\mathbb{R^{d}}$ for $i=1,..,n$, $p(x)$ is linear polynomial in $d$ variables.

## Matrix notation

* $\varPhi\in\mathbb{R}^{n\times n},\varPhi_{ij}=\phi\left(\parallel x_{i}-x_{j}\parallel\right),i,j=1,...,n.$ 
  $$
  \varPhi_{n\times n}=\begin{bmatrix}\phi\left(\parallel x_{1}-x_{1}\parallel\right) & \phi\left(\parallel x_{1}-x_{2}\parallel\right) & \cdots & \phi\left(\parallel x_{1}-x_{n}\parallel\right)\\
  \phi\left(\parallel x_{2}-x_{1}\parallel\right) & \phi\left(\parallel x_{2}-x_{2}\parallel\right) & \cdots & \phi\left(\parallel x_{2}-x_{n}\parallel\right)\\
  \vdots & \vdots & \ddots & \vdots\\
  \phi\left(\parallel x_{n}-x_{1}\parallel\right) & \phi\left(\parallel x_{n}-x_{2}\parallel\right) & \cdots & \phi\left(\parallel x_{n}-x_{n}\parallel\right)
  \end{bmatrix}
  $$

* $P\in\mathbb{R}^{n\times\left(d+1\right)}$.
  $$
  P_{n\times\left(d+1\right)}=\begin{bmatrix}1 & x_{1}^{T}\\
  1 & x_{2}^{T}\\
  \vdots & \vdots\\
  1 & x_{n}^{T}
  \end{bmatrix}=\begin{bmatrix}1 & x_{11} & x_{12} & \cdots & x_{1d}\\
  1 & x_{21} & x_{22} & \cdots & x_{2d}\\
  \vdots & \vdots & \vdots & \ddots & \vdots\\
  1 & x_{n1} & x_{n2} & \cdots & x_{nd}
  \end{bmatrix}
  $$

* $F,\lambda\in\mathbb{R}^{n}.\;$$C\in\mathbb{R}^{d+1}$.
  $$
  F=\begin{bmatrix}f\left(x_{1}\right)\\
  f\left(x_{2}\right)\\
  \vdots\\
  f\left(x_{n}\right)
  \end{bmatrix},\lambda=\begin{bmatrix}\lambda_{1}\\
  \lambda_{2}\\
  \vdots\\
  \lambda_{n}
  \end{bmatrix},C=\begin{bmatrix}c_{0}\\
  c_{1}\\
  \vdots\\
  c_{d}
  \end{bmatrix}
  $$

Radial Basis Interpolant:

$$
\begin{bmatrix}\varPhi_{n\times n} & P_{n\times\left(d+1\right)}\\
P_{\left(d+1\right)\times n} & 0_{\left(d+1\right)\times\left(d+1\right)}
\end{bmatrix}\centerdot\begin{bmatrix}\lambda_{n}\\
c_{d+1}
\end{bmatrix}=\begin{bmatrix}F_{n}\\
0_{\left(d+1\right)}
\end{bmatrix}
$$

## Jacobin Matirx

Cubic Interpolant.
$$
\phi(r)=r^3 \\
s_{n}(x)=\sum_{i=1}^{n}\lambda_{i}\epsilon^{3}\parallel x-x_{i}\parallel^{3}+p\left(x\right),x\in\mathbb{R^{d}}
$$

> Norm 2 partial derivative: 
> $$
> F(\boldsymbol{x})	=\|\boldsymbol{x}\| \\
> \frac{\partial F}{\partial x_{n}}	=\frac{x_{n}}{\|\boldsymbol{x}\|}
> $$
> 

> Let $G\left(\boldsymbol{x}\right)=\boldsymbol{x}-\boldsymbol{y}$. Then $F\left(G\left(\boldsymbol{x}\right)\right)=\|\boldsymbol{x}-\boldsymbol{y}\|$. Then the chain rule gives:
> $$
> \frac{\partial F\circ G}{\partial x_{n}}(\boldsymbol{x})=\frac{x_{n}-y_{n}}{\|\boldsymbol{x}-\boldsymbol{y}\|}\frac{\partial G}{\partial x_{n}}(\boldsymbol{x})
> $$

So. Let $T\left[F\left(G\left(\boldsymbol{x}\right)\right)\right]=\|\boldsymbol{x}-\boldsymbol{y}\|^{3}$. 
$$
\frac{\partial T\circ F\circ G}{\partial x_{n}}(\boldsymbol{x})=3*\|\boldsymbol{x}-\boldsymbol{y}\|^{2}\frac{x_{n}-y_{n}}{\|\boldsymbol{x}-\boldsymbol{y}\|}=3*\|\boldsymbol{x}-\boldsymbol{y}\|\left(x_{n}-y_{n}\right)
$$
Then. 
$$
\frac{\partial s\left(x\right)}{x_{j}}=\sum_{i=1}^{n}\lambda_{i}\epsilon^{3}\times3\times\|\boldsymbol{x}-\boldsymbol{x}_{i}\|\left(x_{j}-x_{ij}\right)+c_{j}
$$
