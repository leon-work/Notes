# Simple Harmonic Analysis of Regenerators

## Introduction

* Based on stacked screen friction factor and heat transfer data of Kays and Gary et al.
* It allows the incorporation of any steady state friction-factor and heat transfer correlations, for stacked screens or for any other complex regenerator geometry, into a harmonic analysis in a self-consistent manner that uses the full amplitude-dependent information in the correlations.
1. Basic geometry
    Length: $L$, Cross sectional area: $A$, Porosity $\phi$
    Total gas volume: $\phi AL​$
$$
Length: L,Cross\;sectional\;area\;A,Porosity\; \phi.\\
Hydraulic\; radiu:\;r_h=\frac{V_{gas}}{A_{gas-solid}} \\
$$

​	For square-weave screen with $m$  wires per unit length and wire diameter $d_{wire}$, DelataEC Page 199.
$$
\phi \simeq 1-\frac{\pi md_{wire}}{4} \\
r_h = d_{wire}\frac{\phi}{4(1-\phi)}
$$

2. Assumption
* An expansion to first order in the oscillatory amplitude suffices for any dynamic variable $\xi$.
$$
\xi\left(\boldsymbol{r},t\right)\simeq\xi_{m}(\boldsymbol{r})+\mathrm{Re}[\xi_{1}(\boldsymbol{r})e^{i\omega t}] 
$$
  $\boldsymbol{r}$ is the vector postion , $t$ is time,$\xi_{1}$ is a complex number, reflecting time phasing of the oscillating quantity.
## Basic functions
### Derivation Details
1. Momentum Equation: $\frac{dp_1}{dx}$
Harmonic approximation:
$$
\frac{dp_{1}}{dx}=i\omega\rho_{eff}\langle u_{1}\rangle-\Phi\langle u_{1}\rangle
$$
$\rho_{eff}$: The effective mean mass density that accounts for the tortuosity of the flow path through the screens.

$\Phi $: the effects of viscosity.

$i\omega\rho_{eff}\langle u_{1}\rangle$: Inertia contributions; $\Phi\langle u_{1}\rangle$: Dissipative contribution.

The inertial term is much smaller than the dissipative term in typical regenerators. It has no direct influence on effectiveness, and so it is generally neglected in regenerator analyses.

$\rho_m$ is lower bound on $\rho_{eff}$, because the flow passages in the regenerator cannot be less tortured than straight, parallel-sided passages. A plausible upper bound on $\rho_{eff}$ can be obtained by considering a regenerator geometry comprising alternating, equal-length open and constricted sections in series, with straight, parallel-sided passages in all sections, and with porosity 1 in the open sections and porosity $2\phi -1$in the open sections.

2. Oscillatory Temperature
Heat transfer coefficient $h​$: the ratio of heat flux per unit wetted area to temperature difference from one side of the wetted area to the other, with the gas-side temperature a heat-capacity-flux-density wighted average rather than a simple spatial average.
$$
\frac{heat\,flux}{wetted\,area}=(T_{s}-\frac{\langle\rho c_{p}uT\rangle}{\langle\rho c_{p}u\rangle})h
$$

Assumption: $h​$ depends only on the instantaneous value of the Reynolds number, not on the past history of the flow.
General equation of heat transfer:
$$
\rho c_{p}\frac{\partial T}{\partial t}-T\beta\frac{\partial p}{\partial t}+\rho c_{p}\nu\cdot\nabla T-T\beta\nu\cdot\nabla p=\nabla\cdot(K\nabla T)
$$

Ignore the distinction between the local spatial average temperature 
$$
\langle T\rangle\simeq\langle T\rangle_{u}\equiv\frac{\langle uT\rangle}{\langle u\rangle}
$$

$$
\langle T\rangle_{u,1}=\frac{T_{m}\beta_{m}}{\rho_{m}c_{p,m}}\frac{\varepsilon_{s}+(g_{c}+e^{2i\theta_{p}}g_{v})\varepsilon_{h}}{1+\varepsilon_{s}+(g_{c}+e^{2i\theta_{T}}g_{v})\varepsilon_{h}}p_{1}-\frac{1}{i\omega}\frac{dT_{m}}{dx}\frac{\varepsilon_{s}+(g_{c}-g_{v})\varepsilon_{h}}{1+\varepsilon_{s}+(g_{c}+e^{2i\theta_{T}}g_{v})\varepsilon_{h}}\langle u_{1}\rangle
$$
3. Energy Equation 
### Summary
> Initials:  $\bar{H}_{2}$ , (real) $T_m$, (complex) $p_1$, $ \langle u_{1} \rangle$
> Generate: $T_m(x $,$P_1(x)$,$\langle u_{1}(x) \rangle$

$$
\begin{align*}
\frac{dp_{1}}{dx}= & -i\omega\rho_{m}[1+\frac{(1-\phi)^{2}}{2(2\phi-1)}]\langle u_{1}\rangle-\frac{\mu_{m}}{r_{h}^{2}}[\frac{c_{1}(\phi)}{8}+\frac{c_{2}(\phi)Re_{1}}{3\pi}]\langle u_{1}\rangle\\
\frac{d\langle u_{1}\rangle}{dx}= & -\frac{i\omega\gamma_{m}}{\rho_{m}a_{m}^{2}}p_{1}+\beta_{m}\frac{dT_{m}}{dx}\langle u_{1}\rangle+i\omega\beta_{m}[\frac{T_{m}\beta_{m}}{\rho_{m}c_{p,m}}\frac{\varepsilon_{s}+(g_{c}+e^{2i\theta_{p}}g_{v})\varepsilon_{h}}{1+\varepsilon_{s}+(g_{c}+e^{2i\theta_{T}}g_{v})\varepsilon_{h}}p_{1}\\
 & -\frac{1}{i\omega}\frac{dT_{m}}{dx}\frac{\varepsilon_{s}+(g_{c}-g_{v})\varepsilon_{h}}{1+\varepsilon_{s}+(g_{c}+e^{2i\theta_{T}}g_{v})\varepsilon_{h}}\langle u_{1}\rangle]\\
\frac{dT_{m}}{dx}= & \left\{ \mathrm{Re}[(T_{m}\beta_{m}\frac{\varepsilon_{s}+(g_{c}+e^{2i\theta_{p}}g_{v})\varepsilon_{h}}{1+\varepsilon_{s}+(g_{c}+e^{2i\theta_{T}}g_{v})\varepsilon_{h}}+1-T_{m}\beta_{m})p_{1}\langle\bar{u}_{1}\rangle]-\frac{2\bar{H}_{2}}{\phi A}\right\} /\\
 & \left\{ \frac{\rho_{m}c_{p,m}}{\omega}\times\mathrm{Im}[\frac{\varepsilon_{s}+(g_{c}-g_{v})\varepsilon_{h}}{1+\varepsilon_{s}+(g_{c}+e^{2i\theta_{T}}g_{v})\varepsilon_{h}}]\langle u_{1}\rangle\langle\bar{u}_{1}\rangle+2K_{eff}\frac{1-\phi}{\phi}\right\} 
\end{align*}
$$

using 
$$
\begin{align*}
c_{1}(\phi)= & 1268-3545\phi+2544\phi^{2}\\
c_{2}(\phi)= & -2.82+10.7\phi-8.6\phi^{2}\\
b(\phi)= & 3.81-11.29\phi+9.47\phi^{2}\\
Re_{1}= & 4\lvert\langle u_{1}\rangle\rvert r_{h}\rho_{m}/\mu_{m}\\
\varepsilon_{s}= & \phi\rho_{m}c_{p,m}/(1-\phi)\rho_{s,m}c_{s,m}\\
\varepsilon_{h}= & 8ir_{h}^{2}/b(\phi)\sigma^{1/3}\delta_{\kappa}^{2}\\
\delta_{\kappa}= & 2K_{m}/\omega\rho_{m}c_{p,m}\\
\theta_{p}= & phase(\langle u_{1}\rangle)-phase(p_{1})\\
\theta_{r}= & phase(\langle u_{1}\rangle)-phase(\langle T\rangle_{u,1})\\
g_{c}= & \frac{2}{\pi}\int_{0}^{\pi/2}\frac{dz}{1+Re_{1}^{3/5}\cos^{3/5}(z)}\\
g_{v}= & -\frac{2}{\pi}\int_{0}^{\pi/2}\frac{\cos(2z)dz}{1+Re_{1}^{3/5}\cos^{3/5}(z)}
\end{align*}
$$

# One point Computation 
## **基本假设 **

* $T_m,a_m,\rho_m,\mu_m,k_m,\sigma$在计算中保持不变
```matlab
T_m = (T_hot+T_cold)/2.0;       % mean temperature
a_m = sqrt(gamma*R_gas*T_m);    % m/s, speed of sound in gas
rho_m = p_m/R_gas/T_m;          % kg/m3, gas density at Tm
% The correlations for dynamic viscosity and thermal conductivity for usual 
% working gases can be found in (DeltaEC Users Guide)
mu_m = 0.412e-6*T_m^0.68014;    % kg/(m.s), gas viscosity at Tm
k_m = 0.0025672*T_m^0.716;      % W/(m.K), gas thermal conductivity at Tm
Pr = mu_m*cp/k_m;               % Prandtl number of gas,\sigma
Zspecific = rho_m*a_m;          % specific acoustic IMPEDANCE
```

## $c_1(\phi),c_2(\phi),b(\phi)$ 保持不变

$$
\begin{align*}
c_{1}(\phi)= & 1268-3545\phi+2544\phi^{2}\\
c_{2}(\phi)= & -2.82+10.7\phi-8.6\phi^{2}\\
b(\phi)= & 3.81-11.29\phi+9.47\phi^{2}\\
\end{align*}
$$

	c1phi = 1268 - 3545 * phi + 2544 * phi^2      
	c2phi = -2.82 + 10.7 * phi - 8.6 * phi^2
	bphi = 3.81 - 11.29 * phi + 9.47 * phi^2

## $\varepsilon_{s},\varepsilon_{h}$ 温度梯度简化

```matlab
epsil_s = phi*rho_m*cp/((1-phi)*rho_s*c_s); 
epsil_h = 8.0*1i*rh^2/(bphi*Pr^(1/3)*deltakappa_m^2);
```

## $\theta_p,Re_1$均采用初值, 导致 $g_c,g_v$ 只在初值有定义

```matlab
theta_p = angle(u10) - angle(p10)
NR1 = 4.0*abs(u10)*rh*rho_m/mugas(T0)
func = @(z) 1./(1+NR1^(3/5)*(cos(z)).^(3/5));
funv = @(z) cos(2*z)./(1+NR1^(3/5)*(cos(z)).^(3/5));
gc = 2/pi * integral(func,0,pi/2);
gv = - 2/pi * integral(funv,0,pi/2);
```

##  $C_{11}\;to\;C_{33}$
$$
C_{11} = -i\omega\rho_{m}[1+\frac{(1-\phi)^{2}}{2(2\phi-1)}]-\frac{\mu_{m}}{r_{h}^{2}}[\frac{c_{1}(\phi)}{8}+\frac{c_{2}(\phi)Re_{1}}{3\pi}] \\
C_{21} = -\frac{i\omega\gamma_{m}}{\rho_{m}a_{m}^{2}} \\
C_{23} = 1-\varepsilon_{s}-(g_c-g_v)\varepsilon_{h} \\
C_{31} = \varepsilon_{s}+(g_{c}+e^{2i\theta_{T}}g_{v})\varepsilon_{h} \\
C_{22} = \frac {i\omega}{\rho_m c_p}[\varepsilon_{s}+(g_{c}+e^{2i\theta_{T}}g_{v})\varepsilon_{h}] \\
C_{32} = \frac{\rho_{m}c_{p,m}}{\omega}\times\mathrm{Im}[\varepsilon_{s}+(g_c-g_v)\varepsilon_{h}] \\
C_{33} = 2\frac{k_{se}(1-\phi)}{\phi+k_m}
$$
```matlab
C11 = -1i*omega*rho_m*(1+(1-phi)^2/(2.0*phi-1)/2.0);
C11 = C11 - mu_m/(rh^2)*(c1phi/8.0+c2phi*NR1/pi/3.0);   % U-dependent
C21 = -1i*omega*gamma/(rho_m*a_m^2);
C23 = 1 - epsil_s - (gc-gv)*epsil_h;                    % U-dependent
C31 = epsil_s + (gc + gv*exp(2*1i*theta_p))*epsil_h;    % U-dependent
C22 = C31*1i*omega/(rho_m*cp);
C32 = imag(1-C23)*rho_m*cp/omega;
C33 = 2.0*(kse*(1-phi)/phi+k_m);
```

## Code equations

* **Initial Assumptions**
$$
1+\varepsilon_{s}+(g_{c}+e^{2i\theta_{T}}g_{v})\varepsilon_{h} \approx 1 \\
T_{m}\beta_{m}\approx 1
$$
```matlab
Sodefun=@(x,PUT)[C11.*PUT(2);...
        C21.*PUT(1) + C22.*PUT(1)./PUT(3)+C23.*PUT(2)./PUT(3).*...
        ((-2.*H2/(phi.*A)+real(PUT(1)*conj(PUT(2))*C31))./(C32.*abs(PUT(2)).^2 + 		C33));...
        (-2.*H2/(phi.*A)+real(PUT(1)*conj(PUT(2))*C31))./(C32.*abs(PUT(2)).^2 + 		C33)];
xspan = [x0,x];                 % Interval of integration
PUTini = [p10 u10 T0];          % initial conditions (at x0)
```
$$
\begin{align*}
\frac{dp_{1}}{dx}= & -i\omega\rho_{m}[1+\frac{(1-\phi)^{2}}{2(2\phi-1)}]\langle u_{1}\rangle-\frac{\mu_{m}}{r_{h}^{2}}[\frac{c_{1}(\phi)}{8}+\frac{c_{2}(\phi)Re_{1}}{3\pi}]\langle u_{1}\rangle\\
\frac{d\langle u_{1}\rangle}{dx}= & -\frac{i\omega\gamma_{m}}{\rho_{m}a_{m}^{2}}p_{1}+\frac{i\omega}{\rho_{m}c_{p}}[\varepsilon_{s}+(g_{c}+e^{2i\theta_{p}}g_{v})\varepsilon_{h}]\frac{p_{1}}{T_{m}}+[1-\varepsilon_{s}-(g_{c}-g_{v})\varepsilon_{h}]\frac{\langle u_{1}\rangle}{T_{m}}\frac{dT_{m}}{dx}\\
\frac{dT_{m}}{dx}= & \{\mathrm{Re}[(\varepsilon_{s}+(g_{c}+e^{2i\theta_{p}}g_{v})\varepsilon_{h})p_{1}\langle\bar{u}_{1}\rangle]-\frac{2\bar{H}_{2}}{\phi A}\}/\\
 & \{\frac{\rho_{m}c_{p,m}}{\omega}\times\mathrm{Im}[\varepsilon_{s}+(g_{c}-g_{v})\varepsilon_{h}]\langle u_{1}\rangle\langle\bar{u}_{1}\rangle+2\frac{k_{se}(1-\phi)}{\phi+k_{m}}\}
\end{align*}
$$


