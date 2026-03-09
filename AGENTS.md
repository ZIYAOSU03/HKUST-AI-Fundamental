# AGENTS.md

## Cursor Cloud specific instructions

This is a Python/PyTorch Jupyter Notebook project (MAIE5102 university assignment). All code lives in `assignment1_maie5102_release/assignment1.ipynb`.

### Services

| Service | How to start |
|---|---|
| Jupyter Lab | `cd assignment1_maie5102_release && jupyter lab --ip=0.0.0.0 --port=8888 --no-browser --ServerApp.token='' --ServerApp.password=''` |

### Dependencies

Python packages: `torch`, `numpy`, `matplotlib`, `jupyter` (installed via pip).

### Running the notebook

- The notebook loads CSV data files from the same directory (`2_cluster_*.csv`, `wine_*.csv`). The working directory must be `assignment1_maie5102_release/` when starting Jupyter.
- No GPU required — the code runs on CPU. CUDA references in the code are for optional GPU acceleration.
- There are no lint checks, automated tests, or build steps — this is a single Jupyter notebook assignment.

### Gotchas

- `~/.local/bin` must be on `PATH` for `jupyter` CLI to work (pip installs scripts there).

## HKUST 作业 PDF 格式规范

所有港科大 (HKUST) 相关的作业、报告 PDF 必须使用以下 XeLaTeX 模板。模板源文件参考 `assignment1_maie5102_release/21272577_assignment1.tex`。

### 编译器与字体
- 使用 **XeLaTeX**（不是 pdflatex），因为依赖 `unicode-math`, `setmainfont`
- 主字体：`TeX Gyre Termes`（衬线），数学字体：`TeX Gyre Termes Math`
- 编译命令：`xelatex -interaction=nonstopmode filename.tex`（运行两次处理引用）

### 文档类型与页面设置
- `\documentclass[10pt, a4paper]{article}`
- 页边距：top=3cm, bottom=4cm, left=3.5cm, right=3.5cm

### 页眉页脚（fancyhdr 包）
- **页眉左侧**：`\today`（当前日期）
- **页眉右侧**：HKUST logo 图片（`logo-hkust.png`，宽度 2.5cm）
- **headheight**：35pt，**headsep**：1.2em
- **页脚**：居中页码（`\cfoot{\small\thepage}`）
- 封面使用 `titlepage` 环境，自动无页眉页脚

### 封面页（titlepage 环境）
- `\vspace*{3cm}` 起始
- "Assignment X"（`\Huge\textbf`）
- "Q1 & Q2"（`\huge`）
- 学生信息（`\Large\textbf`），格式如 "Su Ziyao (21272577)"
- 底部：课程名 + HKUST logo（宽度 0.4\textwidth）+ 日期

### Problem / Solution 环境
- 使用 `mdframed` 包的 `mdtheorem` 定义 Problem 环境
- 样式：黑色 1pt 边框，灰色标题背景（`gray!20`），标题分隔线
- Solution 环境：以 "**Solution.**" 开头，末尾带 QED 符号（`\qed`）

### 代码格式（listings 包）
- 浅米色背景（`rgb{0.95,0.95,0.92}`）
- 语法高亮：绿色注释、品红色关键字、紫色字符串
- 左侧行号，等宽字体 `\ttfamily\footnotesize`

### 表格、图片、数学公式
- 表格：`booktabs` 包三线表
- 图片：`\includegraphics` + `float[H]`，并排用 `minipage`
- 数学：`amsmath`, `amssymb`, `unicode-math`

### 行间距
- `\renewcommand{\baselinestretch}{1.25}`

### 自定义命令
- `\course{课程名}`, `\hwnumber{作业编号}`, `\Information{学生信息}`
- 各种数学快捷命令（`\Z`, `\R`, `\Q`, `\NN`, `\PP` 等）

### 必须确保的文件
- `logo-hkust.png`：HKUST 校徽图片，与 .tex 文件同目录

### 系统依赖
```
sudo apt-get install texlive-xetex texlive-latex-extra texlive-fonts-extra fonts-texgyre texlive-science
```
