我们假设本文所出现的环都是含幺交换环，即有一个乘法单位元的交换环，并且，我们所谓的环同态，他将单位元映到单位元。特别地，我们约定，零环即$R=\\{0\\}$，其中乘法单位元和加法单位元相等，即$0=1$。在环（即我们这里所谓的环）范畴中，零环的地位大致相当于集合范畴中的空集。所以下面我们在提到环的时候，经常是默认该环不是零环。此外，我们下面谈及的模也都是含幺交换环上的模，所以不分左右双边。

## 1.1. Sheafs and Ringed Spaces 

1.1 一个拓扑空间$X$能被看成一个范畴，对象是他的开集，而态射取作\\[\mathrm{Mor}\_{X}(U,V)=\begin{cases}
\bigl\\{i^U\_V:U\hookrightarrow V\bigr\\}&\text{, if }U\subset V\text{;}\\\
\varnothing&\text{, otherwise}.
\end{cases}\\]


1.2 对于任意的范畴$K$，一个拓扑空间$X$，我们称呼一个取值在$K$中的预层$F$（简称为$K$-预层）是一个$X\to K$的反变函子，特别地，记态射$F(i^U\_V)$为$\rho^U\_V$. $F(U)$中的元素$s$被称为$U$上的一个截面，而$s|\_V:=\rho^U\_V(s)$被称为截面$s$在$V$上的限制。

1.3 设$A\in K$是范畴$K$里面的一个对象，而$F$是$X$上的一个预层，$U$是$X$的任意开子集, 而$\\{U\_\alpha\\}\_{\alpha\in I}$是$U$的任意开覆盖，如果存在态射族$\\{\varphi\_\alpha:A\to F(U\_\alpha)\\}\_{\alpha\in I}$使得下图交换（画图的时候省去了限制映射）\\[\xymatrix{
	A\ar[r]^{\varphi\_{\alpha}}\ar[d]\_{\varphi\_{\beta}}&F(U\_\beta)\ar[d]\\\
	F(U\_\alpha)\ar[r]&F(U\_{\alpha}\cap U\_{\beta})
}\\]则存在唯一的态射$\varphi:A\to F(U)$使得下图交换的时候，\\[\xymatrix{
	A\ar@/\_/[ddr]\_{\varphi\_{\alpha}}\ar@/^/[drr]^{\varphi\_{\beta}}\ar@{.>}[dr]|{\varphi}&& \\\
	&F(U)\ar[r]\ar[d]&F(U\_\beta)\ar[d]\\\
	&F(U\_\alpha)\ar[r]&F(U\_{\alpha}\cap U\_{\beta})
}\\]预层$F$被称为一个层。这些条件被称为层公理。如果需要明确取值的范畴是$K$，则称为$K$-层。

1.4 所有$X$上的预层构成一个范畴，态射就是所谓的函子间态射，或者叫做自然变换：设$F$和$G$是$X$上的两个预层，设$\varphi(U)$是使得如下交换图交换的一族态射，\\[\xymatrix{
	F(U)\ar[rr]^{\varphi(U)} \ar[d]\_{\rho^U\_V}&&G(U) \ar[d]^{\pi^U\_V}\\\
	F(V)\ar[rr]^{\varphi(V)}&&G(V)
}\\]则称呼$\varphi$是$F$到$G$的一个态射，记做$\varphi:F\to G$. 层之间的态射就是作为预层的态射。很自然地，如果已知一个预层态射$\varphi:F\to G$，即使$F$是一个层，也不能断言$G$是一个层。

1.5 当$K$是交换群范畴的时候，很容易发现上面关于层的定义和我们熟知的层的定义是等价的，即局部相容的截面可以唯一地拼成一个整体的截面。这点只要将$A$取作$\prod\_{\alpha\in I}F(U\_\alpha)$即可。

1.6 两个层的例子，流形$M$上，每一个开集$U$上的光滑函数的全体构成一个环，记作$F(U)$，则这是一个预层，$U$上的截面就是$U$上的光滑函数。这显然是一个层，因为光滑性是局部概念，如果两个光滑函数限制在同一个开集上是相同的，那么我们自然可以拼成一个唯一的更大的光滑函数，一族也是类似的。

另一个例子来自代数簇，设$X$是一个代数簇，他的每一个开集$U$都是一个子代数簇，自然有相应的正则函数环$F(U)$，则这是也给预层，$U$上的截面就是$U$上的正则函数。这依然是一个层，因为正则性还是局部概念，可以拼接的理由同上。

1.7 设$F$是$X$上的一个预层，如果范畴$K$能容纳colimit，那么定义$F$在$p\in X$处的纤维$F\_p$为$\varinjlim F(U)$，其中$U$跑遍所有$p$的邻域，这些领域通过包含构成一个显然的direct system。

对于交换群范畴，直接写出具体构造还是比较方便的，$F\_p$中的元素是这样的等价类$\langle U,f\rangle$的全体，其中$f$是$U$上的截面，而$U$是$p$的邻域。等价关系定义为$\langle U,f\rangle\sim \langle V,g\rangle$，当且仅当存在一个$p$的邻域$W\subset U\cap V$使得$f|\_W=g|\_W$.

利用colimit的泛性质，我们发现，预层间的态射$\varphi:F\to G$如下图在局部诱导了$\varphi\_p:F\_p\to G\_p$.\\[\xymatrix{
	&&F(U)\ar[dl]^{\rho\_{Up}}\ar[dd]^{\rho\_{UV}}\ar@/\_/[lld]\_{\rho'\_{Up}\circ\varphi(U)} \\\
	G\_p&F\_p\ar@{-->}[l]\_(0.4){\varphi\_p}&\\\
	&&F(V)\ar[ul]\_{\rho\_{Vp}}\ar@/^/[llu]^{\rho'\_{Vp}\circ\varphi(V)}
}\\]

1.8 考虑$\mathfrak{B}$是$X$的拓扑基，则同拓扑空间一样，我们取对象为基中的元素，态射为内含映射，则自然他也构成一个范畴。类似地，我们可以定义$\mathfrak{B}$上取值在$K$的预层为$\mathfrak{B}$到$K$的一个反变函子，层公理也可以一模一样搬过来。

如果范畴$K$可以容纳limit，而$F$是$\mathfrak{B}$上的一个预层，则我们可以通过$F'(U)=\varprojlim F(V)$定义出$X$上的一个预层$F'$，其中$V$跑遍集合$\\{V\in \mathfrak{B}\\,:\\, V\subset U\\}$，而这个集合通过包含构成一个显然的投影系。

pro 9 如果范畴$K$可以容纳limit，且$F$是$\mathfrak{B}$上的一个层，$\mathfrak{B}$上的层诱导的预层$F'$也是一个层。证明完全是泛性质的练习，见[EGA, Chap 0, 3.2].

1.10 对于$X$上的$K$-层$F$，很自然可以定义层$F$在$U$上的限制$F|\_U$，这是一个$U$上的预层，对于$U$中的开集，有$F|\_U(V)=F(V)$，限制态射直接从$F$那里继承过来。显然这也是一个层。

pro 11 现在我们可以讨论层的黏合。设$\\{U\_\alpha\\}\_{\alpha \in I}$是$X$的一个开覆盖，如果分别在每一个$U\_\alpha$上有一个层$F\_\alpha$，而且对于任意的指标组$(\alpha,\beta)$，都有一个同构$\theta\_{\alpha\beta}:F\_\alpha|\_{U\_\alpha\cap U\_\beta}\to F\_\beta|\_{U\_\alpha\cap U\_\beta}$. 以及对于任意的指标组$(\alpha,\beta,\gamma)$成立$\theta'\_{\alpha\gamma}=\theta'\_{\alpha\beta}\circ \theta'\_{\beta\gamma}$，其中$\theta'\_{\star\star}$是态射$\theta\_{\star\star}$在$U\_\alpha\cap U\_\beta \cap U\_\gamma$上的限制。则存在一个环层$F$和一族同构$\eta\_\alpha:F|\_{U\_\alpha}\to F\_\alpha$.

*Proof.* 选取包含在某个开覆盖的开集的全体，这是全空间的一个拓扑基，命题中的黏合条件自然地给出层的条件。详细见[EGA, Chap 0, 3.3].<p align = right>Q.E.D.</p>

1.12 设$\varphi:X\to Y$是拓扑空间之间的连续映射，而$F$是$X$上的一个预层，则通过$f\_\*F(U)=F(f^{-1}(U))$我们可以定义出$Y$上的一个预层$f\_\*F$，他被称为$F$关于$f$的顺像。 由于原象是保持包含关系的，即如果$V\subset U$，则$f^{-1}(V)\subset f^{-1}(U)$，所以$f\_\*F$上的限制映射就很自然地习作f. 不难检验，当$F$是$X$上的一个层的时候，$f\_\*F$是$Y$上的一个层。

设$\varphi:F\to G$是$X$上两个预层之间的态射，那么，很自然，$f$诱导了一个新的态射$f\_\*\varphi:f\_\*F\to f\_\*G$，具体写出来就是$(f\_\*\varphi)(U)=\varphi(f^{-1}(U))$，通过自然变换$\varphi$可以验证$f\_\*\varphi$是一个自然变换。

考虑两个连续映射的复合，很自然地可以验证$(f\circ g)\_\*=f\_\*\circ g\_\*$，这来自于关于原象的等式$(f\circ g)^{-1}(U)=g^{-1}(f^{-1}(U))$.

1.13 所谓的赋环空间(ringed space)，就是一个拓扑空间$X$，和拓扑空间上的环层$\mathcal{O}\_X$构成的资料$(X,\mathcal{O}\_X)$. 流形和上面的光滑函数构成一个赋环空间，同样，代数簇和上面的正则函数构成一个赋环空间。

所谓的局部赋环空间，就是说任意一点$p\in X$处的纤维$\mathcal{O}\_p=\varinjlim \mathcal{O}\_X(U)$是局部环。流形的例子是一个局部赋环空间，因为在$p$附近的光滑函数，如果在$p$处不为零，则存在一个邻域是可逆的，故而，在$p$处为零的光滑函数构成的等价类是唯一的极大理想。代数簇的例子还是一个局部赋环空间，因为代数簇局部是仿射的，所以我们可以假设这是一个仿射簇，对于仿射簇而言，$X$中的点$p$（如果是非代数闭的情况，那就是一条Galois轨道）一一对应着坐标环$A(X)$中的一个极大理想$\mathfrak{m}\_p$（这来自于Hilbert零点定理），而$\mathcal{O}\_p$正好同构于$A(X)$关于$\mathfrak{m}\_p$的局部化，所以是一个局部环。

赋环空间之间的态射如下定义：设有赋环空间$(X,\mathcal{O}\_X)$和$(Y,\mathcal{O}\_Y)$，以及连续映射$\psi:X\to Y$和$Y$上的层之间的同态$\theta:\mathcal{O}\_Y\to \psi\_\*\mathcal{O}\_X$，这样的一个二元组$\Psi=(\psi,\theta)$构成了赋环空间范畴的同态，记做$\Psi:(X,\mathcal{O}\_X)\to (Y,\mathcal{O}\_Y)$.

要确切地理解是一个同态，则需要验证复合，假设$\Phi=(\psi',\theta'):(Y,\mathcal{O}\_Y)\to (Z,\mathcal{O}\_Z)$是另一个态射，在$\Phi\circ \Psi$中，连续映射的复合不用多说，对于层的复合，则如图所示\\[\mathcal{O}\_Z\xrightarrow{\theta'} \psi'\_\*\mathcal{O}\_Y \xrightarrow{\psi'\_\*\theta} \psi'\_\*\psi\_\*\mathcal{O}\_X,\\]写成$(\psi'\_\*\theta)\circ \theta'$的形式。

1.14 有了顺像，我们现在考虑逆像，设$\psi:X\to Y$是一个连续映射，而$F$是$X$上的一个层，$G$是$Y$上的一个预层。预层$G$关于$\psi$的逆像首先是这样一个二元组$(\psi^\*G,\rho\_G)$，其中$\psi^\*G$是$X$上的层，而$\rho\_G$是$G$到$\psi\_\*\psi^\*G$的典范态射。其次对于任意的态射$u:G \to \psi\_\*F$，都可以找到唯一的态射$v:\psi^\*G \to F$使得分解$u:G\xrightarrow{\rho\_G} \psi\_\*\psi^\*G \xrightarrow{\psi\_\*v} \psi\_\*F$成立。换而言之，集合$\mathrm{Hom}\_X(\psi^\*G,F)$和$\mathrm{Hom}\_Y(G,\psi\_\*F)$之间存在双射。$(\psi^\*G,\rho\_G)$满足的是一个泛性质，所以逆像确定到一个同构上。当然对于逆像的存在性我们现在还不清楚。

特别地，$1\_X:X\to X$是恒同映射，对于$X$上的预层$F$，如果层$1\_X^\*F$存在，则他称为$F$的伴随层，有时候也被记做$F^+$. 对于任意的层$F'$和态射$u:F\to F'$，总有唯一分解$u:F\xrightarrow{\rho\_F} F^+ \xrightarrow{v} F'$成立。这意味着层的伴随层与自己同构。

1.15 对于一些特殊情况，逆像层总是存在的。考虑一个内含映射的例子，设$U$是$X$的开子集，相应的内含映射为$i:U\hookrightarrow X$。对于$X$上的$K$-层$F$，$F|\_U$即其在$U$上的逆像层$i^\*F$.

*Proof.* 为此，我们先假设这是对的，然后检查泛性质即可。现在还缺一个典范态射$F\to i\_\*i^\*F$，由于我们假设了$i^\*F=F|\_U$，所以$i\_\*i^\*F(V)=i^\*F(i^{-1}(V))=F|\_U(U\cap V)=F(U\cap V)$. 那么限制映射族$\rho^V\_{U\cap V}:F(V)\to F(U\cap V)$可以构成层之间的态射$F\to i\_\*i^\*F$，我们将其记做$i^\\#$，我们希望这就是典范态射。

剩下的不过是检查$(F|\_U,i^\\#)$所需要满足的泛性质。设$G$是$U$上的一个层，对于任意的态射$u:F\to i\_\*G$，他具有形式$u(V):F(V)\to i\_\*G(V)=G(U\cap V)$. 遍历$U$中的开集$V$，我们定义$v(V)=u(V):F(V)\to G(U\cap V)=G(V)$，此时由于$i^\*F(V)=F|\_U(V)=F(V)$，所以我们定义出了一族态射$v(V):i^\*F(V)=F(V)\to G(V)$，自然也得到了态射$v:i^\*F\to G$. 这样定出来的$v$显然是唯一的。最后，需要检查分解$u:F\xrightarrow{i^\\#} i\_\*i^\*F \xrightarrow{i\_\*v} i\_\*G$成立，这个分解其实说白了就是，已知如下交换图（图中的限制映射都略去了）成立，\\[\xymatrix{
	F(V)\ar[r]^{u(V)} \ar[d]&G(U\cap V) \ar[d]\\\
	F(W)\ar[r]^{u(W)}&G(U\cap W)
}\\]其中$W\subset V$是$X$中的开集，要验证定出来的$v$使得如下交换图成立。\\[\xymatrix{
	F(V)\ar[r] \ar[d]&F(U\cap V)\ar[r]^{v(U\cap V)}\ar[d]&G(U\cap V) \ar[d]\\\
	F(W)\ar[r]&F(U\cap W)\ar[r]^{v(U\cap W)}&G(U\cap W)
}\\]这个并不困难，左边一个矩形的交换性来自于限制映射的复合，这是自然的，右边一个矩形的交换性来自于$v$的定义和上面一个交换图，所以最后要检验的不过是横向的那个分解，即对于任意的开集$V$，分解$u(V):F(V)\to F(U\cap V) \xrightarrow{v(U\cap V)} G(U\cap V)$成立。

现考虑如下交换图，\\[\xymatrix{
	F(V)\ar[r]^{u(V)} \ar[d]&G(U\cap V) \ar@{=}[d]\\\
	F(U\cap V)\ar[r]^{u(U\cap V)}&G(U\cap V)
}\\]这就得出了$u(V)=u(U\cap V)\circ \rho^V\_{U\cap V}$，而$v(U\cap V)=u(U\cap V)$，所以$u(V)=v(U\cap V)\circ \rho^V\_{U\cap V}$，即交换图横向的分解成立。逆像层的泛性质检验完毕。<p align = right>Q.E.D.</p>

1.16 应用到赋环空间，我们就有了一个赋环空间的态射$(i,i^\\#):(U,\mathcal{O}\_U)\to (X,\mathcal{O}\_X)$，其中$\mathcal{O}\_U=\mathcal{O}\_X|\_U$，他被称为赋环空间的典范内含态射。

设$\Phi:(X,\mathcal{O}\_X)\to (Y,\mathcal{O}\_Y)$是一个态射，他在$U\subset X$上的限制记做$\Phi|\_U:=\Phi\circ (i,i^\\#)$，如果$\Phi=(\psi,\theta)$，则$\Phi|\_U=\bigl(\psi|\_U, \psi\_\*(i^\\#) \circ \theta\bigr):(U,\mathcal{O}\_U)\to (Y,\mathcal{O}\_Y)$，层之间的态射具体写出来即\\[\mathcal{O}\_Y\xrightarrow{\theta} \psi\_\*\mathcal{O}\_X \xrightarrow{\psi\_\*(i^\\#)} \psi\_\*i\_\*\mathcal{O}\_U=\bigl(\psi|\_U\bigr)\_\*\mathcal{O}\_U,\\]其中$\psi\_\*(i^\\#)(V)=i^\\#\bigl(\psi^{-1}(V)\bigr)=\rho^{\psi^{-1}(V)}\_{U\cap \psi^{-1}(V)}$，设$s\in \mathcal{O}\_Y(V)$是一个截面，那么表现为\\[\psi\_\*(i^\\#)(V)\circ \theta(V)(s)=\theta(V)(s)|\_{U\cap \psi^{-1}(V)}.\\]很容易验证，如果$V$又是$U$的一个开子集，则$(\Phi|\_U)|\_V=\Phi|\_V$.

pro 17 有了限制的知识，就可以讨论赋环空间间态射的黏合。设$(X,\mathcal{O}\_X)$是一个赋环空间，并且$\\{U\_\alpha\\}\_{\alpha\in I}$是一个$X$的开覆盖。如果我们有一族态射$\Phi\_\alpha:(U\_{\alpha},\mathcal{O}\_{U\_{\alpha}})\to (Y,\mathcal{O}\_Y)$，对于任意的两个指标$(\alpha,\beta)$，成立$\Phi\_\alpha|\_{U\_{\alpha}\cap U\_{\alpha}}=\Phi\_\beta|\_{U\_{\alpha}\cap U\_{\alpha}}$，则存在一个态射$\Phi:(X,\mathcal{O}\_{X})\to (Y,\mathcal{O}\_Y)$使得$\Phi|\_{U\_{\alpha}}=\Phi\_\alpha$.

*Proof.* 连续函数在开覆盖上的黏合是显然的，对于层的态射那部分，用的技术无外乎层上截面的黏合，这是很琐碎的检验，这里略去了。<p align = right>Q.E.D.</p>

pro 18 设$\psi:X\to Y$是一个连续映射，$F$是$X$上的一个$K$-层，而$G$是$Y$上的一个$K$-预层。如果范畴$K$是交换群范畴，则$G$关于$\psi$的逆像层$\psi^\*G$存在。

*Proof.* 
证明是直接的构造。交换群范畴，我们知道预层的纤维总是存在的。所以我们这样定义$\psi^\*G$：对$X$中的开集$U$, 令$\psi^\*G(U)$是函数$s:U\to \bigcup\_{p\in U}G\_{\psi(p)}$的集合，这些函数需要满足

* 对任意的$p\in U$, $s(p)\in G\_{\psi(p)}$，以及

* 对任意的$p\in U$，总存在$\psi(p)$的一个开邻域$V$，$p$的一个邻域$W\subset \psi^{-1}(V)\cap U$和一个元素$t\in G(V)$，使得当$q\in W$的时候总有$s\_q=t\_{\psi(q)}$.

$\psi^\*G(U)$上的加法直接定义为$(s+t)(p)=s(p)+t(p)$，因此$\psi^\*G(U)$是一个交换群。如果$V$是$U$的开子集，那么函数限制$i^U\_V:\psi^\*G(U)\to \psi^\*G(V)$就是所需要的预层的限制映射，记$i^U\_V(s)=s|\_V$，因此$\psi^\*G$是一个预层。令$\\{U\_i\\}$是$U$的一个开覆盖，且$s\_i\in \psi^\*G(U\_i)$是局部截面。如果$s\_i|\_{U\_i\cap U\_j}=s\_j|\_{U\_i\cap U\_j}$，那么我们能定义一个函数$s:U\to \bigcup\_{p\in U}F\_p$通过$s|\_{U\_i}=s\_i$，函数完全由其值确定，所以唯一性也得证。因此$\psi^\*G$是一个层。

现在设$U$是$Y$的一个开集，对于$s\in G(U)$, 我们定义一个$s^+\in \psi^\*G(\psi^{-1}(U))$通过$s^+(p)=s\_{\psi(p)}$，其中$p\in \psi^{-1}(U)$. 由于$\psi^\*G(\psi^{-1}(U))=\psi\_\*\psi^\*G(U)$，所以我们就通过$\rho\_{G}(U):s\mapsto s^+$定义了态射$\rho\_{G}(U):G(U)\to \psi\_\*\psi^\*G(U)$. 下面要检验$\rho\_{G}$是一个自然变换。

由于$i$在$\psi\_\*\psi^\*G$诱导的限制映射的形式为$\pi^U\_V=i^{\psi^{-1}(U)}\_{\psi^{-1}(V)}$，所以对任意的$s\in G(U)$，因为\\[	\pi^U\_V\bigl(\rho\_{G}(U)(s)\bigr)=i^{\psi^{-1}(U)}\_{\psi^{-1}(V)}\left(\\{p\mapsto s\_{\psi(p)}\\,:\\, p\in \psi^{-1}(U)\\}\right)=\\{p\mapsto s\_{\psi(p)}\\,:\\, p\in \psi^{-1}(V)\\},\\]以及\\[	\rho\_{G}(V)\bigl(\rho^U\_V(s)\bigr)=\rho\_{G}(V)(s|\_V)=\\{p\mapsto s\_{\psi(p)}\\,:\\, p\in \psi^{-1}(V)\\},\\]所以$\rho\_{G}$是一个预层之间的态射。剩下的就是检验分解的成立，即对于任意的态射$u:G \to \psi\_\*F$，都可以找到唯一的态射$v:\psi^\*G \to F$使得分解$u:G\xrightarrow{\rho\_G} \psi\_\*\psi^\*G \xrightarrow{\psi\_\*v} \psi\_\*F$成立。

直接看我们想要什么，设$s\in G(U)$，那么我们已经定义了$\rho\_{G}(s)=s^+$，上面的分解即是要找一个$v$使得$\psi\_\*v(U)(s^+)=u(U)(s)$，所以下面我们定义$v$的时候要尽可能往这个式子上靠。

固定$U$是$X$的开子集，令$s\in \psi^\*G(U)$，由于$\psi^\*G$的构造，在每一点$p\in U$附近，我们都可以找到一个开子集$W\_p$, 一个$\psi(p)$附近的开子集$V\_p$使得$W\_p\subset \psi^{-1}(V\_p)\cap U$以及一个$t(p)\in G(V\_p)$使得$q\in W\_q$的时候$s\_q=t(p)\_{\psi(q)}$恒成立。记$t(p)^+:=\\{q\mapsto t(p)\_{\psi(q)}\\,:\\, q\in W\_p\\}\in \psi^\*G(W\_p)$，则最后一点即意味着$s|\_{W\_p}=t(p)^+$. 

现在我们定义$v(W\_p)(s|\_{W\_p})=\rho^{\psi^{-1}(V\_p)}\_{W\_p}\bigl(u(V\_p)(t(p))\bigr)$，其中$u(V\_p)(t(p))\in \psi\_\*F(V\_p)=F(\psi^{-1}(V\_p))$，而$\rho^{\psi^{-1}(V\_p)}\_{W\_p}$是$F$上的限制映射。后面将其简记为$\bigl(u(V\_p)(t(p))\bigr)|\_{W\_p}$.

遍历$p\in U$，我们就得到了一个开覆盖$\\{W\_p\\}\_{p\in U}$，由于$F$是一个层，于是可以把$\bigl(u(V\_p)(t(p))\bigr)|\_{W\_p}$拼成$U$上的一个截面$s'$，此时定义$v(U):s\mapsto s'$就得到了预层的态射$v:\psi^\*G \to F$的完整定义，显然这由$u$唯一确定。

证明的最后一步就是检验分解是否成立，十分琐碎的活，这里就不表了。<p align = right>Q.E.D.</p>

1.19 设$w:G\_1\to G\_2$是$Y$上的一个$K$-预层同态，如果$G\_2$和$G\_2$关于$\psi:X\to Y$的逆像是存在的，则复合$\rho\_{G\_2}\circ w:G\_1\to \psi\_\*\psi^\*G\_2$，由逆像的泛性质，我们可以找到一个态射$v:\psi^\*G\_1\to \psi^\*G\_2$来分解上面的复合态射，我们将其记做$\psi^\*(w)$，他将$Y$上的$K$-预层同态，变成了$X$上的$K$-层同态。这里不加验证，$\psi^\*(w\_1)\circ \psi^\*(w\_2)=\psi^\*(w\_1\circ w\_2)$，所以这是一个协变函子。

1.20 设$(X,\mathcal{O}\_X)$是一个赋环空间，我们称$F$是一个$\mathcal{O}\_X$-模层，如果对每一个开集$U$，$F(U)$都是一个$\mathcal{O}\_X(U)$-模，并且$F$和$\mathcal{O}\_X$的限制映射是相容的，即：设$V\subset U$是$X$的开子集，记$F$的限制映射为$\pi^U\_V$，相应地$\mathcal{O}\_X$的限制映射为$\rho^U\_V$，那么对于标量乘法而成的截面$a\cdot s\in F(U)$，则$\pi^U\_V(a\cdot s)=\rho^U\_V(a)\cdot \pi^U\_V(s)$.
类似地，我们定义什么叫$\mathcal{O}\_X$-代数层：环层$F$被称为$\mathcal{O}\_X$-代数层，如果他是一个$\mathcal{O}\_X$-模层。

我们知道$\mathcal{O}\_X(U)$自己作为$\mathcal{O}\_X(U)$-模的子模就是$\mathcal{O}\_X(U)$的理想，所以一个$\mathcal{O}\_X$的$\mathcal{O}\_X$-子模层，被称为$\mathcal{O}\_X$-理想层。

1.21 考虑任意的指标集$I$，以及一系列$\mathcal{O}\_X$-模层$\\{F\_i\\}\_{i\in I}$，直接用直积（即模范畴的product）的泛性质去检验层需要满足的泛性质\footnote{设$\\{U\_\alpha\\}$是$U$的一个开覆盖。对于每一个$i$，任意的同态$A\to \prod\_{i\in I}F\_i(U\_\alpha)$都可以复合典范投影得到同态$A\to F\_i(U\_\alpha)$，然后利用$F\_i$是个层，我们就得到了同态$A\to F\_i(U)$，最后利用product的泛性质就得到了同态$A\to \prod\_{i\in I}F\_i(U)$. 其他的同态的交换性不难检验。}，可以看到预层$U\mapsto \prod\_{i\in I}F\_i(U)$依然是一个环层。他被称作直积层，记做$\prod\_{i\in I}F\_i$.

而对于直和（即模范畴的coproduct），箭头反过来了导致预层$U\mapsto \bigoplus\_{i\in I}F\_i(U)$就不一定是一个层。所以我们定义直和层为上述预层的伴随层，记做$\bigoplus\_{i\in I}F\_i$. 对于有限指标集$I$，直和和直积等价，所以$U\mapsto \bigoplus\_{i\in I}F\_i(U)$此时就是一个层。

1.22 考虑一个$\mathcal{O}\_X$-模层同态$u:\mathcal{O}\_X\to F$，这个同态完全由截面$s=u(X)(1)\in F(X)$决定，其他的任意截面$t\in \mathcal{O}\_X(U)$，则$u(U)(t)=t\cdot (s|\_U)$.

类似地，考虑直和层$\bigoplus\_{i\in I}\mathcal{O}\_X=\mathcal{O}\_X^{(I)}$，对每一个$i\in I$，都有典范含入$h\_i:\mathcal{O}\_X\to \mathcal{O}\_X^{(I)}$. 设$F$是一个$\mathcal{O}\_X$-模层，而$u:\mathcal{O}\_X^{(I)}\to F$是一个$\mathcal{O}\_X$-模层同态，现在考虑复合$u\circ h\_i:\mathcal{O}\_X\to F$，他被截面$s\_i=(u\circ h\_i)(X)(1)$唯一确定，故$u$被$\\{s\_i\\}\_{i\in I}$唯一确定，对应着$u(U)\bigl(\bigoplus\_i a\_i\bigr)=\sum\_i a\_i\cdot (s\_i|\_U)$.

1.23 现在，我们来看所谓的有限生成模等概念如何推广到模层上面来。回忆一下，$R$-模$M$称被某个集合$E\subset M$生成，就是说，$M$是所有$s\in E$生成的自由模$R^{(E)}$的商模，即如下正和列成立$R^{(E)}\to M \to 0$. 所谓的有限生成，即是指存在一个有限集$E$生成$M$。

所以一个$\mathcal{O}\_X$-模层$F$被称作被截面$\\{s\_i\\}\_{i\in I}$生成，就是说由截面$\\{s\_i\\}\_{i\in I}$定义的同态$\mathcal{O}\_X^{(I)}\to F$是满射。类似地，$F$被称为有限生成$\mathcal{O}\_X$-模层，如果存在一族有限截面$\\{s\_i\\}\_{i\in I}$生成他。

1.24 设$u:F\to G$是$\mathcal{O}\_X$-模层同态，那么我们定义$U\to \ker(u(U))$, $U\to \mathrm{im}(u(U))$, $U\to \mathrm{coker}(u(U))$的伴随层为相应的$\mathcal{O}\_X$-模层$\ker(u)$, $\mathrm{im}(u)$以及$\mathrm{coker}(u)$. $u$被称为满的，就是说$\mathrm{im}(u)=G$，$u$被称为单的$\ker(u)=0$. 进而我们可以谈论层之间的正和列。

1.25 一个$\mathcal{O}\_X$-模层$F$被称作拟凝聚的，就是说，对任意的$x\in X$，存在他的一个开邻域$U$使得$F|\_U$同构于某个形如$\mathcal{O}\_X^{(I)}|\_U\to \mathcal{O}\_X^{(J)}|\_U$的同态的余核，此处$I$, $J$是任意的指标集。如果一个$\mathcal{O}\_X$-代数层作为$\mathcal{O}\_X$-模层是拟凝聚的，则他被称为拟凝聚$\mathcal{O}\_X$-代数层。或者说，在每一点附近都有一个开邻域$U$使得如下正和列成立\\[\mathcal{O}\_X^{(I)}|\_U\to \mathcal{O}\_X^{(J)}|\_U\to F|\_U\to 0.\\]考虑显然的正和列$0\to \mathcal{O}\_X^{(I)}\to \mathcal{O}\_X^{(I)} \to 0$，所以$\mathcal{O}\_X^{(I)}$本身就是拟凝聚$\mathcal{O}\_X$-模层。