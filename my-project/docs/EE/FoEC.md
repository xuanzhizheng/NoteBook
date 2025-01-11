## 电原

### 一阶

$$
f(t)=f(\infty)+[f(0_{+})-f(\infty)]e^{-\frac{t}{\tau}}
$$

$$
\tau=RC=\frac{L}{R}
$$

## 模电



### 二极管

$$
I=I_se^\frac{V}{V_T}
$$

两边对V求导，得
$$
g_m=\frac{I_s}{V_T}e^\frac{V}{V_T}=\frac{I_D}{V_T}
$$

### 三极管

同理对三极管
$$
I_c=I_se^\frac{V_{BE}}{V_T}
$$

$$
g_m=\frac{I_C}{V_T}=\frac{i_c}{v_{be}}
$$

故
$$
r_\pi = \frac{v_{be}}{i_b} = \frac{\beta}{g_m} = \frac{V_T}{I_B}
$$
若考虑厄利现象
$$
I_c=I_se^\frac{V_{BE}}{V_T}(1+\frac{V_{CE}}{V_A})
$$
两边对$V_{CE}$求导，得
$$
g_m=\frac{I_s}{V_A}e^\frac{V}{V_T}=>ro=\frac{V_A}{I_C}
$$

### 场效应管

饱和条件
$$
V_{DS} \geq V_{GS} -V_t
$$
放大区：
$$
I_D=k_n^{\prime}\frac{W}{L}[(V_{GS} -V_t)V_{DS}-\frac{1}{2}V_{DS}^2]
$$

$$
k_n^{\prime}=\mu_nC_{ox},k_n=k_n^{\prime}\frac{W}{L}
$$

饱和区
$$
I_D=\frac{1}{2}k_n^{\prime}\frac{W}{L}(V_{GS} -V_t)^2
$$
其中
$$
I_{DSS}=\frac{1}{2}k_n^{\prime}\frac{W}{L}V_t^2
$$
故
$$
I_D=I_{DSS}(1 -\frac{V_{GS}}{V_t})^2
$$


与三极管相似（ $\lambda = \frac{1}{V_A}$ ）
$$
r_o=\frac{V_A}{I_D}
$$
小信号模型：
$$
i_d=k_n^{\prime}\frac{W}{L}(V_{GS} -V_t)v_{gs}
$$
故
$$
g_m=k_n^{\prime}\frac{W}{L}(V_{GS} -V_t)=\frac{I_D}{V_{OV}/2}
$$

常用
$$
k_n^{\prime}=\mu_nC_{ox},k_n=k_n^{\prime}\frac{W}{L},V_{OV}=V_{GS}-V_t
$$

$$
I_D=k_n[(V_{GS} -V_t)V_{DS}-\frac{1}{2}V_{DS}^2]
$$

$$
g_m=k_nV_{OV}
$$

### 频率响应

米勒定理（输入–输出，输出-输入）
$$
C_1=(1-A)C,C_2=(1-\frac{1}{A})C
$$

$$
Z_C=\frac{1}{j\omega C},Z_L=j\omega L,s=j\omega
$$


低频极点
$$
\frac{\frac{jf}{f_L}}{1+\frac{jf}{f_L}}=\frac{1}{1+\frac{f_L}{jf}}
$$
高频极点
$$
\frac{1}{1+\frac{jf}{f_H}}
$$


由：
$$
f=\frac{\omega}{2\pi}
$$


低频响应时（找频率最大，越串越大），其他电容短路
$$
f_L=f_{L1}+f_{L2}+f_{L3}+···，\omega_L=\Sigma\frac{1}{CR}
$$
高频响应时（找频率最小，越并越小），其他电容断路
$$
f_H=\frac{1}{\frac{1}{f_{H1}}+\frac{1}{f_{H2}}+\frac{1}{f_{H3}}+···},\omega_H=\frac{1}{\Sigma CR}
$$

### 反馈：

闭环增益$A_f$，开环增益$A$，反馈系数$F$，环路增益$AF$，**反馈量$1+AF$**

1. 减小放大倍数

$$
A_f=\frac{A}{1+AF}
$$

2. 提高增益稳定性

$$
\frac{dA_f}{A_f}=\frac{1}{1+AF} \frac{dA}{A}
$$

3. 拓展带宽
	$$
	\omega_{Hf}=(1+AF)\omega_H,\omega_{Lf}=\frac{1}{1+AF}\omega_L，\omega_{BWf}=(1+AF)\omega_{BW}
	$$

4. 串联增大电阻
	$$
	R_{f}=R(1+AF)
	$$
	
5. 并联减小电阻

$$
R_{f}=\frac{1}{(1+AF)}R
$$

### 自激振荡

$f_c(Crossover)$：环路增益下降到0dB的频率

可靠稳定性要求：

$$
G_m\le -10dB, \phi\ge 45\degree
$$

1. 拆环
2. 算出放大倍数A，反馈系数F
3. 算出输入电阻
4. 输入电阻=(输入电阻+ $R_s$ )*系数- $R_s$  （电压时串，电流时并）
5. 输出电阻同理


### 功放

AB类电路（双电源）：
$$
P_{L}=\frac{1}{2}\frac{V_{O}^2}{R_L},V_O=V_{CC}-U_{CES}
$$

$$
P_S=\frac{2}{\pi}\frac{V_OV_{CC}}{R_L},V_o=V_{CC}-U_{CES}
$$

$$
P_D=P_S-P_L=\frac{2}{\pi}\frac{V_OV_{CC}}{R_L}-\frac{1}{2}\frac{V_{O}^2}{R_L}
$$

$$
V_O=\frac{2}{\pi}V_{CC}，P_D=\frac{2}{\pi^2}\frac{V_{CC}^2}{R_L}
$$

