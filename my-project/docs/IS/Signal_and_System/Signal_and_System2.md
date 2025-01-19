# 二、LTI系统的时域分析

## （一）LTI系统定义

LTI系统：线性时不变系统（Linear Time-Invariant System）

核心：如果知道一个x(t)对应的y(t)，则知道所有x(t)对应的y(t)

## （二）离散LTI系统卷积公式

$x[n]$单位脉冲序列，$h[n]$单位脉冲响应

对于**LTI系统**，若$h[n]$相同，则输入输出相同

$$
\begin{gather}
\delta[n] \rightarrow h[n] \\
x[n] \rightarrow y[n] \\
y[n]=x[n]*h[n]
\end{gather}
$$

1. 列表法

	$y[n]$的最左边等于$x[n]$的最左边+$h[n]$的最左边

	$y[n]$的最右边等于$x[n]$的最右边+$h[n]$的最右边

	| h[n] |  1   |  1   |  2   |  -1  |      |      |      |
	| :--: | :--: | :--: | :--: | :--: | :--: | :--: | :--: |
	|  3   |  3   |  3   |  6   |  -3  |      |      |      |
	|  2   |      |  2   |  2   |  4   |  -2  |      |      |
	|  1   |      |      |  1   |  1   |  2   |  -1  |      |
	|  -1  |      |      |      |  -1  |  -1  |  -2  |  1   |
	|      |  3   |  5   |  9   |  1   |  -1  |  -3  |  1   |

要用$(N-1)^2$次加法，$N$次乘法，复杂度为$O(N)$

快速傅里叶变换 -> 复杂度降为$O(NlogN)$

2. 卷积公式
	
	左右同时LTI：
	
	$$
	\begin{gather}
	x[n]=\Sigma_{k=-\infty}^\infty x[k]\delta[n-k] \\
	\Rightarrow x[n]*h[n]=\Sigma_{k=-\infty}^\infty x[k]h[n-k]
	\end{gather}
	$$

翻转（**卷**），平移，相乘（**积**），求和
$$
x[n]*h[n]=\Sigma_{k=-\infty}^\infty x[k]h[-(k-n)]
$$
事实上同一方法，只不过交换了加法与乘法的顺序

### （三）连续LTI系统卷积公式推导

由连续到离散，$\delta(t)冲激函数$，$h(t)冲激响应$

$$
\begin{gather}
\delta(t) \mathop{=}\limits^{def} \mathop{lim}\limits_{\Delta \rightarrow0} \delta_\Delta(t)
\\
\delta(t) \rightarrow h(t)
\\
x_{\Delta}(t)=\mathop{\Sigma}\limits_{k=-\infty}^{\infty}x(k\Delta)\delta_\Delta(t-k\Delta)\times \Delta
\\
\Rightarrow y(t)=\int_{-\infty}^\infty x(t)h(t-\tau)d\tau
\end{gather}
$$

### （四）冲激函数的性质（难）

勒贝格定义中为何不能直接
$$
\int_{-\infty}^{\infty}f_1(t)dt=\int_{-\infty}^{\infty}f_2(t)dt
$$
而是
$$
\int_{-\infty}^{\infty}y(t)f_1(t)dt=\int_{-\infty}^{\infty}y(t)f_2(t)dt
$$

1. $\int_{-\infty}^{\infty}\delta(t)dt=1$
2. $\int_{-\infty}^{\infty}x(t)\delta(t)dt=x(0)，\delta(t)$**定义**
3. $x(t)\delta(t)=x(0)\delta(t)$
4. $\delta(at)=\frac{1}{|a|}\delta(t)$，**在拉伸**$\delta(t)$**时需注意**
5. $\delta(f(t))=\sum\limits_{f(t_0)=0}\frac{1}{|f^\prime(t_0)|}\delta(t-t_0)$

其中2是冲激函数的核心，表明冲激函数实质就是在积分下取函数在冲激时间下的值，1是2的特例，取常数1在冲激时间下的值

3，5由2经勒贝格积分推出，4为5的特例

可证：
$$
\mathop{lim}\limits_{\omega\rightarrow\infty}\frac{sin(\omega t)}{\pi t}=\delta (t)
$$

### （五）连续信号卷积计算

1. 公式法
2. 图像法

方波题目其实本质可以看成离散波，用列表法解决？

卷积后 横坐标为带着坐标翻转并相加？ 
