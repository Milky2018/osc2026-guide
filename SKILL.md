---
name: osc2026-self-review
description: Pre-submission self-review Agent skill for local MoonBit国产开源生态大赛 OSC 2026 repositories. Use it to inspect the current local MoonBit project and produce a Chinese Markdown risk report for contestants.
---

# OSC 2026 Self Review

Review a contestant's local repository before submission. The result is advisory and is not an official contest review.

## Scope

- Write the report in Chinese unless the user explicitly asks for another language.
- Review only the current local repository, or a local path explicitly provided by the user.
- Treat the proposal document as optional input. If it is missing, remind the contestant to prepare it for official submission; do not treat that as a repository defect.
- Use the bundled charter as the rule source: `references/2026 MoonBit 国产基础软件开源大赛章程.md`.
- Use the bundled charter instead of querying online charter pages. Do not clone or sync remote repositories, and do not compare Gitlink/GitHub remote contents.
- Inspect the repository directly and return a Markdown report. Do not create helper scripts or require structured output.
- Run `moon version --all` to check the MoonBit toolchain version and confirm it is at least `0.10.0`. If the command is unavailable or the version is too old, report it as a toolchain environment issue.
- Check whether `moonbitlang/skills` is installed, using the current tool's exposed skill list or local skill directories when available. If it is missing, suggest installing https://github.com/moonbitlang/skills for better MoonBit development assistance. This is an optional environment suggestion, not a project risk.

## Contest Checks

- Judge MoonBit project configuration using files recognized by the current toolchain, such as `moon.mod` and `moon.pkg`, together with `moon check` / `moon test` results.
- Inspect the package namespace in `moon.mod`, for example the `username` in `username/package`. The template default `username` should be replaced with the contestant's GitHub account name, otherwise publishing to mooncakes.io may fail.
- Treat a current local branch with 10 or fewer commits as high risk. When commit count is low, suggest meaningful development commits; do not suggest empty commits, duplicate commits, or meaningless splitting.
- Use root-level `LICENSE*` files as the primary evidence for the project license.
- For ports or projects based on another open source project, the README or a dedicated document should identify the original project name, link, license, and scope of reference.
- Focus on evidence that affects submission risk: MoonBit as the main implementation language, README usability, runnable examples, tests, `moon check` / `moon test`, and source/license notes for third-party code or test data.
- Keep toolchain environment issues separate from project code issues.
- If personal sensitive information is found, mention only the risk and file location; do not repeat the sensitive content.

## Report

The report should help the contestant decide what to fix before submission. Use these sections when appropriate:

- 总体判断
- 提交前需要处理的问题
- 需要进一步确认的问题
- 建议改进
- 已检查的证据
- 可选环境建议

Separate facts, inferences, and uncertain rule interpretations. Cite local commands or files for evidence-backed conclusions. Present items that cannot be verified locally as points to clarify, not final rulings.
