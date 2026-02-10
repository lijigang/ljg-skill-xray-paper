# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个 **Claude Code Skill** 项目：**ljg-xray-paper**（论文X光机）。该项目不包含传统意义上的源代码，而是一个用于学术论文深度分析的 Claude Code Skill。

## 核心功能

该 Skill 用于解构学术论文，穿透学术黑话，还原作者最底层的逻辑模型。主要功能包括：

1. **输入支持**：PDF 路径、文本内容或论文链接
2. **认知提取算法**：去噪 → 提取 → 批判
3. **五维分析框架**：
   - 核心痛点：论文试图解决的具体困难问题
   - 解题机制：作者的"灵光一闪"想法
   - 创新增量：相比 SOTA 的具体提升
   - 批判性边界：隐形假设和未解之谜
   - 餐巾纸公式：一句话浓缩核心
4. **输出格式**：根据系统环境自动选择 org-mode 或 markdown 格式报告，包含 ASCII 逻辑流程图

## 项目结构

```
ljg-xray-paper/
├── README.md          # 项目说明文档
├── SKILL.md           # Claude Code Skill 配置文件
├── CLAUDE.md          # Claude Code 操作指南（本文件）
└── .git/              # Git 版本控制目录
```

## Skill 执行流程

当用户调用 `/ljg-xray-paper` 命令时，Skill 按以下步骤执行：

1. **接收论文输入**：等待用户提供论文（PDF 路径、文本内容或论文链接）
2. **执行认知提取算法**：
   - 去噪：忽略背景介绍、客套话和通用知识
   - 提取：锁定论文的核心贡献和关键操作
   - 批判：寻找逻辑漏洞、隐形假设和未解问题
3. **结构化分析**：按五维框架组织分析结果
4. **生成逻辑结构图**：使用纯 ASCII 字符绘制论文核心逻辑流程
5. **检查系统环境**：检查系统中是否安装 emacs，决定输出格式
6. **生成报告**：根据环境检查结果，按相应模板生成 org-mode 或 markdown 格式文件
7. **保存并打开**：保存到 `~/Documents/notes/` 目录并打开文件

## 输出文件规范

生成的报告文件遵循以下命名规范：
- 文件名格式：`{时间戳}--xray-{简短标题}__read.{扩展名}`
  - 扩展名根据系统环境自动选择：
    - 如果系统安装了 emacs：使用 `.org` 扩展名（org-mode 格式）
    - 如果系统未安装 emacs：使用 `.md` 扩展名（markdown 格式）
- 示例（org 格式）：`20260207T171500--xray-dflash-block-diffusion__read.org`
- 示例（markdown 格式）：`20260207T171500--xray-dflash-block-diffusion__read.md`
- 保存路径：`~/Documents/notes/`

时间戳通过 `date +%Y%m%dT%H%M%S` 命令生成。

## 报告模板

报告根据系统环境自动选择模板格式：

### Org-mode 模板（当系统安装 emacs 时）
使用 org-mode 格式，包含以下章节：
- `NAPKIN FORMULA`：餐巾纸公式和解释
- `PROBLEM`：痛点定义和前人类境
- `INSIGHT`：核心直觉和关键步骤
- `DELTA`：与 SOTA 的对比和新拼图
- `CRITIQUE`：隐形假设和未解之谜
- `LOGIC FLOW`：纯 ASCII 逻辑结构图
- `NAPKIN SKETCH`：ASCII 餐巾纸图

### Markdown 模板（当系统未安装 emacs 时）
使用 markdown 格式，包含相同的章节结构，但使用 markdown 语法（# 标题，- 列表，``` 代码块等）。

## 输出质量标准

1. **高密度信息**：使用列表和关键词，不写长段落
2. **直白语言**：用最简单的语言解释复杂概念
3. **批判性思维**：必须指出至少一个隐形假设或未解问题
4. **纯 ASCII 图表**：仅使用基础 ASCII 符号（+, -, |, >, <, /, \, *, =, .），不使用 Unicode
5. **餐巾纸图/公式**：必须一眼能懂，简洁明了

## 开发说明

这是一个纯配置型 Skill，不需要编译、构建或测试。所有逻辑都定义在 `SKILL.md` 文件的提示词中。要修改 Skill 的行为，只需编辑 `SKILL.md` 文件。

## 使用示例

用户在 Claude Code 中输入：
```
/ljg-xray-paper /path/to/paper.pdf
```
或
```
/ljg-xray-paper https://arxiv.org/abs/xxxx.xxxxx
```

Skill 将分析论文并生成结构化报告。