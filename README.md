# osc2026-self-review

面向 MoonBit国产开源生态大赛 OSC 2026 选手的提交前自查 Agent skill。

## 安装

推荐使用 `skills` CLI 安装：

```bash
npx skills add Milky2018/osc2026-self-review-skill
```

也可以手动克隆到本地 Agent skill 目录：

```bash
mkdir -p ~/.agent/skills
git clone https://github.com/Milky2018/osc2026-self-review-skill.git ~/.agent/skills/osc2026-self-review
```

如果 skill 列表没有自动刷新，请重启对应工具。

## 使用

在参赛项目本地仓库中调用：

```text
使用 $osc2026-self-review 检查当前仓库是否适合提交到 MoonBit国产开源生态大赛。
```

如果已有申报书，可以同时提供路径：

```text
使用 $osc2026-self-review 检查当前仓库。申报书在 /path/to/proposal.pdf。
```
