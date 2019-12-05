# Thermoacoustic
## Background
* [Nabla operator](https://en.wikipedia.org/wiki/Del)
$$
\nabla=\frac{\partial}{\partial x}\vec{i}+\frac{\partial}{\partial y}\vec{j}+\frac{\partial}{\partial z}\vec{k}
$$
* [Laplace operator](https://en.wikipedia.org/wiki/Laplace_operator)
$$
\Delta f=\nabla^{2}f=\frac{\partial^{2}f}{\partial x^{2}}+\frac{\partial^{2}f}{\partial y^{2}}+\frac{\partial^{2}f}{\partial z^{2}}
$$

* Thermal expansion coefficient 
$$
\beta\equiv-\frac{1}{\rho}(\frac{\partial\rho}{\partial T})_{p}
$$
##  理想流体媒质的三个基本方程
### 基本假设
1. 媒质不存在粘滞性，传播无损耗
2. 没有声扰动时，煤质宏观上静止，初速度为0，煤质中 $P_0​$, $\rho_0​$ 都是常数
3. 传播过程是绝热过程
4. 传播的是**小振幅**声波，各声学变量 $p,\nu,\rho^{'}​$ 都是一级微量

### 一维： $x$ 方向
1. 运动方程  ( $p$ & $\nu$ )
$$
\rho\frac{dv}{dt}=-\frac{\partial p}{\partial x}
$$

2. 连续性方程 ( $\nu$ & $\rho^{'}​$ )

$$
-\frac{\partial}{\partial x}(\rho v)=\frac{\partial\rho}{\partial t}
$$

3. 物态方程 ( $p$ &  $\rho^{'}$ )
$$
dp=(\frac{dP}{d\rho})_sd\rho \\
dP=c^{2}d\rho	\\
PV^{\gamma}=const \\
c^2 = \frac{\gamma P}{\rho}
$$

###  小振幅声波简化方程
* **$p,\nu,\rho^{'}​$ 以及它们随位置，时间的变化量都是微小量，可以忽略**
1. 运动方程
$$
dv = \frac{\partial v}{\partial x}dx+\frac{\partial v}{\partial t}dt \\
\frac{dv}{dt}=(\frac{\partial v}{\partial t}+v\frac{\partial v}{\partial x}) \\
\rho_{0}\frac{\partial v}{\partial t}=-\frac{\partial P}{\partial x}
$$

2. 连续性方程
$$
-\rho_{0}\frac{\partial v}{\partial x} = \frac{\partial \rho^{'}}{\partial{t}}
$$

3. 物态方程

$$
p = c^{2}_{0}\rho^{'}
$$

### 三维声波方程
$$
Momentum:\;\; \rho\frac{d\boldsymbol v}{dt}=-grad\;p \\
Continuity:\; -div(\rho\boldsymbol v)=\frac{\partial{\rho}}{\partial t}
$$

## 粘性流体基本方程
1. Continuity 
$$
-\nabla(\rho\boldsymbol v)=\frac{\partial{\rho}}{\partial t}
$$
2. Momentum
$$
\frac{d\boldsymbol{v}}{dt}=\frac{\partial\boldsymbol{v}}{\partial t}+(\boldsymbol{v}\cdot\nabla)\boldsymbol{v} \\
\rho[\frac{\partial\boldsymbol{v}}{\partial t}+(\boldsymbol{v}\cdot\nabla)\boldsymbol{v}]=-\nabla p+\mu\nabla^{2}\boldsymbol{v}
$$

3. Energy
* Open system ----  **Microscopic volume $dxdydz$**
$$
d\mathcal{E}=dQ-dW+(h+\frac{\lvert\boldsymbol{v}\rvert^{2}}{2})dM
$$
* Energy in volume
$$
d\mathcal{E}=d(\rho\epsilon+\frac{1}{2}\rho\lvert\boldsymbol{v}\rvert^{2})dxdydz
$$
* Net rate of heat flows into the control volum
$$
\Sigma\frac{dQ}{dt}=-\nabla\cdot(k\nabla T)dxdydz
$$
* **Energy Equation**
$$
\frac{\partial}{\partial t}(\rho\epsilon+\frac{1}{2}\rho\lvert\boldsymbol{v}\lvert^{2})=-\nabla\cdot[-k\nabla T-\boldsymbol{v}\cdot\boldsymbol\sigma^{'}+(\rho h+\frac{1}{2}\rho\lvert\boldsymbol{v}\lvert^{2})\boldsymbol{v}]
$$

4. Entropy

* Open system 
$$
dS =\frac {dQ}{T}+s \, dM+(dS)_{gen} \\(dS)_{gen}\geq0
$$
* General equation of heat transfer for fluids
$$
\rho T(\frac{\partial s}{\partial t}+\boldsymbol{v}\cdot\nabla s)=\nabla\cdot k\nabla T+(\sigma'\cdot\nabla)\cdot\boldsymbol{v}
$$
## Acoustic Approximations to the Laws of Gases
* Thermal penetration depth
$$
\delta_{k}=\sqrt{\frac{2k}{\omega\rho c_{p}}}=\sqrt{\frac{2\kappa}{\omega}}\\
k: thermal\;conductivity \\
\kappa: thermal\; diffusity
$$

* Viscous penetration depth
$$
\delta_{\nu}=\sqrt{\frac{2\mu}{\omega\rho}}=\sqrt{\frac{2\nu}{\omega}}\\
\mu: dynamic\; viscosity \\
\nu: kinematic\; viscosity
$$

1. Continuity equation
$$
i\omega\rho_{1}+\nabla\cdot(\rho_{m}\boldsymbol{v}_{1})=0 \\
i\omega\rho_{1}+\frac{d\rho_{m}}{dx}u_{1}+\rho_{m}\nabla\cdot\boldsymbol{v}_{1}=0
$$

2. Ideal-gas equation
$$
dp=\rho\Re dT+\Re Td\rho \\
p_{1}=\rho_{m}\Re T_{1}+\Re T_{m}\rho_{1}
$$

3. Momentum equation
$$
i\omega\rho_{m}u_{1}=-\frac{dp_{1}}{dx}+\mu(\frac{\partial^{2}u_{1}}{\partial y^{2}}+\frac{\partial^{2}u_{1}}{\partial z^{2}})
$$

4. Heat-transfer equation
$$
i\omega\rho_{m}c_{p}T_{1}+\rho_{m}c_{p}\frac{dT_{m}}{dx}u_{1}=i\omega p_{1}+k(\frac{\partial^{2}T_{1}}{\partial y^{2}}+\frac{\partial^{2}T_{1}}{\partial z^{2}})
$$

