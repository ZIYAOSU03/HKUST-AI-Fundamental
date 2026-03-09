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

所有港科大 (HKUST) 相关的作业、报告 PDF 必须遵循以下 LaTeX 格式：

### 文档类型与页面设置
- `\documentclass[11pt,a4paper]{article}`
- 页边距：1 inch（约 2.54cm），使用 `geometry` 包
- 字体：Computer Modern（LaTeX 默认衬线字体）

### 页眉页脚（fancyhdr 包）
- **页眉左侧**：课程编号（如 "MAIE5102"），普通字体
- **页眉右侧**：HKUST 校名文字 "THE HONG KONG / UNIVERSITY OF SCIENCE / AND TECHNOLOGY"（三行，小号加粗）；如有 HKUST 校徽图片可替换为 logo
- **页眉分隔线**：无（`\renewcommand{\headrulewidth}{0pt}`）
- **页脚**：居中页码，无其他内容
- **首页（封面）**：不显示页眉页脚（`\thispagestyle{empty}`）

### 封面页
- 垂直居中偏上（`\vspace*{8cm}`）
- 课程编号（Large）
- 课程名称（large）
- "Homework Assignment X"（Large bold）
- "Student ID: XXXXXXXX"（large）
- 全部水平居中

### 标题层级
- 一级标题：`\section{}`，编号如 "1 Introduction"，14-16pt 加粗
- 二级标题：`\subsection{}`，编号如 "1.1 xxx"，12-13pt 加粗
- 三级标题：`\subsubsection{}`，编号如 "1.1.1 xxx"

### 表格格式
- 使用 `booktabs` 包（`\toprule`, `\midrule`, `\bottomrule`）
- 表格标题在表格上方，居中，格式 "Table X: 描述"
- 使用 `\centering` 和 `float` 环境 `[H]`

### 图片格式
- 使用 `\includegraphics` 插入
- 标题在图片下方，格式 "Figure X: 描述"
- 使用 `float` 环境 `[H]` 固定位置
- 并排图片使用 `minipage` 环境

### 代码格式
- 等宽字体（Courier / Computer Modern Typewriter）
- 缩进显示，无背景色
- 使用 `verbatim` 环境或 `listings` 包

### 数学公式
- 行内公式用 `$...$`
- 独立公式用 `\[...\]` 或 `equation` 环境
- 使用 `amsmath`, `amssymb` 包

### 编译命令
```
pdflatex -interaction=nonstopmode filename.tex
pdflatex -interaction=nonstopmode filename.tex  # 第二次编译处理引用
```

### 所需 LaTeX 包
`geometry`, `fancyhdr`, `graphicx`, `amsmath`, `amssymb`, `booktabs`, `float`, `caption`, `hyperref`, `enumitem`
