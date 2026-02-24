# ljg-skill-xray-paper

论文 X 光机 — 一个 [Claude Code](https://docs.anthropic.com/en/docs/claude-code) Skill，只做两件事：论文说了什么 + 对我意味着什么。

## 功能

- 支持 arxiv ID、URL、PDF 路径等多种输入
- 零术语规则：承重概念必须场景化，去掉技术名字仍能理解
- 认知卡片：ASCII art 直观展示论文洞见与个人认知的碰撞
- 诚实原则：delta = 0 就说 0，不造空卡片
- 生成 Org-mode 格式报告，自带模板

## 安装

```bash
/plugin marketplace add lijigang/ljg-skill-xray-paper
/plugin install ljg-xray-paper
```

## 使用

在 Claude Code 中输入：

```
/ljg-xray-paper <arxiv ID、论文URL或PDF路径>
```

## 输出示例

生成的 Org-mode 报告包含：

- **论文说了什么** — 问题、视角、结果（人话），配餐巾纸图
- **对我意味着什么** — 认知卡片（ASCII art），每张附金句级启发
- **追问** — 推测性 claim 或锐利问题（有则写，无则省）

## License

MIT
