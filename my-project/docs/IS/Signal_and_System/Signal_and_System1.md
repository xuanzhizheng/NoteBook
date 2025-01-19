

# 一、信号与系统的基本概念

## （一）、典型的信号

### 1. 基于信号维度的分类

一维信号：声音（仅讨论）

二维信号：图像

三维信号：视频、深度图

四维信号：VR、三维游戏中看到的信号

### 2. 连续/离散

连续信号：x（t），离散信号：x[n]

证明：把一个信号拆成奇信号和偶信号的方法唯一

$$
\left\{
	\begin{aligned}
		x(t)=x_e(t)+x_o(t) \\
		x(-t)=-x_e(t)+x_o(t) \\
	\end{aligned}
\right.
\Longrightarrow
\left\{
	\begin{aligned}
		x_e(t)=\frac{1}{2}[x(t)-x(-t)] \\
		x_o(t)=\frac{1}{2}[x(t)+x(-t) \\
	\end{aligned}
\right.
$$
### 3.  连续信号函数：

冲激函数：

$$
\delta(t)=\frac{du(t)}{dt}
$$
抽样函数

$$
S_a(t)=\frac{sint}{t} \\
$$

有：

$$
\int_{-\infty}^\infty Sa(t)dt={\pi}
$$

证1：留数定理（积分路径上有单极点的积分：分开考虑，上半平面2$\pi$i，实轴上$\pi$i）

$$
\int_{-\infty}^\infty \frac{sint}{t}dt=Im(\int_{-\infty}^\infty \frac{e^{ix}}{x}dx)=Im(\pi iRes[\frac{e^{iz}}{z};0])={\pi}
$$

证2：实质上用的Laplace变换证明
由：
$$
\mathscr{L}[f(t)]=F(p)\to\mathscr{L}[\frac{f(t)}{t}]=\int_{p}^{+\infty}F(s)ds\\
$$
得：
$$
\begin{align} 
\int_{-\infty}^{+\infty}\frac{\sin{x}}{x}dx &=2\int_{0}^{+\infty}\frac{\sin{x}}{x}dx \\ 
&=2\lim_{p \to 0}\int^{+\infty}_{p}\mathscr{L}[\sin{x}]dp \\ 
&=2\int_0^{+\infty}\frac{1}{1+p^2}dp \\
&=\pi \\ 
\end{align}\\
$$

### 4.离散信号函数

### 5. 信号的自变量变换

1. 化成标准形式

2. 前有负号翻转
3. 系数大于1，压缩；系数小于1，拉伸
4. 加号左移，减号右移

$$
x(3t+6)=>x(3(t+2))
$$


## （二）、系统
### 1. 线性系统（Linear System）

叠加性

$$
\begin{gather}
x_1(t) \rightarrow y_1(t) \\
x_2(t) \rightarrow y_2(t) \\
\Rightarrow x_1(t)+x_2(t) \rightarrow y_1(t)+y_2(t)
\end{gather}
$$

齐次性

$$
\begin{gather}
x_1(t) \rightarrow y_1(t) \\
\Rightarrow ax_1(t) \rightarrow ay_1(t)
\end{gather}
$$

零输入零输出特性 

线性系统判据：所有项均为x的一次项

条件：a可能是复数

求：一个满足齐次性不满足叠加性的系统 

一个满足齐次性不满足叠加性的系统

相同叠加推出齐次？

### 2. 时不变系统（Time-Invariant System）

$$
\begin{gather}
x(t) \rightarrow y(t) \\
\Rightarrow x(t-t_0) \rightarrow y_(t-t_0) 
\end{gather}
$$
信号先平移再变换=信号先变换再平移

输入信号平移$t_  0$则输出信号平移$t_0$

时不变：

$$
\begin{gather}
y(t)=x(t+k) \\
y(t)=e^{x(t+k)}
\end{gather}
$$

时变：
$$
\begin{gather}
y(t)=x(2t) \\
y(t)=tx(t) \\
y(t)=x(3-t)
\end{gather}
$$

判据:仅括号中有t且括号中不是t的函数

### 3. 因果系统(Causal System)

输出只决定于现在和过去的输入

非因果:
$$
\begin{gather}
y(t)=x(2t) \\
y(t)=x(\frac{1}{2}t) \\
y[n]=x[3-n]
\end{gather}
$$

判据:x括号里的数恒小于/等于y括号里的数

### 4. 无记忆系统(Memoryless System)

y(t)的值**仅仅只**依赖于x(t)的值

记忆：
$$
\begin{gather}
y(t)=x(t-1) \\
y(t)=x(2t)
\end{gather}
$$
判据:x与y中括号里的数完全一样

**无记忆系统一定是因果系统**

微分器是否为无记忆系统/因果系统不严格进行考虑

普遍认为微分器不是无记忆系统，是因果系统

### 5. 可逆系统(Invertable System)

x(t)能唯一写成y(t)的形式

积分器可逆,微分器不可逆

### 6. 稳定系统(Stable System)

$$
\begin{gather}
x(t) \rightarrow y(t) \\
\Rightarrow x(t)有界 \rightarrow y_(t)有界 \\
\end{gather}
$$
连续的微分器，积分器（叠加器）均不稳定

但**离散的微分器稳定**