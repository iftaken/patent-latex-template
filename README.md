# 专利申请技术交底书 LaTeX 模板

一个用于撰写专利申请技术交底书的 LaTeX 模板，基于 ctexbook 文档类，支持中文排版，标题使用楷体。

## 项目结构

```
.
├── main.tex              # 主文档文件
├── main.cls              # 文档类定义（含格式设置）
├── references.bib        # 参考文献数据库（可选）
├── figture/              # 图片文件夹
│   └── example.jpg       # 示例图片
├── font/                 # 字体文件夹（初始化时下载）
│   └── SIMKAI.TTF        # 楷体字体文件
├── init.sh               # 初始化脚本（下载字体）
├── .latexmkrc            # LaTeX 编译配置
└── README.md             # 本说明文件
```

## 专利申请技术交底书结构

根据标准格式，本模板包含以下章节：

1. **发明名称** - 发明创造的名称
2. **背景技术** - 描述现有技术及其缺点
3. **发明创造所要解决的技术问题及发明目的** - 阐述要解决的技术问题
4. **清楚完整的叙述发明创造的技术方案** - 详细描述技术实现方案
5. **与现有技术相比的优点** - 说明本发明的有益效果
6. **附图及说明** - 提供相关附图及其说明

## 快速开始

### 1. 初始化（首次使用）

```bash
bash init.sh
```

此脚本会下载所需的楷体字体文件到 `font/` 目录。

### 2. 编译文档

```bash
# 使用 Tectonic（推荐）
tectonic -X compile main.tex

# 或使用 latexmk
latexmk -pdf main.tex
```

### 3. 查看结果

编译成功后，会生成 `main.pdf` 文件。

## 修改内容

编辑 `main.tex` 文件，修改以下信息：

```latex
% 专利基本信息
\newcommand{\techcontact}{唐时康}              % 技术联系人
\newcommand{\techphone}{+86-13551098471}      % 技术联系电话
\newcommand\techemail{tang@example.com}       % 电子邮件
\newcommand{\patentname}{一种结合CNN迁移学习和SVDD的图像异常检测方法}  % 发明名称
```

然后在各章节中填写具体内容。

## 插入图片

将图片放入 `figture/` 目录，使用：

```latex
\begin{figure}[H]
    \centering
    \includegraphics[width=0.9\textwidth]{figture/your-image.png}
    \caption{图片说明}
    \label{fig:label}
\end{figure}
```

## 字体说明

- **正文**：宋体（SimSun）
- **标题**：楷体（KaiTi）
- **强调**：黑体（SimHei）

系统会自动检测楷体字体，优先使用系统安装的 `KaiTi` 或 `SimKai`，如果没有则尝试使用 `font/SIMKAI.TTF`。

## 依赖

- Tectonic 或 TeX Live（含 XeLaTeX）
- 系统字体：宋体、黑体、Times New Roman
- 可选字体：楷体（可通过 init.sh 下载）

## 许可证

本模板仅供学习和研究使用。

## 参考

- 格式参考：专利申请技术交底书标准格式
- 基于：ctexbook 文档类
