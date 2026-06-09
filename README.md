# osc2026-self-review

Codex skill for contestants to self-review a local MoonBit国产开源生态大赛 OSC 2026 repository before submission.

This skill is intended for pre-submission self-checks. It is not an official review result from the contest organizers.

## What It Checks

- Whether the current local repository looks like the intended contest project.
- Basic repository readiness, including README, root license, commit history, source layout, tests, and examples.
- MoonBit project health with current project files such as `moon.mod` and `moon.pkg`.
- Potential manual-review risks such as copied third-party code, unclear attribution, missing sources, or incomplete documentation.
- Optional proposal consistency when the contestant provides a Markdown or PDF proposal.

## What It Does Not Do

- It does not require the proposal document to be stored in the repository.
- It does not clone, fetch, or compare Gitlink and GitHub remotes.
- It does not emit structured JSON by default.
- It does not replace the official contest review.

## Install

Clone this repository into your Codex skills directory:

```bash
mkdir -p ~/.ai/skills
git clone https://github.com/Milky2018/osc2026-self-review-skill.git ~/.ai/skills/osc2026-self-review
```

Then restart Codex if the skill list does not refresh automatically.

## Usage

Open Codex in your local project repository and ask:

```text
使用 $osc2026-self-review 用中文检查当前本地仓库是否适合提交到 MoonBit国产开源生态大赛。
```

If you also have a proposal document, include its path:

```text
使用 $osc2026-self-review 检查当前仓库。申报书在 /path/to/proposal.pdf。
```

The default report language is Chinese.
