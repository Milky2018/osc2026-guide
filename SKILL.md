---
name: osc2026-self-review
description: Pre-submission self-review Agent skill for local MoonBit国产开源生态大赛 OSC 2026 repositories. Use it to inspect the current local MoonBit project and produce a Chinese Markdown self-review report for contestants.
---

# OSC 2026 Self Review

Review a contestant's local repository before submission. Frame conclusions as pre-submission self-review findings.

## Scope

- Write the report in Chinese unless the user explicitly asks for another language.
- Review only the current local repository, or a local path explicitly provided by the user.
- Treat the proposal document as optional input. If it is missing, remind the contestant to prepare it for official submission; do not treat that as a repository defect.
- Use the bundled charter as the rule source: `references/2026 MoonBit 国产基础软件开源大赛章程.md`.
- Use the bundled charter instead of querying online charter pages.
- Inspect the repository directly and return a Markdown report.
- Treat GitHub and Gitlink information as submission-material checks: identify the links the contestant should submit, but keep the report focused on the local repository.
- Run `moon version --all` to check the MoonBit toolchain version and confirm it is at least `0.10.0`. If the command is unavailable or the version is too old, report it as a toolchain environment issue.
- Check whether `moonbitlang/skills` is installed, using the current tool's exposed skill list or local skill directories when available. If it is missing, suggest installing https://github.com/moonbitlang/skills for better MoonBit development assistance under optional environment suggestions.

## Contest Checks

- Judge MoonBit project configuration using files recognized by the current toolchain, such as `moon.mod` and `moon.pkg`, together with `moon check` / `moon test` results.
- Inspect the package namespace in `moon.mod`, for example the `username` in `username/package`. The template default `username` should be replaced with the contestant's GitHub account name, otherwise publishing to mooncakes.io may fail.
- Treat a current local branch with 10 or fewer commits as high risk. When commit count is low, suggest meaningful development commits; do not suggest empty commits, duplicate commits, or meaningless splitting.
- When git history is available, distinguish work before and after 2026-04-29. Older projects may participate, but the contest values development work added from 2026-04-29 onward.
- Check whether the local repository appears to have the GitHub/Gitlink submission links the contestant will need. If a remote is missing, present it as a submission-material reminder, not a remote validation failure.
- If a proposal document is provided, check that it explains the project name, summary, direction, target use case, core features, implementation plan, expected deliverables, and whether the project is original, a port, or based on another project. If it contains GitHub links, distinguish the contestant's project repository from reference/upstream repositories.
- Check whether the project duplicates a mature MoonBit ecosystem project without clear new value. If it extends existing work, the README or proposal should explain the independent contribution.
- Estimate MoonBit source scale when practical. Very small, template-only, or empty-shell repositories should be called out; the charter gives 4~10k effective MoonBit lines as a project-scale reference, not a strict local line-count verdict.
- Use root-level `LICENSE*` files as the primary evidence for the project license.
- For ports or projects based on another open source project, the README or a dedicated document should identify the original project name, link, license, and scope of reference.
- Focus on evidence that affects submission risk: MoonBit as the main implementation language, README usability, runnable examples, tests, `moon check` / `moon test`, and source/license notes for third-party code or test data.
- Include later-stage readiness suggestions when relevant: CI for check/build/test, at least one runnable example, tests for core paths, and readiness for publishing to mooncakes.io.
- Call out compliance risks for copied code, generated code, fixtures, sample files, private/commercial code, undisclosed upstream sources, or materials whose redistribution rights are unclear.
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
