# write-academic-paper

（！！！！用这个发不了SCI的，只能发一个小普刊。想法SCI的建议看看nature-skill ）
一个用于中文学术论文写作的 Codex Skill。它可以帮助你按章节起草、修改、诊断和润色论文内容，适合摘要、引言、相关工作、方法、实验结果、讨论、结论等部分。


这个 skill 的核心目标不是替用户编造论文，而是把用户提供的研究主题、方法、数据集、实验结果和创新点整理成更规范的中文学术表达。

## 适合做什么

- 写中文期刊论文或研究生课程论文的摘要、引言、方法、实验、结论。
- 根据研究内容生成论文提纲。
- 修改已有段落，使逻辑更清楚、语气更学术。
- 从审稿人视角检查论文是否存在逻辑断裂、证据不足或过度表述。
- 将零散研究信息整理成规范论文段落。

## 不适合做什么

- 编造实验数据、准确率、消融实验结果或参考文献。
- 在没有研究内容的情况下直接生成完整论文。
- 替代真实实验、真实引用和学校/期刊格式审查。

如果缺少关键信息，skill 会使用 `[数据集名称]`、`[核心指标]`、`[提升幅度]` 等占位符，或者提示你需要补充哪些内容。

## Codex 安装方式

### Windows

打开 PowerShell，运行：

```powershell
git clone https://github.com/Mapengfeixx/write-academic-paper.git "$env:USERPROFILE\.codex\skills\write-academic-paper"
```

然后重启 Codex，让新 skill 生效。

### macOS / Linux

打开终端，运行：

```bash
git clone https://github.com/Mapengfeixx/write-academic-paper.git ~/.codex/skills/write-academic-paper
```

然后重启 Codex，让新 skill 生效。

### 已经下载过，想更新

进入 skill 目录后拉取最新版本：

```bash
git pull
```

然后重启 Codex。

## Codex 使用方式

在 Codex 中直接用 `$write-academic-paper` 调用：

```text
Use $write-academic-paper 帮我写一段中文期刊论文摘要。
```

更推荐提供完整研究信息：

```text
Use $write-academic-paper 帮我写摘要。

研究主题：基于 VGG16 的 HAM10000 皮肤病变分类
研究问题：皮肤病变图像类别多、类间差异小、部分类别样本不均衡
方法：使用迁移学习的 VGG16，并加入数据增强和全连接层微调
数据集：HAM10000
实验结果：准确率为 xx%，相比 baseline 提升 xx%
想要风格：中文期刊论文风格
```

## 常用提示词

### 写摘要

```text
Use $write-academic-paper 帮我写摘要。

研究主题：
研究问题：
现有方法不足：
本文方法：
数据集：
实验结果：
论文风格：中文期刊论文风格
```

### 写引言

```text
Use $write-academic-paper 帮我写引言。

研究背景：
研究意义：
已有方法：
现有不足：
本文方法：
主要贡献：
```

### 写相关工作

```text
Use $write-academic-paper 帮我写相关工作。

研究方向：
已有方法分类：
每类方法的代表性思路：
现有研究不足：
本文与已有工作的区别：
```

### 写方法部分

```text
Use $write-academic-paper 帮我写方法部分。

研究任务：
输入数据：
输出结果：
整体框架：
核心模块：
关键改进：
为什么这样设计：
```

### 写实验结果

```text
Use $write-academic-paper 帮我写实验结果部分。

数据集：
数据划分：
评价指标：
对比方法：
实验结果表：
消融实验：
参数或复杂度分析：
```

### 修改已有段落

```text
Use $write-academic-paper 帮我修改下面这段论文内容，使其更符合中文期刊论文风格，并指出逻辑问题。

原文：
这里粘贴你的段落。
```

### 审稿人视角检查

```text
Use $write-academic-paper 从审稿人视角检查这段论文内容，重点看研究必要性、创新性、实验支撑和结论是否过度。

内容：
这里粘贴你的段落。
```

## Claude 使用方式

这个仓库是 Codex Skill 格式，不是 Claude 原生格式。Claude 用户可以用下面两种方式参考使用。

### 方式一：放入 Claude Project 知识库

1. 新建一个 Claude Project。
2. 将 `SKILL.md` 和 `references/section-guides.md` 上传到 Project knowledge。
3. 在 Project instructions 中加入：

```text
请按照 write-academic-paper 的规则帮助我进行中文学术论文写作。写作时不要编造实验数据、参考文献或结论；如果信息不足，请使用占位符或询问我需要补充的信息。
```

之后可以直接问：

```text
帮我根据以下研究信息写一段中文期刊论文摘要：

研究主题：
研究问题：
方法：
数据集：
实验结果：
```

### 方式二：直接粘贴作为提示词

如果不使用 Project，也可以把 `SKILL.md` 的内容粘贴给 Claude，然后继续输入论文写作任务。

示例：

```text
请按照我提供的 write-academic-paper 规则工作。现在帮我写引言。

研究背景：
现有方法：
不足：
本文方法：
主要贡献：
```

## 文件结构

```text
write-academic-paper/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    └── section-guides.md
```

## 写作原则

- 先明确论文属于哪个章节，再选择对应结构。
- 所有结论必须由用户提供的方法、实验或文献支撑。
- 摘要强调“背景-问题-方法-结果-结论”。
- 引言强调“研究必要性”。
- 相关工作强调“分类梳理”和“本文定位”。
- 方法部分强调“本文怎么做”。
- 实验结果强调“方法是否有效”。
- 讨论强调“结果说明什么”。
- 结论强调“最终得出什么结论”。

