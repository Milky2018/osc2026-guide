# osc2026-self-review

这是一个 Codex skill，用于帮助选手在提交前自查本地的 MoonBit国产开源生态大赛 OSC 2026 参赛仓库。

这个 skill 面向提交前自查，不代表赛事组织方的正式审核结论。

## 检查内容

- 当前本地仓库是否像是准备提交的参赛项目。
- 仓库基础状态，包括 README、根目录许可证、提交历史、源码布局、测试和示例。
- MoonBit 项目健康度，包括当前有效的 `moon.mod`、`moon.pkg` 等项目文件。
- 可能触发人工复核的风险，例如第三方代码拷贝、许可证归属不清、源码缺失、文档不完整等。
- 当选手提供 Markdown 或 PDF 申报书时，检查申报书与仓库内容是否一致。

## 不做什么

- 不要求申报书必须放在仓库中。
- 不克隆、不 fetch、不比较 Gitlink 和 GitHub 远程仓库。
- 默认不输出结构化 JSON。
- 不替代赛事官方审核。

## 安装

把这个仓库克隆到 Codex skills 目录：

```bash
mkdir -p ~/.ai/skills
git clone https://github.com/Milky2018/osc2026-self-review-skill.git ~/.ai/skills/osc2026-self-review
```

如果 Codex 没有自动刷新 skill 列表，请重启 Codex。

## 使用方式

在本地参赛项目仓库中打开 Codex，然后输入：

```text
使用 $osc2026-self-review 用中文检查当前本地仓库是否适合提交到 MoonBit国产开源生态大赛。
```

如果你也有申报书，可以附上申报书路径：

```text
使用 $osc2026-self-review 检查当前仓库。申报书在 /path/to/proposal.pdf。
```

默认自查报告使用中文输出。
