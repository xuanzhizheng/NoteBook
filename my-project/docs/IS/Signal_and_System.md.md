

# 一、信号

## （一）、信号的分类

### 1、基于信号维度的分类

一维信号：声音（仅讨论）

二维信号：图像

三维信号：视频、深度图

四维信号：VR、三维游戏中看到的信号

### 2、连续/离散

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
