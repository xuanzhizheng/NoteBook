

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
\begin{align} \int_{-\infty}^{+\infty}\frac{\sin{x}}{x}dx &=2\int_{0}^{+\infty}\frac{\sin{x}}{x}dx\\ &=2\lim_{p \to 0}\int^{+\infty}_{p}\mathscr{L}[\sin{x}]dp\\ &=2\int_0^{+\infty}\frac{1}{1+p^2}dp\\&=\pi\\ \end{align}\\
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
