*my note*

**我的笔记**

--------------

进度：

- Electrodynamics
	中文，大半，已经不想写了
- series
	中文，大半，将来不会写
- vector analysis
	英文，矢量分析公式表，基本不会有大的改动。
- manifold
	中文，进行中
- lie_algebra
	中文，进行中
- algebra
	中/英文，以前写的各种关于代数的小东西整理一下
- ag
	Hartshorne第一章，主要是中文。第二章开始，以英文为主，参考文本有Hartshorne, ega等。
- qft
	中文，主要是Weinberg第一卷，（可能的）进行中
- bose
	一维费米系统玻色化的相关内容，（可能的）进行中
- 黑历史
	中/英文，黑历史，基本已停止

--------------

关于LaTeX的编译，如果什么都不懂就使用XeLaTeX，在terminal里面输入`xelateX haha.tex`就可以了，haha为你tex的文件名。速度上建议使用李阿玲的[ApTeX](https://github.com/clerkma/ptex-ng)进行编译（按个人经验，尽可能使用他提供的fmt文件，见[ptex-ng-dist](https://github.com/clerkma/ptex-ng-dist)）。

--------------

关于`noteheader`宏包，我笔记的自用宏包，默认载入`amssymb`, `amsfonts`, `amsmath`, `amsthm`, `bm`, `mathrsfs`, `xy`这些数学用宏包，以及`geometry`,`tikz`, `titletoc`, `fancyhdr`负责版式设计等。

目前提供六个选项：

- `zh` 选项：负责section开始后第一行不缩进，符合中文习惯，实现方式同`indentfirst`宏包。
- `en` 选项：section开始后第一行不缩进，符合英文习惯。默认选项。
- `a4paper` 选项：正如其名。默认选项。
- `b5paper` 选项：正如其名。

`noteheader`宏包不负责公式环境的具体设置（尽管默认载入`amsthm`宏包）。普通的公式环境可以直接新建具体公式环境，对于ega式的风格，可以使用`egastyle`宏包。

该宏包也不默认超链接以及目录的使用，需要的可以使用`hyperref`宏包。

--------------

关于`egastyle`宏包，在他之前要使用`amsmath`，我个人建议是直接使用`noteheader`。具体效果可以参看`manifold.pdf`，实现的主要思路就是新建了一个计数器来负责重要段落，然后其他的公式环境由他实现。