# osc2026-self-review

这是一个 Codex skill，用于帮助 MoonBit国产开源生态大赛 OSC 2026 选手在提交前自查当前本地仓库。

它刻意做得很薄：不替 Codex 写通用代码审查教程，只补充比赛规则、审核边界和容易误判的 MoonBit 现状。

## 适用场景

在参赛项目本地仓库中打开 Codex，然后输入：

```text
使用 $osc2026-self-review 检查当前仓库是否适合提交到 MoonBit国产开源生态大赛。
```

如果你有申报书，也可以附上路径：

```text
使用 $osc2026-self-review 检查当前仓库。申报书在 /path/to/proposal.pdf。
```

## 自查边界

- 只检查当前本地仓库。
- 不克隆、不 fetch、不比较 Gitlink/GitHub 远程仓库。
- 申报书不必放在仓库中；没有提供时只会提醒提交时需要准备。
- 默认用中文输出 Markdown 报告。
- 自查结果仅供提交前参考，不代表赛事官方审核结论。

## 安装

```bash
mkdir -p ~/.ai/skills
git clone https://github.com/Milky2018/osc2026-self-review-skill.git ~/.ai/skills/osc2026-self-review
```

如果 Codex 没有自动刷新 skill 列表，请重启 Codex。
