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
