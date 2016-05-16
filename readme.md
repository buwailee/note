*my note*

**我的笔记**

--------------

进度：

- Electrodynamics
	中文，大半，已经不想写了
- series
	中文，大半，将来不会写
- vector analysis
	英文，矢量分析公示表，基本不会有大的改动。
- manifold
	中文，进行中
- field,  sheaf, repfunctor
	中英文，小东西，将来会整理
- algtopo
	英文，进行中
- Hartshorne
	中文，主要是第一章的部分内容，将来会补充。第二章开始，代数几何主要参考书多了，所以可能不会补充
- qft
	中文，主要是Weinberg第一卷，进行中
- 黑历史
	中文，黑历史，已停止

--------------

关于noteheader宏包，我笔记的自用宏包，默认载入`amssymb`, `amsfonts`, `amsmath`, `amsthm`, `bm`, `mathrsfs`, `xy`这些数学用宏包，以及`geometry`,`tikz`, `titletoc`, `fancyhdr`负责版式设计等。

目前提供四个选项：

- `book` 选项：这个选项主要负责存在chapter计数器的情况。默认选项。
- `article` 选项：这个选项主要负责最大计数器为section的情况。
- `zh` 选项：负责section开始后第一行不缩进，符合中文习惯，实现方式同`indentfirst`宏包。默认选项。
- `en` 选项：section开始后第一行不缩进，符合英文习惯。

该宏包不负责公式环境的具体设置（尽管默认载入`amsthm`宏包）。普通的公式环境可以直接新建具体公式环境，对于对于ega式的风格，可以参考`manifold.tex`，主要思路就是新建了一个计数器来负责重要段落，然后其他的公式环境由他实现。

该宏包也不默认超链接以及目录的使用，需要的可以使用`hyperref`宏包。