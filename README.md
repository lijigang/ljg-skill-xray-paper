# ljg-skill-xray-paper

论文 X 光机 — 一个 [Claude Code](https://docs.anthropic.com/en/docs/claude-code) Skill，只做两件事：论文说了什么 + 对我意味着什么。

## 功能

- 支持 arxiv ID、URL、PDF 路径等多种输入（自动转 `/html/` 格式抓取全文）
- **零术语规则**：承重概念必须场景化（3 级渐进），去掉技术名字仍能理解
- **一句话压缩**：电梯里跟外行朋友说的那句大白话 + 餐巾纸图
- **认知碰撞卡片**：ASCII art 直观展示论文洞见与个人认知的碰撞
- **多种碰撞形状**：分叉、张力、阈值、缺口、翻转——选跟碰撞匹配的空间结构
- **诚实原则**：delta ≈ 0 就说 0，不造空卡片
- 生成 Org-mode 格式报告（Denote 规范），自带模板

## 安装

```bash
claude plugin add lijigang/ljg-skill-xray-paper
```

## 使用

```
/ljg-xray-paper <arxiv ID、论文URL或PDF路径>
```

支持的输入格式：

| 输入 | 示例 |
|------|------|
| arxiv ID | `2601.01290` |
| arxiv URL | `https://arxiv.org/abs/2601.01290` |
| HTML URL | `https://arxiv.org/html/2601.01290` |
| PDF 路径 | `~/papers/example.pdf` |

## 输出示例

生成的 Org-mode 报告结构：

```org
* 论文说了什么

*问题*: ...
*视角*: ...
*结果*: 实验证明...。作者推测...

*一句话*: 大白话核心总结

#+begin_example
{餐巾纸图: 核心机制 ASCII art}
#+end_example

* 对我意味着什么

*可能改变我的*: 一句话指向具体改变

** 碰撞点标题

#+begin_example
{ASCII art 碰撞图}
#+end_example

金句级启发

** 开放问题

#+begin_example
{ASCII art}
#+end_example

一个尖锐的问题
```

## 约束体系

- **L0 通用约束**：Org-mode 语法、纯 ASCII art（禁 Unicode 绘图符号）、Denote 文件规范
- **L1 认知约束**：认知基线加载（soul.md + memory.md）、诚实原则、卡片质量标准

## 设计原则

- 只有两个部分，不加别的
- 承重概念必须场景化，普通术语一句话类比即可
- 卡片标准：遮住文字只看线条，仍能感受到结构关系
- 推测性结论做成"开放问题"碰撞卡片，写尖锐的问题而非温和的 checkbox

## License

MIT
