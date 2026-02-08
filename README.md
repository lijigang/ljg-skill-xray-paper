# ljg-skill-xray-paper

论文X光机 (Paper X-Ray Scanner) — 一个 [Claude Code](https://docs.anthropic.com/en/docs/claude-code) Skill，解构学术论文，穿透学术黑话，还原作者最底层的逻辑模型。

## 功能

- 支持 PDF 路径、文本内容或论文链接输入
- 认知提取算法：去噪 → 提取 → 批判
- 五维分析：核心痛点、解题机制、创新增量、批判性边界、餐巾纸公式
- 生成 Org-mode 格式报告，含 ASCII 逻辑流程图

## 安装

```bash
git clone https://github.com/lijigang/ljg-skill-xray-paper.git ~/.claude/skills/ljg-xray-paper
```

## 使用

在 Claude Code 中输入：

```
/ljg-xray-paper <论文PDF路径、URL或粘贴内容>
```

## 输出示例

生成的 Org-mode 报告包含：

- **NAPKIN FORMULA** — 餐巾纸公式，一句话浓缩核心
- **PROBLEM** — 痛点定义与前人困境
- **INSIGHT** — 作者的灵光一闪
- **DELTA** — 相比 SOTA 的创新增量
- **CRITIQUE** — 隐形假设与未解之谜
- **LOGIC FLOW** — ASCII 逻辑结构图
- **NAPKIN SKETCH** — ASCII 餐巾纸图

## License

MIT
