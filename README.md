# Linear-Algebra

# 向量空间

## 向量

$n$个有序的数$a_1,a_2,...,a_n$所组成的数组称为$\color{Salmon}{n\ 维向量}$，这$n$个数称为该向量的$n$个分量，第$i$个数$a_i$称为第$i$个分量。$n$维向量可写成一行，也可写成一列。分别称为$\color{Salmon}{行向量}$和$\color{Salmon}{列向量}$：
$n$维列向量：
$$\begin{pmatrix}a_1\\a_2\\\vdots\\a_n\end{pmatrix}$$
与$n$维行向量：
$$(a_1,a_2,...,a_n)\quad 或 \quad \begin{pmatrix}a_1&a_2&\cdots&a_n\end{pmatrix}$$
$n$也称为该向量的$\color{Salmon}{维数}$。

起点与终点为同一个点的向量为$\color{Salmon}{零向量}$，记做$\boldsymbol{0}$。从几何上理解，就是平面、空间中的原点。这是一个很特殊的向量，有如下性质：
* 长度：零向量的长度为0；
* 方向：零向量指向任意方向；
* 夹角：因为零向量指向任意方向，所以它与某一向量的夹角为任意角度；
* 平行与正交：因为夹角任意，所以零向量与任意向量平行、正交。

## 基本运算

#####  加法

列向量
$$\vec{a}+\vec{b}=\begin{pmatrix}a_1\\a_2\\...\\a_n\end{pmatrix}+\begin{pmatrix}b_1\\b_2\\...\\b_n\end{pmatrix}=\begin{pmatrix}a_1+b_1\\a_2+b_2\\...\\a_n+b_n\end{pmatrix}$$

行向量：
$$\vec{a}+\vec{b}=(a_1,a_2...a_n)+(b_1,b_2...b_n)=(a_1+b_1,a_2+b_2,...a_n+b_n)$$

##### 数乘

数乘就是对$\vec{u}$进行缩放：1. $|k|$为缩放比例；2. $k < 0$时，$k\boldsymbol{u}$与$\boldsymbol{u}$方向相反；3. $k\vec{u}\ // \ \vec{u}$。数乘$k$即是将每个元素都扩大为$k$倍:

$$k\vec{a}=k\begin{pmatrix}a_1\\a_2\\...\\a_n\end{pmatrix}=\begin{pmatrix}ka_1\\ka_2\\...\\ka_n\end{pmatrix},k\in\mathbb{R}$$

写成行向量：

$$k\vec{a}=k(a_1,a_2...a_n)=(ka_1,ka_2,...ka_n),k\in\mathbb{R}$$

##### 基本运算

向量加法与向量数乘被称为向量的基本运算。这些基本运算符合以下规律：

\begin{array}{c|c}
    \hline
    \quad 加法 \quad & 
    \quad\begin{aligned} 交换律 \\ 结合律 \end{aligned} \quad & 
    \quad\begin{aligned} \vec{v}+\vec{u}=\vec{u}+\vec{v} \qquad \quad \\ 
    \vec{u}+\vec{v}+\vec{w}=\vec{u}+(\vec{v}+\vec{w}) \end{aligned} \quad \\
    \hline
    \quad 数乘 \quad &
    \quad \begin{aligned} 交换律 \\ 结合律 \\ 分配律 \end{aligned} \quad & 
    \quad \begin{aligned} 
    k\cdot\vec{u}=\vec{u}\cdot k\qquad\ \ \\ 
    k\cdot m\cdot\vec{u}=k\cdot(m\cdot\vec{u})\\
    k(\vec{u}+\vec{v})=k\vec{u}+k\vec{v}\ \  \end{aligned}\quad\\
    \hline
\end{array}


## 线性相关

### 向量组

若干$\color{Salmon}{同维数}$的列向量（或行向量）$\vec{a}_1,\vec{a}_2,...\vec{a}_m$所组成的集合$A$，叫做$\color{Salmon}{向量组}$$A$，通常记作：

$$A:\vec{a}_1,\vec{a}_2,...\vec{a}_m \quad 或 \quad A=\{\vec{a}_1,\vec{a}_2,...\vec{a}_m\}$$

### 线性组合

给定向量组$A=\{\vec{a}_1,\vec{a}_2,...\vec{a}_m\}$和向量$\vec{b}$，如果存在一组实数$k_1,k_2,...k_m$，使：

$$\vec{b}=k_1\vec{a}_1+k_2\vec{a}_2+...+k_m\vec{a}_m$$

则称向量$\vec{b}$能由向量组$A$线性表示，或称向量$\vec{b}$是向量组$A$的线性组合。

对于零向量$\boldsymbol{0}$，必然可以由和它**同维数**的任意向量组$A=\{\vec{a}_1,\vec{a}_2,...\vec{a}_m\}$线性表示：

$$\boldsymbol{0}=0\vec{a}_1+0\vec{a}_2+...+0\vec{a}_m$$

给定向量组$A=\{\vec{a}_1,\vec{a}_2,...\vec{a}_m\}$，如果存在**不全为零**的实数$k_1,k_2,...k_m$，使：

$$k_1\vec{a}_1+k_2\vec{a}_2+...+k_m\vec{a}_m=\vec{0}$$

则称向量组$A$是$\color{Salmon}{线性相关}$的，否则称它为$\color{Salmon}{线性无关}$。

### 升维与降维

$A$为$n$维向量组，那么：
1. 如果$A$线性无关，则给向量组中的每个向量增加第$n+1$个分量后，该向量组依旧线性无关，或者简单叙述为：线性无关的向量组，升维后仍线性无关；
2. 如果$A$线性相关，则去掉向量组中的每个向量的第$n$个分量后，该向量组依旧线性相关，或者简单叙述为：线性相关的向量组，降维后仍线性相关。

## 向量空间与张成空间

### 向量空间

* $V$为一非空向量组，且$V$对于向量的加法及数乘两种运算封闭（数乘和加减的结果依然在$V$中），那么就称$V$为$\color{Salmon}{向量空间}$。  
封闭的具体定义为:  
若$\vec{a}\in V,\vec{b}\in V$，则$\vec{a}+\vec{b} \in V$；  
若$\vec{a}\in V, k\in \mathbb{R}$，则$k\vec{a} \in V$。  


* 所有$n$维向量构成的集合是一个向量空间$\color{Salmon}{\mathbb{R^n}}$：
$\mathbb{R^n}=\{(x_1,x_2,...,x_n)|n\in \mathbb{N},x_n\in\mathbb{R}\}, n\ge 1$

* **向量空间必含有零向量**。  
<br/>

##### 向量空间的子空间
向量空间并不一定是$\mathbb{R^n}$，也可以是它们的子集。比如$\mathbb{R^3}$中的一个点，一根直线，或者一个面，也可以是向量空间（必须经过原点）。它们都是$\mathbb{R^3}$的子集，也称为$\mathbb{R^3}$的一个子空间，记作：$V \subset \mathbb{R^3}$

### 张成空间

某向量组$A=\{\vec{v}_1,\vec{v}_2,...,\vec{v}_p\}$，其所有线性组合构成的集合为向量空间，也称为向量组$A$的$\color{Salmon}{张成空间}$，记为$span(\vec{v}_1,\vec{v}_2,...,\vec{v}_p)$，即：

$$ V=span(\vec{v}_1,\vec{v}_2,...,\vec{v}_p)=\{k_1\vec{v}_1+k_2\vec{v}_2+...+k_p\vec{v}_p, k_{1,2,...,p}\in\mathbb{R}\} $$

也称$span(\vec{v}_1,\vec{v}_2,...,\vec{v}_p)$为向量组$A$所$\color{Salmon}{张成}$。

##### 等价向量组
* 设有两个向量组$A=\{\vec{a}_1,\vec{a}_2,...,\vec{a}_m\}$及$B=\{\vec{b}_1,\vec{b}_2,...,\vec{b}_m\}$，若$B$组中的每个向量都能由向量组$A$线性表示，则称向量组$B$能由向量组$A$线性表示。
* 若向量组$A$与向量组$B$能相互线性表示，则称这两个向量组等价，也可以说$A$和$B$是等价向量组。
* 等价向量组的张成空间是相等的：$ A和B等价 \iff span(A)=span(B) $

##### 最大无关组
如果在向量组$A$中能选出$r$个向量$\vec{a}_1,\vec{a}_2,...,\vec{a}_r$满足：
* 向量组$A_0=\{\vec{a}_1,\vec{a}_2,...,\vec{a}_r\}$线性无关
* 向量组$A$中任意$r+1$个向量（若存在）都线性相关，那么称向量组$A_0$是向量组$A$的一个**最大线性无关组**，简称**最大无关组**

##### 向量组的秩
虽然**向量组的最大无关组并不唯一**，但是最大无关组包含向量的数目是相同的，此不变的数目就称为秩。  
假设向量组$A$的最大无关组为：

$$A_0=\{a_1,a_2,\cdots,a_r\}$$

那么$A_0$的向量个数$r$称为向量组$A$的$\color{Salmon}{秩}$，记做$\color{Salmon}{rank(A)}$，或$r(A)$。


## 向量空间的基/坐标/维度

##### 基
$V$为向量空间，如果其中的某向量组$Basis \subset V$：

$$Basis=\{\vec{e}_1,\vec{e}_2,...\vec{e}_r\}$$

是$V$的最大无关组，那么向量组$A$被称为向量空间$V$的一个$\color{Salmon}{基}$。  
  
##### 坐标
有了基就可以对向量空间中的向量进行定位(给出坐标)：
在向量空间$V$中取一个基$\vec{e}_1,\vec{e}_2,...\vec{e}_r$，那么$V$中某向量$\vec{x}$可唯一地表示为：

$$\vec{x}=k_1\vec{e}_1+k_2\vec{e}_2+\cdots+k_r\vec{e}_r$$

其中，$(k_1,k_2,...,k_r)$称为向量$\vec{x}$在该基中的$\color{Salmon}{坐标}$。

##### 维度
假设向量空间$V$的基为$\{e_1,e_2,\cdots,e_r\}$，则该基的秩$r$称为该向量空间的$\color{Salmon}{维度}$，或者称$V$为$r$维向量空间。

## 向量的点积

##### 2维
$$\vec{a}\cdot\vec{b}=(a_1,a_2)\cdot({b_1},{b_2})=a_1b_1+a_2b_2$$

那么向量空间$\mathbb{R}^2$中的长度和角度的计算就可以通过点积来完成（向量的坐标必须在自然基下）：

* 长度
$||\vec{a}||=\sqrt{a_1^2+a_2^2}=\sqrt{a_1a_1+a_2a_2}=\sqrt{\vec{a}\cdot\vec{a}}$

* 夹角
$cos\theta=\displaystyle\frac{a_1b_1+a_2b_2}{||\vec{a}||||\vec{b}||}=\displaystyle\frac{\vec{a}\cdot\vec{b}}{||\vec{a}||||\vec{b}||},\quad 0\le\theta\le\pi$


##### n维
向量$\vec{x}=\begin{pmatrix}x_1 \\ \vdots \\ x_n \end{pmatrix}$和 $\vec{y}=\begin{pmatrix}y_1 \\ \vdots \\ y_n\end{pmatrix}$的点积(dot product)，或称内积(inner product)，定义为：

$$\vec{x}\cdot\vec{y}=x_1y_1+\cdots+x_ny_n=\displaystyle\sum_{i=1}^{n}x_iy_i$$

向量的坐标必须在自然基下：
* 长度
$||\vec{a}||=\sqrt{\vec{a}\cdot\vec{a}}$。 $\vec{a}与\vec{b}$的欧几里得距离为$||\vec{a}-\vec{b}||=\sqrt{(\vec{a}-\vec{b}) \cdot (\vec{a}-\vec{b})}$
* 夹角
$cos\theta=\displaystyle\frac{\vec{a}\cdot\vec{b}}{||\vec{a}||||\vec{b}||},\quad \vec{a},\vec{b}\ne\boldsymbol{0}$。 $\vec{a} \cdot \vec{b}=0$表示二者正交（相互独立）。


##### 运算法则
\begin{array}{c|c}
    \hline
    \quad 交换律\quad & \quad \vec{a}\cdot\vec{b}=\vec{b}\cdot\vec{a} \quad\\
    \quad 数乘结合律\quad & \quad (k\vec{a})\cdot\vec{b}=k(\vec{b}\cdot\vec{a}) \quad\\
    \quad 分配律\quad & \quad (\vec{a}+\vec{b})\cdot\vec{c}=\vec{a}\cdot\vec{c}+\vec{b}\cdot\vec{c} \quad\\
    \hline
\end{array}

另：$(\vec{a}\cdot\vec{b})\vec{c}\neq\vec{a}(\vec{b}\cdot\vec{c})$


# 矩阵

## 起源和定义

* 英国数学家阿瑟·凯莱（1821－1895）在1858年的《矩阵理论纪要》的论文中提出，对于线性方程组：
$$
\begin{cases}\ \ 
x+2y=3\\
3x+4y=5
\end{cases}
$$
未知数的名字$x$、$y$根本不重要，所以可把未知数的系数提出来，用一种称为$\color{Salmon}{矩阵}$的紧凑阵列来表示，该阵列称为$\color{Salmon}{系数矩阵}$：
$$
\begin{pmatrix}
    1&2\\
    3&4
\end{pmatrix}
$$
如果把等号右边的数字一起提出来，那么称为$\color{Salmon}{增广矩阵}$，有的书本也会把右边的数字用竖线隔开，本课程会根据展示的需要混用这两种符号：
$$
\begin{pmatrix}
    1&2&3\\
    3&4&5
\end{pmatrix}
,\quad 
\left(
\begin{array}{c:c}
\begin{matrix}
1&2\\
3&4\\
\end{matrix}&
\begin{matrix}
3\\
5
\end{matrix}
\end{array}
\right )
$$
<br/>

* 由$m\times n$个数$a_{ij}(i=1,2,...m;j=1,2...n)$排成的$m$行$n$列的数表称为$m$行$n$列$\color{Salmon}{矩阵}$，简称$m\times n$矩阵。为表示这些数字是一个整体，总是加一个括弧，下面就表示了矩阵$A$：
$$
A=\underbrace
{\begin{pmatrix}
    a_{11} & a_{12} & \dots &a_{1n} \\
    a_{21}&a_{22}& \dots &a_{2n} \\
    \dots & \dots & & \dots \\
    a_{m1}&a_{m2}&...&a_{mn}
    \end{pmatrix}}
_{\large n列}\left.\begin{aligned} \\ \\ \\ \\ \end{aligned}\right\}m行 
$$
可以用$a_{ij}$或$a_{i,j}$来表示该矩阵$A$的第$i$行$j$列的数字。为了表示矩阵的行数和列数，$m\times n$矩阵$A$也记作$A_{m\times n}$。
<br/>

* 元素都是零的矩阵称为**零矩阵**，记做$O$。比如下面是两个零矩阵：$$\begin{pmatrix}0&0&0\\0&0&0\end{pmatrix},\quad\begin{pmatrix}0&0\\0&0\\0&0\end{pmatrix}$$

## 线性方程组与矩阵乘法

* 矩阵乘法的**最初定义**来源于方便进行方程组的消元。比如对于以下两个矩阵  
<br/>
$$
\begin{pmatrix}
1 & 0\\
-3 & 1
\end{pmatrix}
\begin{pmatrix}
1 & 2 & 3\\
3 & 4 & 5
\end{pmatrix}
$$
<br/>
做乘法。
第一各矩阵的第一行$\begin{pmatrix}1 & 0\end{pmatrix}$的代表的意思是：第一元素（$1$）数乘第二个矩阵的第一行$\begin{pmatrix}1 & 2 & 3\end{pmatrix}$，再加上这第二个元素（$0$）乘以第二个矩阵的第二行$\begin{pmatrix}3 & 4 & 5\end{pmatrix}$，其结果放入结果矩阵的第一行中。同理，第一个矩阵的第二行$\begin{pmatrix}-3 & 1\end{pmatrix}$的两个元素分别与第二个矩阵的两行分别做数乘再相加，其结果放入结果矩阵的第二行，得到最终的结果。（矩阵乘法的最初定义就是后文提到的矩阵乘法的行观点）。如下视频所示：
<center>
<video controls src="http://matongxue.oss-cn-hangzhou.aliyuncs.com/attch/matex/1386/20200620141418347/1.mp4" width ="270" height=180>animation</video>
</center>
<br/>

* 利用以上定义的矩阵乘法，则可以求解线性方程组，如：
$$
\begin{cases}
    \ \ x+2y=3\\
    3x+4y=5
\end{cases}
$$
<br/>
的解题过程就可以完全用矩阵以及矩阵乘法来表示了。将线性方程组对应的增广矩阵写出，并根据所需的Gauss消元过程列出左乘的矩阵：<br/>
<br/>
$$
\begin{aligned}
    \begin{pmatrix}1&2&3\\3&4&5\end{pmatrix}
    &\xrightarrow{\quad r_2'=-3r_1+r_2\quad}
    \begin{pmatrix}1&0\\-3&1\end{pmatrix}\begin{pmatrix}1&2&3\\3&4&5\end{pmatrix}=\begin{pmatrix}1&2&3\\0&-2&-4\end{pmatrix}\\
    \qquad\\
    &\qquad\xrightarrow{\quad r_2'=\frac{r_2}{-2}\quad}
    \begin{pmatrix}1&0\\0&-\frac{1}{2}\end{pmatrix}
    \begin{pmatrix}1&2&3\\0&-2&-4\end{pmatrix}=
    \begin{pmatrix}1&2&3\\0&1&2\end{pmatrix}\\
    \qquad\\
    &\qquad\xrightarrow{\quad r_1'=r_1-2r_2\quad}
    \begin{pmatrix}1&-2\\0&1\end{pmatrix}
    \begin{pmatrix}1&2&3\\0&1&2\end{pmatrix}=
    \begin{pmatrix}1&0&-1\\0&1&2\end{pmatrix}
\end{aligned}
$$
<br/>
上面的过程可以串在一起：<br/>
<br/>
$$
\underbrace{\begin{pmatrix}1&-2\\0&1\end{pmatrix}\begin{pmatrix}1&0\\0&-\frac{1}{2}\end{pmatrix}\begin{pmatrix}1&0\\-3&1\end{pmatrix}}_{\large 注意顺序}\begin{pmatrix}1&2&3\\3&4&5\end{pmatrix}=\begin{pmatrix}1&0&-1\\0&1&2\end{pmatrix}
$$
<br/>
每个按顺序想成的矩阵都对应于一次Gauss消元的过程。根据矩阵乘法的规则，还能把前面这一串结合起来：<br/>
<br/>
$$
\begin{pmatrix}1&-2\\0&1\end{pmatrix}\begin{pmatrix}1&0\\0&-\frac{1}{2}\end{pmatrix}\begin{pmatrix}1&0\\-3&1\end{pmatrix}=\begin{pmatrix}-2&1\\1.5&-\frac{1}{2}\end{pmatrix}
$$
<br/>

##### 对角矩阵
对角线以外的元素都是0，这种**n阶方阵**称为$\color{Salmon}{对角矩阵}$，记作：

$$\Lambda_{n}=\begin{pmatrix}\lambda_1&0&...&0\\0&\lambda_2&...&0\\...&...&&...\\
0&0&...&\lambda_n\end{pmatrix}=diag(\lambda_1,\lambda_2,...,\lambda_n)$$

对角矩阵乘法：

$$\begin{pmatrix}a_{1}&&&\\&a_{2}&&\\&&\ddots &\\&&&a_{n}
\end{pmatrix}\begin{pmatrix}b_{1}&&&\\&b_{2}&&\\&&\ddots 
&\\&&&b_{n}\end{pmatrix}=\begin{pmatrix}a_{1}b_{1}&&&\\&a_{2}b_{2}&&\\&&\ddots &\\&&&a_{n}b_{n}\end{pmatrix}$$

##### 单位矩阵
如果对角阵的对角线上的元素全为1，那么该对角阵称为$\color{Salmon}{n阶单位矩阵}$（Identity matrix），或者简称为$\color{Salmon}{单位阵}$。

$$I_n=\begin{pmatrix}1&0&...&0\\0&1&...&0\\...&...&&...\\
0&0&...&1\end{pmatrix}$$

单位阵乘上任何矩阵$A$的结果还是$A$。

## 矩阵运算



##### 加法
两个矩阵的行数相等、列数也相等时，就称它们是$\color{salmon}{同型矩阵}$。如果$A=(a_{ij})$与$B=(b_{ij})$是同型矩阵，并且他们的对应元素都相等，则矩阵$A$与矩阵$B$相等，记做：$A=B$。正如同维向量才能相加一样，同型矩阵才可以相加。  

设有两个$m\times n$矩阵$A=(a_{ij})$和$B=(b_{ij})$，那么矩阵$A$和$B$的和记做$A+B$，规定为：

$$
A+B = \begin{pmatrix}
a_{11}+b_{11} & a_{12}+b_{12} & \dots & a_{1n}+b_{1n} \\
a_{21}+b_{21} & a_{22}+b_{22} & \dots & a_{2n}+b_{2n} \\
\dots & \dots &  & \dots \\
a_{m1}+b_{m1} & a_{m2}+b_{m2} & \dots & a_{mn}+b_{mn}
\end{pmatrix}
$$

矩阵加法的规律：

$$
\begin{array}{c|c}
    \hline
    \quad 交换律 \quad & \quad A+B=B+A \quad \\
    \quad 结合律 \quad & \quad (A+B)+C=A+(B+C)\quad\\
    \hline
\end{array}
$$

##### 数乘与减法
数$k$与矩阵$A$的乘积记作：$kA$或$Ak$。规定为：

$$
kA=Ak=
\begin{pmatrix}
    ka_{11} & ka_{12} & \dots & ka_{1n}\\
    ka_{21} & ka_{22} & \dots & ka_{2n}\\
    \dots & \dots &  & \dots\\
    ka_{m1} & ka_{m2} & \dots & ka_{mn}
\end{pmatrix}
$$

$\color{Salmon}{负矩阵}$和减法:
$-A$称为矩阵$A$的负矩阵，根据数乘规则有$-A=(-a_{ij})$，那么：$A+(-A)=O$。通过矩阵数乘，可以得到矩阵$-B$，也称为矩阵$B$的负矩阵：$-B=-1\cdot B$。接着就可以定义出矩阵的减法：$A-B=A+(-B)$。

矩阵数乘满足以下规律（设$A$、$B$为同型矩阵，$\lambda$、$\mu$为数）：

$$
\begin{array}{c|c}
    \hline
    \quad 交换律\quad & \quad (\lambda\mu) A=\lambda(\mu A)\quad\\
    \hline
    \quad 分配律\quad & \quad 
        \begin{aligned}
            (\lambda+\mu) A=\lambda A+\mu A\\
            \lambda(A+B)=\lambda A+\lambda B\end{aligned}\quad\\
    \hline
\end{array}
$$

### 矩阵乘法
矩阵$AB$相乘，是需要满足一定**合法性**的：
* $m\times n$的矩阵只能和$n\times p$矩阵相乘
* 相乘后的矩阵大小为$m\times p$

其原因就是来源于前面所述的矩阵乘法的原始定义。最初是为了简化线性方程组的消元过程。第一矩阵$A_{m\times n}$的每一行都有$n$个元素，每一个元素都意味着第二个矩阵$B_{n\times p}$中每一行的数乘系数，最后把计算结果放入结果矩阵中的对应行，因此结果矩阵的行数与$A$矩阵的行数相同，而结果矩阵的列数与$B$矩阵的列数相同。

##### 行观点
$$
\vec{x}=
\begin{pmatrix}
    x_1 & x_2 & \cdots & x_m
\end{pmatrix},\quad 
A=
\begin{pmatrix}
    a_{11} & a_{12} & \cdots & a_{1n}\\
    a_{21} & a_{22} & \cdots & a_{2n}\\
    \vdots & \quad & \quad & \vdots\\
    a_{m1} & a_{m2} & \cdots & a_{mn}
\end{pmatrix}
$$

此时若计算$\vec{x}A$，很适合用行观点来看待矩阵乘法，把结果看作A矩阵的行向量的**线性组合**：

$$
\begin{align}
\vec{x}A 
        &= 
            \begin{pmatrix}
                \color{blue}{x_1} & \color{blue}{x_2} & \cdots & \color{blue}{x_m}
            \end{pmatrix}
            \begin{pmatrix}
                a_{11}&a_{12}&\cdots&a_{1n}\\
                a_{21}&a_{22}&\cdots&a_{2n}\\
                \vdots&\quad&\quad&\vdots\\
                a_{m1}&a_{m2}&\cdots&a_{mn}
            \end{pmatrix}\\
        &= 
            \color{blue}{x_1}\begin{pmatrix}a_{11}&a_{12}&\cdots&a_{1n}\end{pmatrix}
            +\color{blue}{x_2}\begin{pmatrix}a_{21}&a_{22}&\cdots&a_{2n}\end{pmatrix}
            +\cdots+\color{blue}{x_m}\begin{pmatrix}a_{m1}&a_{m2}&\cdots&a_{mn}\end{pmatrix}      
\end{align}
$$

此时，$A$在行向量$\vec{x}$的右边，所以可说$A\ \color{Salmon}{右乘}\ \vec{x}$。

##### 列观点
$$
A=\begin{pmatrix}
    a_{11}&a_{12}&\cdots&a_{1n}\\
    a_{21}&a_{22}&\cdots&a_{2n}\\
    \vdots&\quad&\quad&\vdots\\
    a_{m1}&a_{m2}&\cdots&a_{mn}
\end{pmatrix},\quad 
\vec{x}=\begin{pmatrix}
    x_1\\
    x_2\\
    \vdots\\
    x_n
\end{pmatrix}
$$

此时若计算$A\vec{x}$，很适合用列观点来看待矩阵乘法，把结果看作$A$矩阵的列向量的线性组合：

$$
\begin{align}
    A\vec{x} 
            &=
                \begin{pmatrix}a_{11}&a_{12}&\cdots&a_{1n}\\
                   a_{21}&a_{22}&\cdots&a_{2n}\\
                   \vdots&\quad&\quad&\vdots\\
                   a_{m1}&a_{m2}&\cdots&a_{mn}
                \end{pmatrix}
                \begin{pmatrix}
                    \color{blue}{x_1}\\
                    \color{blue}{x_2}\\
                    \vdots\\
                    \color{blue}{x_n}
                \end{pmatrix}\\
            &=
                \color{blue}{x_1}
                \begin{pmatrix}
                    a_{11}\\
                    a_{21}\\
                    \vdots\\
                    a_{m1}
                \end{pmatrix}
                +\color{blue}{x_2}
                \begin{pmatrix}
                    a_{12}\\
                    a_{22}\\
                    \vdots\\
                    a_{m2}
                \end{pmatrix}
                +\cdots+
                \color{blue}{x_n}
                \begin{pmatrix}
                    a_{1n}\\
                    a_{2n}\\
                    \vdots
                    \\a_{mn}
                \end{pmatrix}
\end{align}
$$

此时，$A$在列向量$\vec{x}$的左边，所以可说$A\ \color{Salmon}{左乘}\ \vec{x}$。

##### 点积观点（矩阵乘法标准定义）
设$A=(a_{ij})$是一个$m\times s$矩阵，$B=(b_{ij})$是一个$s\times n$矩阵，那么规定矩阵$A$与矩阵$B$的乘积是一个$m\times n$矩阵$C=(c_{ij})$，其中：

$$
c_{ij}=\vec{a}_{i*}\cdot\vec{b}_{*j},\quad (i=1,\cdots,m;j=1,\cdots,n)
$$

并把乘积记作：$C=AB$

##### 矩阵乘法法则
$$
\begin{array}{c|c}
    \hline
    \quad 交换律\quad&\quad 不一定满足\quad\\
    \quad 数乘交换律\quad&\quad \lambda(AB)=(\lambda A)B=A(\lambda B)（其中\lambda是数）\quad\\
    \quad 结合律\quad&\quad (AB)C=A(BC)\quad\\
    \quad 分配律\quad&\quad A(B+C)=AB+AC\quad\\
    \hline
\end{array}
$$

### 矩阵转置
把矩阵$A$的行换成同序数的列，该操作称为矩阵的转置运算。转置运算后可以得到$A^\mathrm{T}$：

$$A=(a_{ij}),\quad A^\mathrm{T}=(a_{ji})$$

最开始，在1.1节向量的数学定义中提到，其实行向量和列向量是没有区别的，只是书写习惯问题 。但是学习了矩阵乘法合法性之后，就应该明白在矩阵乘法中，行向量和列向量是有区别的。在学习转置运算之后，用向量$\vec{x}$来表示列向量，它的转置$\vec{x}^\mathrm{T}$来表示行向量：

$$
\vec{x}=\begin{pmatrix}a_1\\a_2\\\vdots\\a_n\end{pmatrix},\quad\vec{x}^\mathrm{T}=(a_1,a_2,...,a_n)
$$


##### 转置运算性质：

$$
\begin{array}{c}
    \hline
    \quad (A^\mathrm{T})^\mathrm{T}=A \quad\\
    \quad (AB)^\mathrm{T}=B^\mathrm{T}A^\mathrm{T} \quad\\
    \quad (A^\mathrm{T})^n=(A^n)^\mathrm{T}  \quad\\
    \quad (A+B)^\mathrm{T}=A^\mathrm{T}+B^\mathrm{T} \quad\\
    \hline
\end{array}
$$

##### 对称矩阵与反对称矩阵：

若 $A^T=A$，则$A$为对称矩阵。如：

$$
\begin{pmatrix}
1 & 2 & 3\\
2 & 4 & -5\\
3 & -5 & 6\end{pmatrix}^\mathrm{T}
=
\begin{pmatrix}
1 & 2 & 3\\
2 & 4 & -5\\
3 & -5 & 6\end{pmatrix}
$$

若 $A^T=-A$，则$A$为反对称矩阵。如：

$$
\begin{pmatrix}
0 & 2 & -1 \\
-2 & 0 & -4 \\
1 & 4 & 0\end{pmatrix}^\mathrm{T}
=
-\begin{pmatrix}
0 & 2 & -1 \\
-2 & 0 & -4 \\
1 & 4 & 0\end{pmatrix}
$$


## 矩阵函数与线性函数

### 矩阵函数

**函数**是数学的核心概念，其概念为：假设有两不为空集的集合$X$、$Y$，$函数$指的是$X$、$Y$之间的一种对应关系，这种对应关系要满足两个条件：
1. $X$中的**所有元素**都有$Y$中的元素与之对应;
2. $X$中的元素只能有**唯一**的Y中的元素与之对应。

可以用**函数图像**表示函数：
1. 映射图，如果集合内元素比较少，那么可以用映射图来表示两个集合间的对应关系；
2. 函数曲线，集合内元素无限的时候，比如正弦函数$\sin(x)$，适合用函数曲线来表示。函数曲线本质上还是代表了$x$轴上的数与$y$轴上的数的一种对应关系；
3. 输入输出图，作函数曲线有困难，就可以用输入输出图。比如，对于抽象函数$f(x)=y$而言，输入为$x$，输出为$y$。

而矩阵乘法$A\vec{x}=\vec{y}$实际上就是一个函数，也称为$\color{Salmon}{矩阵函数}$。可以用输入输出图来表示,矩阵函数的输入为$\vec{x}$，输出为$\vec{y}$。为了突出这一点，有时候又将矩阵乘法写成函数的形式，这两种形式是等价的：
$$
\underbrace{A\vec{x}=\vec{y}}_{\large 矩阵乘法的形式}
\iff 
\underbrace{A(\vec{x})=\vec{y}}_{\large 矩阵函数的形式}
$$

### 线性函数

满足下面两个条件的函数就称为$\color{Salmon}{线性函数}$（一般用$\mathcal{L}$来表示线性函数，它是英文线性，Linear，的首字母）：
* 齐次性：$\mathcal{L}(a\vec{x})=a\mathcal{L}(\vec{x})$
* 可加性：$\mathcal{L}(x+y)=\mathcal{L}(x)+\mathcal{L}(y)$

**定理**：矩阵函数$A\vec{x}=\vec{y}$满足：
* 齐次性：$A(m\vec{x})=m(A\vec{x})$
* 可加性：$A(\vec{x}+\vec{y})=A(\vec{x})+A(\vec{y})$
所以$\color{Salmon}{矩阵函数是线性函数}$。


### 列向量函数矩阵与行向量函数矩阵

* 矩阵函数$A\vec{x}=\vec{y}$，它的输入、输出都是列向量，所以也称为$\color{Salmon}{列向量矩阵函数}$。
* 矩阵函数$\vec{x}^\mathrm{T}A=\vec{y}^\mathrm{T}$，它的输入、输出都是行向量，所以也称为$\color{Salmon}{行向量矩阵函数}$。

每一个列向量矩阵函数都有对应的行向量矩阵函数。对列向量矩阵函数$A\vec{x}=\vec{y}$进行转置运算，就可以得到对应的行向量矩阵函数：
$$
A\vec{x}=\vec{y}\implies (A\vec{x})^\mathrm{T}=\vec{y}^\mathrm{T}\implies\vec{x}^\mathrm{T}A^\mathrm{T}=\vec{y}^\mathrm{T}
$$

# 线性变换与基变换

3Blue1Brown关于线性与基变换的视频：  
线性变换：https://www.bilibili.com/video/BV1ns41167b9/  
基变换：https://www.bilibili.com/video/BV1Ls411b7r2/

## 线性变换


根据3Blue1Brown的解释，在向量空间中的一个向量$\vec{v}$（起点为原点）可以通过旋转变换到空间中的另一个坐标上。当变换前后，所有的线都是直线，同时原点保持不变时，此时的变换可以称为**线性变换**。换个角度说，线性变换要保持空间中网格线**平行且等距**分布。  
<br/>
<img src="./Figure/3blue1brown-lineartransformation-1.png" style="zoom:12%" />

若考虑一个向量$\vec{v}$:

$$\vec{v}=-1\hat{i}+2\hat{j}$$

此处暗含了$\vec{v}$在自然基下坐标为$\begin{bmatrix} -1 & 2\end{bmatrix}^\mathrm{T}$。在经过一次线性变换$A$后，变换后的向量$\vec{v}$可以用变换后的$\hat{i}$和$\hat{j}$同样的线性组合，既：

$$
transformed\,\vec{v}=-1(transformed \,\hat{i})+2(transformed\,\hat{j})
$$

因此可以看出，在变换前后，线性组合值（或坐标值）都是$\begin{bmatrix} 1 & -2\end{bmatrix}^\mathrm{T}$，只是对应的基底不同，所以线性变换本质上是改变了向量空间的基。若经过线性变换$P$后
$$
\hat{i} \stackrel{A}{\longrightarrow} transformed \,\hat{i} =
\begin{bmatrix} 1 \\ -2 \end{bmatrix}
,\quad
\hat{j} \stackrel{A}{\longrightarrow} transformed \,\hat{j} =
\begin{bmatrix} 3 \\ 0 \end{bmatrix}
$$

因此：

$$
\begin{align}
    transformed\,\vec{v} &= -1(transformed \,\hat{i})+2(transformed\,\hat{j}) \\
    &= -1\left[\begin{matrix}1 \\ -2\end{matrix}\right] + 2\left[\begin{matrix}3 \\ 0\end{matrix}\right] \\
    &=  \left[\begin{matrix}5 \\ 2\end{matrix}\right] 
\end{align}
$$

将变换后的基用变换前的基做替代，最后得到的就是变换后的向量在变换前的基下的坐标。另外，上式：

$$
1\begin{bmatrix}1 \\ -2\end{bmatrix} + 2\begin{bmatrix}3 \\ 0\end{bmatrix} 
$$

可以依据矩阵乘法的列观点重新写为：

$$
\begin{bmatrix}5 \\ 2\end{bmatrix}=
\begin{bmatrix} 1 & 3 \\ -2 & 0 \end{bmatrix}
\begin{bmatrix} -1 \\ 2\end{bmatrix}
$$

$$
{(transformed \, \vec{v})}_{e} = A(\vec{v})_{e}
$$

$A$的每一列都代表了自然基变换后的落点。

<table>
<td> 
<img src="./Figure/3blue1brown-lineartransformation-2.png" width="350" hight=“180”/> <br>
</td> 
<td> 
<img src="./Figure/3blue1brown-lineartransformation-3.png" width="350" hight=“180”/> <br>
</td> 
</table>

综上所述，站在向量旋转的角度上，向量空间的基始终是自然基，始终看重一个向量$v$经过变换后仍然在自然基下的线性组合（坐标），而非在变换后的基下的线性组合（坐标）。因为在向量空间线性变换前后，变换前后的$v$相对于变换前后的基向量是不变的，因为整体的旋转保持了相对位置不变。

若线性变换矩阵是**列相关**的，那么变换后整个自然基张成的空间都会挤压进一条线（或一个点）中。
<br/>
<img src="./Figure/3blue1brown-lineartransformation-4.png" width="350" hight=“180”/> <br>


##### 旋转矩阵

常用两个旋转矩阵是基于自然基的：
$$
A=\begin{bmatrix}\cos\theta&-\sin\theta \\ \sin\theta&\cos\theta\end{bmatrix}
$$

如前所述，线性变换$A=\begin{bmatrix}{\hat{i}^{'}}, \hat{j}^{'} \end{bmatrix}$，其中$\hat{i}^{'}=\begin{bmatrix}\cos\theta \\ \sin\theta\end{bmatrix}$，$\hat{j}^{'}=\begin{bmatrix}-\sin\theta \\ \cos\theta\end{bmatrix}$，这表示自然基的$\hat{i}=\begin{bmatrix}1\\0\end{bmatrix}$旋转到$\begin{bmatrix}\cos\theta \\ \sin\theta\end{bmatrix}$，$\hat{j}=\begin{bmatrix}0\\1\end{bmatrix}$旋转到$\begin{bmatrix}-\sin\theta \\ \cos\theta\end{bmatrix}$，即自然基整体逆时针旋转了$\theta$。对于列向量矩阵函数$A\vec{x}=\vec{y}$而言，输入向量$\vec{x}$只需要旋转$\theta$角，就可以得到它的输出向量$\vec{y}$，所以也称为列向量的旋转矩阵。

##### 单位矩阵和镜像矩阵

* **单位矩阵**表示坐标系没有变化：
$$
A=\begin{bmatrix}1&0\\0&1\end{bmatrix}
$$

* **镜像矩阵**表示坐标系翻转：
$$
A=\begin{bmatrix}0&1\\1&0\end{bmatrix}
$$

##### 伸缩矩阵与剪切矩阵

* **伸缩矩阵**, $i$方向不变，$j$方向伸缩$k$倍：
$$
A=\begin{bmatrix}1&0\\0&k\end{bmatrix}
$$

<center>
    <video controls src="./Video/extension-matrix.mp4" width="350" hight=“180”/> <br>
</center>



* **剪切矩阵**：
$$
A=\begin{bmatrix}1&k\\0&1\end{bmatrix}
$$

<center>
<video controls src="./Video/shear-matrix.mp4" width ="400" height=200> animation</video>
</center>

**注意以上变换都是针对列向量矩阵，若涉及行向量矩阵，$A$应当为$A^T$**, $\vec{x}^{T}A^T=\vec{y}^T$

## 基变换

线性变换与基变换在数学描述上是等价的。但是二者的解释视角是不同的：
* 线性变换是指，在默认的自然基$e$下，一个向量$\vec{v}_1$通过线性变换$P$变为向量$\vec{v}_2$，这两个向量都用自然基的线性组合来描述：$(\vec{v}_2)_e = P(\vec{v}_1)_e$；
* 基变换是指，当另一个坐标$her$系说向量$\vec{v}$的坐标是$\begin{bmatrix}x_1\\x_2\end{bmatrix}_{her}$时，在当前的坐标系$me$下对应的坐标$\begin{bmatrix} X_1 \\ X_2 \end{bmatrix}_{me}$应该是多少？:

##### 基变换

$me$坐标系的基是自然基 $\{ \boldsymbol{e}_1 ,\, \boldsymbol{e}_2 \}_{me}$:

$$
\boldsymbol{e}_1=\begin{bmatrix}1\\0\end{bmatrix} ,\, \boldsymbol{e}_2=\begin{bmatrix}0\\1\end{bmatrix}
$$

$her$坐标系的基是：$\{\boldsymbol{e'}_1 ,\, \boldsymbol{e'}_2 \}_{her}$。可以利用$me$坐标系 $\{\boldsymbol{e}_1, \boldsymbol{e}_2\}_{me}$ 重新表示$her$坐标系的基$\boldsymbol{e'}_1$ 和 $\boldsymbol{e'}_2$:

$$
\boldsymbol{e'}_1=\begin{bmatrix}a\\b\end{bmatrix} ,\, \boldsymbol{e'}_2=\begin{bmatrix}c\\d\end{bmatrix}
$$  

一向量$\vec{v}$在不同坐标系下

$$\begin{align}
\vec{v} \, 
= \, X_1 \cdot \boldsymbol{e}_1 \,+\, X_2 \cdot \boldsymbol{e}_2 \,
&= \, x\cdot\boldsymbol{e'}_1 \, + \, y\cdot\boldsymbol{e'}_2 
\\
\begin{bmatrix}X_1\\X_2\end{bmatrix}
&= x \cdot \begin{bmatrix}a\\b\end{bmatrix} + y \cdot \begin{bmatrix}c\\d\end{bmatrix}
\\
\begin{bmatrix} X_1 \\ X_2 \end{bmatrix}_{e} &= \begin{bmatrix} a & c \\ b & d \end{bmatrix} \begin{bmatrix} x\\ y\end{bmatrix}_{e'} 
\end{align}$$

其中
$$P=\begin{bmatrix}\boldsymbol{e'}_1 & \boldsymbol{e'}_2\end{bmatrix}
=\begin{bmatrix} a & c \\ b & d \end{bmatrix}_{me-represent-her}$$
就是**基变换矩阵**，或**过度矩阵**。


##### 不同基下的坐标

**例**：下图用$e$来代表$\{\vec{e_1},\vec{e_2}\}$的自然基，$e'$来代表$\{\vec{e_1'},\vec{e_2'}\}$基：

$$
\vec{e_1}=\begin{bmatrix}1\\0\end{bmatrix}_{e}
,\quad 
\vec{e_2}=\begin{bmatrix}0\\1\end{bmatrix}_{e}
$$

$$
\vec{e_1'}=\begin{bmatrix}0.5\\-0.5\end{bmatrix}_{e}
,\quad 
\vec{e_2'}=\begin{bmatrix}0.5\\0.5\end{bmatrix}_{e}
$$

<img src="./Figure/BasisTransformation-1.png" style="zoom:50%" />

$$\vec{x}_\boldsymbol{e} = \boldsymbol{P} \cdot \vec{x}_\boldsymbol{e'} \\
\vec{x}_\boldsymbol{e'} = \boldsymbol{P}^{-1} \cdot \vec{x}_\boldsymbol{e}$$

**正向过程**： 
$$
\begin{aligned}
    \begin{bmatrix}-2\\0\end{bmatrix}_{e'} 
    &= -2 \, \vec{e_1'} \,+\, 0\,\vec{e_2'}\\
    &= -2\begin{bmatrix}0.5\\-0.5\end{bmatrix}_{e}+0\begin{bmatrix}0.5\\0.5\end{bmatrix}_{e}\\
    &= \begin{bmatrix}-1\\1\end{bmatrix}_{e}
\end{aligned}
$$

写成矩阵乘法形式：

$$
\underbrace{\begin{bmatrix}0.5&0.5\\-0.5&0.5\end{bmatrix}}_{P}\begin{bmatrix}-2\\0\end{bmatrix}_{e'}=\begin{bmatrix}-1\\1\end{bmatrix}_{e}
$$




**反向过程**：  
$$
\begin{bmatrix}?\\?\end{bmatrix}_{e'}
\stackrel{P^{-1}}{\Longleftarrow}
\begin{bmatrix}-1\\1\end{bmatrix}_{e}
$$

上述矩阵$P$的逆矩阵为：
$$
P^{-1}=\begin{bmatrix}1&-1\\1&1\end{bmatrix}
$$

可以通过它把坐标变换回去：
$$
\begin{bmatrix}-2\\0\end{bmatrix}_{e'}=\underbrace{\begin{bmatrix}1&-1\\1&1\end{bmatrix}}_{P^{-1}}\begin{bmatrix}-1\\1\end{bmatrix}_{e}
$$

## 在另一坐标系下做线性变换

$\vec{e'}$ 往 $\vec{e''}$ 做映射
<img src="./Figure/map.png" style="zoom:25%" />

$$\boldsymbol{B}=\boldsymbol{P}^{-1}\boldsymbol{A}\boldsymbol{Q}$$
$\boldsymbol{A}$和$\boldsymbol{B}$等价

$\vec{e'}$ 往 $\vec{e'}$ 做映射
<img src="./Figure/map2.png" style="zoom:25%" />

$$\boldsymbol{B}=\boldsymbol{P}^{-1}\boldsymbol{A}\boldsymbol{P}$$
$\boldsymbol{A}$和$\boldsymbol{B}$相似

##### Example

在自然基坐标系下对向量$(\vec{v})_{e}$做一次逆时针旋转$90^{\circ}$操作，只需要$A\vec{v}$即可，其中
$$A=\begin{bmatrix}0&-1\\1&0\end{bmatrix}$$

但当我们想对另一个坐标系描述的$(\vec{v})_{e'}$同样做逆时针旋转$90^{\circ}$的操作时，就需要同时使用基变换和线性变换。首先需要将$(\vec{v})_{e'}$在我们的坐标系$e$下表达：
$$
P\vec{v}
$$

然后在我们的坐标系$e$中做熟悉的线性变换操作$A$：
$$
AP\vec{v}
$$

最后还要将坐标系从目前的我们的坐标系$e$换回之前陌生的坐标系$e'$，在$e'$下表示旋转后的向量：
$$
P^{-1}AP\vec{v}
$$


## 特征值与特征向量

3Blue1Brown线性代数的本质之特征向量与特征值：https://www.bilibili.com/video/BV1Ls411b7oL/

###### 几何含义

如下图，考虑一个线性变换$A$
$$A=\begin{bmatrix}3&1\\0&2\end{bmatrix}$$
通常一个向量会在经过线性变换$A$后偏离它原来自身所张成的空间（即偏离变换前向量原来所在的直线）。

<table>
<td> 
<img src="./Figure/3blue1brown-eigenvalue-1.png" width="250" hight="100" /> <br>
</td> 
<td> 
<img src="./Figure/3blue1brown-eigenvalue-2.png" width="250" hight="100" /><br>
</td> 
</table>

**但有些向量，在经过$A$的变换前后，依然保留在原本自身的张成空间里，即只发生长度的伸长或缩短**。  

对于$A$这一线性变换，这样的向量有两个：

$$
\vec{s}_1 = \begin{bmatrix}1 \\ 0\end{bmatrix} ,\quad
\vec{s}_2 = \begin{bmatrix}-1 \\ 1\end{bmatrix}
$$

那么$\vec{s}_1,\vec{s}_2$就称为线性变换$A$的特征向量。  
这两个方向上的所有向量都发生同样的伸长和缩短，对于$\vec{s}_1$这个方向伸长了3倍，而$\vec{s}_2$这个方向伸长了2倍，那么我们称缩放的值为特征向量的特征值。若特征值为负，则说明该特征向量所在的方向，所有向量都方向发生翻转。

<table>
<td> 
<img src="./Figure/3blue1brown-eigenvalue-3.png" width="300" hight="100" /> <br>
</td> 
<td> 
<img src="./Figure/3blue1brown-eigenvalue-4.png" width="300" hight="100" /><br>
</td> 
</table>

使用特征向量的好处是可以很直观的理解一种线性变换，比如,可以想之前那样把线性变换$A$理解为基向量从
$\hat{i}=\begin{bmatrix}1 \\ 0\end{bmatrix}$移动到$\begin{bmatrix} 3 \\ 0 \end{bmatrix}$，$\hat{j}=\begin{bmatrix}0 \\ 1\end{bmatrix}$移动到$\begin{bmatrix}1 \\ 2\end{bmatrix}$。但我们可以计算$A$对应的特征向量与特征根，然后将$A$的特征向量$\begin{bmatrix}1 \\ 0\end{bmatrix}$和$\begin{bmatrix}-1 \\ 1\end{bmatrix}$当作基向量，那么原本的线性变换$A$就成了简单的缩放$\begin{bmatrix}3 & 0\\ 0 & 2\end{bmatrix}$。

###### 特征值的计算方法

根据上述特征值与特征向量的几何含义，我们可以得知，对于特征向量$\vec{v}$，在经过线性变换$A$后，只发生长度缩放，倍率为$\lambda$，表示为：
$$
\color{Salmon}{A\vec{v}=\lambda\vec{v}}
$$

那么有
$$A\vec{v}=(\lambda I) \vec{v}$$
$$A\vec{v}-(\lambda I)\vec{v} = \boldsymbol{0}$$
$$(A-\lambda I)\vec{v} = \boldsymbol{0}$$

此时我们要找到非$\boldsymbol{0}$的$\vec{v}$，使这个非$\boldsymbol{0}$的$\vec{v}$经过$(A-\lambda I)$的线性变换后成为零向量。即$\vec{v}$所张成的1维空间被降为压缩为一个点(0维)，或者原本向量基所张成的空间（2维）被压缩成一条线（1维，方向垂直于$\vec{v}$），这就需要

$$\color{Salmon}{det(A-\lambda I))=0}$$

才能让$(A-\lambda I)\vec{v} = \boldsymbol{0}$成立。满足该等式的$\lambda$就是要求的特征向量。


## 对角化

<img src="./Figure/diagnalize.png" style="zoom:25%" />

### 特征向量与对角化

**对角化就是以特征向量为基**。若$A$为$n$阶矩阵。  
有$n$个**线性无关**的**特征向量**：
$\vec{s}_1,\vec{s}_2,\cdots,\vec{s}_n$；  
对应的$n$个特征值为：$\lambda_1,\lambda_2,\cdots,\lambda_n$；  
由特征向量组成的$\color{Salmon}{特征矩阵}$$\color{Salmon}{S}$表示为：
$$
\boldsymbol{P}=(\vec{s}_1,\vec{s}_2,\cdots,\vec{s}_n)
$$

则有：
$$
\boldsymbol{P}^{-1}\boldsymbol{A}\boldsymbol{P}=\boldsymbol{\Lambda}
$$

其中，$\Lambda$为：
$$
\Lambda=
\begin{bmatrix}
    \lambda_1&0&\cdots&0\\
    0&\lambda_2&\cdots&0\\
    \vdots&\vdots&\quad&\vdots\\
    0&0&\cdots&\lambda_n
\end{bmatrix}
$$

从对角化的定义中可以看出：$n$阶矩阵可对角化$\iff$$n$个线性无关的特征向量。
$$
\text{特征值不同}\implies\text{特征向量线性无关}\iff\text{可对角化}
$$

矩阵对角化后有**许多好处**，
* 如**特征根相同**；  
* **行列式相同**$|A|=|\Lambda|$；  
* 还**方便求矩阵的多次幂** $ A^n = P^{-1} \Lambda^{n} P $

$$
\begin{aligned}
    A^n &= (P^{-1} \Lambda P)^{n} \\
    &= P^{-1} \Lambda PP^{-1} \Lambda P \dots P^{-1} \Lambda P \\
    &= P^{-1} \Lambda^{n} P
\end{aligned}
$$

### 对角化与连续介质力学级分解

在连续介质力学中，为了实现级分解
$$\boldsymbol{F}=\boldsymbol{R}\boldsymbol{U}$$

一般有
$$\boldsymbol{C}=\boldsymbol{F}^{\rm{T}}\boldsymbol{F}$$

通过对$\boldsymbol{C}$求特征根和特征向量，得到对角矩阵$\boldsymbol{\Lambda}$和特征矩阵$\boldsymbol{P}$。主方向上的右伸长张量$\boldsymbol{U}^{'} = \sqrt{\boldsymbol{\Lambda}}$。
$$\boldsymbol{U}^{'} = \boldsymbol{P}^{-1} \, \boldsymbol{U} \, \boldsymbol{P}$$

为了得到在自然坐标系下的右伸长张量$\boldsymbol{U}$：$\boldsymbol{Q} = \boldsymbol{P}^{-1} \, \boldsymbol{U} \, \boldsymbol{P}$
$$\boldsymbol{U} = \boldsymbol{P} \, \boldsymbol{U}^{'} \, \boldsymbol{P}^{-1}$$

最后
$$\boldsymbol{R} = \boldsymbol{F} \, \boldsymbol{U}^{-1} $$

## 标准正交基与正交矩阵

对角化就是以特征向量为基，特征向量算是一种“好”的基，另外一种“好”的基是**标准正交基**。

设$n$维向量$\vec{\epsilon}_1,\vec{\epsilon}_2,\cdots,\vec{\epsilon}_r$是向量空间$V(V\subset \mathbb{R^n})$的一个基，且两两正交：
$$
\vec{\epsilon}_i\cdot\vec{\epsilon}_j=0
$$

模长为1:
$$
||\vec{\epsilon}_1||=||\vec{\epsilon}_2||=\cdots=||\vec{\epsilon}_r||=1
$$

那么，$\vec{\epsilon}_1,\vec{\epsilon}_2,\cdots,\vec{\epsilon}_r$是$V(V\subset \mathbb{R^n})$的**标准正交基**。

标准基可以保留自然基下的许多公式结论，而非标准基就不一定。如求距离的公式在非标准基下就不能直接使用。而标准正交基和自然基相比，只是发生了旋转（或者镜像），很多公式稍加修改、甚至不需要修改就可以使用。

标准正交基之间的过渡矩阵称$P$为**正交矩阵**
$$
P^TP=I,即P^T=P^{-1}
$$


```python

```
