# 南京大学高能物理实验组毕业论文LaTex表格格式
《学位论文编写规则》推荐使用三线表，三线表包顶线、底线和表头线，允许添加适量的辅助线。
## 软件环境安装
### 搭建本地环境
推荐使用南京大学的毕业论文格式模板，并且使用最新版本，下载地址为：<https://ctan.org/pkg/njuthesis>。为了尽可能避免宏包的错误，请重新安装最新版本的texlive，下载地址为：<https://tug.org/texlive/>。推荐的LaTex本地编辑器为TexStudio，下载地址为：<https://texstudio.sourceforge.net/>。
### 使用南京大学的线上环境
推荐使用南京大学的线上LaTex编辑器，网址为：<https://tex.nju.edu.cn/>，在模板中找到南京大学毕业论文模板。

## 使用宏包
使用booktabs宏包绘制表格的顶线、底线和表头线分别使用\toprule, \bottomrule和\midrule命令绘制。
```latex
\usepackage{booktabs}
```

## 示例
### 对于长度小于页面宽度的表格
使用了table和tabular环境绘制表格，顶线、底线和表头线分别使用\toprule, \bottomrule和\midrule命令绘制。
```latex
\begin{table}[htb]
	\centering
	\caption{MUX64 64-1功能逻辑真值表，输出由内部的6-bit解码器决定。}
	\label{tb:MUX64_truth_table}
	\centering
	\begin{tabular}{cccccccc}
		\toprule
		\text{输入通道} &\text{s5}  &\text{s4}  &\text{s3}  &\text{s2}  &\text{s1}  &\text{s0}  &\text{输出}  \\
		\midrule
		A0 & 0 & 0 & 0 & 0 & 0 & 0 & A0 \\
		A1 & 0 & 0 & 0 & 0 & 0 & 1 & A1 \\
		A2 & 0 & 0 & 0 & 0 & 1 & 0 & A2 \\
		A3 & 0 & 0 & 0 & 0 & 1 & 1 & A3 \\
		... & ... & ... & ... & ... & ... & ... & ... \\
		... & ... & ... & ... & ... & ... & ... & ... \\
		A63 & 1 & 1 & 1 & 1 & 1 & 1 & A63 \\
		\bottomrule
	\end{tabular}
\end{table}
```

### 对于长度大于页面宽度的表格
使用\resizebox{\textwidth}{!}{}环境将tabular环境包含在中间，表格将缩放到适合单页显示。
```latex
\begin{table}[htb]
	\centering
	\caption{PEB所需芯片数目汇总}
	\label{tb:PEB_chips_numbers}
	\centering
	\resizebox{\textwidth}{!}{
		\begin{tabular}{cccccc}
			\toprule
			\text{外围电路板}&\text{探测器模块数}  &\text{示例}  &\text{示例}  &\text{示例}  &\text{MUX64}  \\
			\midrule
			示例 &155 &112 &19	&146 &19	\\
			\bottomrule
		\end{tabular}
	}
\end{table}
```