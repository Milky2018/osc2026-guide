# osc2026-self-review

面向 MoonBit国产开源生态大赛 OSC 2026 选手的提交前自查 Agent skill。

它会根据当前本地仓库、MoonBit 项目状态和赛事章程，生成一份中文自查报告，帮助选手在正式提交前发现明显问题和人工复核风险。

## 使用方式

在参赛项目本地仓库中调用：

```text
使用 $osc2026-self-review 检查当前仓库是否适合提交到 MoonBit国产开源生态大赛。
```

如果已有申报书，可以同时提供路径：

```text
使用 $osc2026-self-review 检查当前仓库。申报书在 /path/to/proposal.pdf。
```

## 自查范围

- 当前本地仓库的项目内容、文档、许可证、提交记录、示例和测试。
- 当前 MoonBit 项目配置与 `moon check` / `moon test` 结果。
- 申报书与仓库内容的一致性；申报书不需要存放在仓库中。
- 第三方代码、测试数据、生成文件和移植来源的许可证说明风险。
- 本地是否已安装 [`moonbitlang/skills`](https://github.com/moonbitlang/skills)；未安装时会作为可选环境建议提示。

自查结果仅供提交前参考，不代表赛事官方审核结论。

## 安装

将仓库放入所用 agent 工具的 skill 目录。例如：

```bash
mkdir -p ~/.ai/skills
git clone https://github.com/Milky2018/osc2026-self-review-skill.git ~/.ai/skills/osc2026-self-review
```

如果 skill 列表没有自动刷新，请重启对应工具。
