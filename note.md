## Lecture 10: four fundanmental subspace
* column space：$C(A)$
* nullspace：$N(A)$
* row space：$C(A^T)$
* left nullspace：$N(A^T)$

意义：$C(A)$回答了$Ax=b$什么时候有解这个问题，$N(A)$回答了$Ax=0$什么时候有解这个问题；而对应的row space和left nullspace回答了$A^T$对应的问题。

求法：
column space：将A化简为R，可以从R中看出哪些列是pivot column，然后**回到A中对应的column**，这些column的线性组合就构成A的column space；（注：A的Colum space和R的column space不是一个空间）

nullspace：将free variables分别赋值为1，利用方程解出对应pivot variables的值，其线性组合就是nullspace

row space：R中非零行的线性组合

left nullspace：

遗留问题
* [ ] 为什么row space的basis就是R中非零行的线性组合？
* [ ] left nullspace的求法？
* [ ] assignment的最后两题？

## Lecture 11: Matrix spaces;rank 1;graphs
* Matrix space
教授主要讲了Matrix space其实是和vector space类似的，它也有所谓的子空间，也有一些basis和dimension的概念。
* 秩为1的矩阵
如果一个矩阵的秩为1，那他应该是一个比较简单矩阵，可以写成两个向量的乘积
* 对矩阵在图问题中的应用开了一点头
具体内容在lecture12讲解

## Lecture 12:Graph,network
这节lecture主要讲了线性代数的应用，主要以有向图为例；
一个有向图可以用一个矩阵来表示，我们可以通过对矩阵进行一些分析，可以得出图的相关性质，如：
* 一些边是否构成环，与row column是否独立有关
* 用线性代数可以推出一些工程有用的结论，如node-edges+loop=1.

## Lecture 14 & Lecture 15
###背景：
这些系列lecture想要解决的问题是：如何“求解”$Ax=b$当$Ax=b$实际上无解
一个最直接的应用就是拟合，如我们想用一个线性模型来拟合实验得到的数据，即我们得到了一系列方程；我们的目的是通过方程求出参数；写成矩阵的形式就是$Ax=b$,但这个方程组可能由于实验中各种误差导致没有解，所以我们需要通过一些方法来找出最优的近似解。

* vectors orthogonal -> subspace orthogonal
    可以从几何上看出四种子空间的关系
    nullspace and row sapce are oothogonal complements in R^n
* something abount A^T*A
    N(A^TA) = N(A)
*  projection
    介绍了如何找出$A\hat{x}=p$中的$\hat{x}$,(其中p为任意向量b在subspaceA中的投影)，通过$\hat{x}$可以得到p，通过化简$A\hat{x}=p$可以得到投影矩阵P

## Lecture 16: Projection matrices and least squares
核心：这节课讲的就是用上节课的方法来进行拟合以及为什么这样效果比较好。
> 上节课的方法：当求解方程$Ax=b(b不在A的column space)$,我们要做的就是改为求解$A^TA\hat{x}=A^Tb$中的$\hat{x}$；
* 看待误差的角度
    在拟合时的误差，我们可以从两个角度去看：第一个就是在x-y平面拉一条线，线上的点与实际点的距离就是误差；第二个就是四种subspace的big picture，向量b不在矩阵A的columnspace中，将向量b向A的columnspace中投影，可将b拆为e+p，向量e就是误差
* 为什么用上面哪种方法误差就最小？
    以线性代数的角度去看：在big picture中，想要向量e最小，那就将b直直的投影在columnspace上，这样出来的e是最短的；而上面那个公式，将左边$A^TA$移到右边去，$(A^TA)^{-1}A^T$就是投影矩阵P。
    以微积分的视角：在x-y平面中，误差就是距离，通过对误差平方求和，在求偏导，可以发现得到的方程组与上面方法一致！
* 方法的使用条件：$A^TA$可逆 or 矩阵A的列相互独立
    上面的两个条件是等价的，证明如下
> $A^TAx=0$,等式两边同乘以$x^T$,就可以得到要想$A^TAx=0$，就需要$Ax=0$,又因为A的列相互独立，所以只有唯一解x=0；所以矩阵$A^TA$的nullspace只有零向量，而$A^TA$为方阵，所以可逆。