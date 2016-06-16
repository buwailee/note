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
- field
	中文，小东西，将来会整理
- algtopo
	英文，进行中
- Hartshorne
	中文，主要是第一章的部分内容，将来会补充。第二章开始，代数几何主要参考书多了，所以可能不会补充
- qft
	中文，主要是Weinberg第一卷，（可能的）进行中
- 黑历史
	中文，黑历史，基本已停止

--------------

关于LaTeX的编译，如果什么都不懂就使用XeLaTeX，在terminal里面输入`XeLaTeX haha.tex`就可以了，haha为你tex的文件名。同时，也可以使用李阿玲的ApTeX进行编译。

--------------

关于noteheader宏包，我笔记的自用宏包，默认载入`amssymb`, `amsfonts`, `amsmath`, `amsthm`, `bm`, `mathrsfs`, `xy`这些数学用宏包，以及`geometry`,`tikz`, `titletoc`, `fancyhdr`负责版式设计等。

目前提供六个选项：

- `book` 选项：这个选项主要负责存在chapter计数器的情况。
- `article` 选项：这个选项主要负责最大计数器为section的情况。此外，版式不再同book选项奇数页与偶数页标题不同。默认选项。
- `zh` 选项：负责section开始后第一行不缩进，符合中文习惯，实现方式同`indentfirst`宏包。
- `en` 选项：section开始后第一行不缩进，符合英文习惯。默认选项。
- `xetex` 选项：当使用XeLaTeX编译的时候使用。默认选项
- `aptex` 选项：当使用ApTeX编译的时候使用。

关于`xetex`选项和`aptex`的区别在于版式设计，在我的机器上，ApTeX（Version 3.14159265，编译平台Arch Linux x86-64 gcc 6.1.1）编译出来的文件整体向左上偏移，所以我就用命令拉了回来，如果在你的机器上没有该问题，则可以自行修改noteheader宏包里面的`aptex`选项。

noteheader宏包不负责公式环境的具体设置（尽管默认载入`amsthm`宏包）。普通的公式环境可以直接新建具体公式环境，对于对于ega式的风格，可以参考`manifold.tex`，主要思路就是新建了一个计数器来负责重要段落，然后其他的公式环境由他实现。

该宏包也不默认超链接以及目录的使用，需要的可以使用`hyperref`宏包。

--------------

关于egastyle宏包，在他之前要使用`amsmath`，我个人建议是直接使用`noteheader`。