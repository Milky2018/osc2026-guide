---
name: osc2026-self-review
description: Help contestants self-review a local MoonBit国产开源生态大赛 OSC 2026 project repository before submission. Use when the user asks to check whether the current local repo is ready for the contest, wants a pre-submission review, or invokes $osc2026-self-review.
---

# OSC 2026 Self Review

Use this skill to review the current local repository from a contestant's point of view before submitting to MoonBit国产开源生态大赛. The goal is a practical Markdown or HTML report, not an official verdict.

## Rule Source

When contest rules, eligibility, submission requirements, review criteria, or terminology are unclear, access the official charter before answering:

- https://bxup9uklfcb.feishu.cn/wiki/Cv5owfd9xiT9Z5k6d8scJlV0n1a

Do not guess unclear contest rules from memory. If the charter cannot be accessed, say that clearly and separate verified local repository findings from unverified rule assumptions.

## Scope

- Review only the current local repository or an explicitly provided local path.
- Do not clone, fetch, or compare Gitlink and GitHub remotes.
- Do not require the proposal document to live in the repo. If no proposal is found or provided, mention it as a submission reminder, not a blocking repo issue.
- Do not write or run bundled scripts for the review. Inspect the repo directly with existing tools such as `git`, `rg`, `find`, `ls`, and `moon`.
- Do not emit JSON, YAML, or other fixed schemas unless the user explicitly asks for one.

## Review Workflow

1. Establish context:
   - Confirm the repo path with `pwd`.
   - Check `git status --short`, `git remote -v`, and recent commit history.
   - Identify whether the local repo appears to be the project intended for contest submission.

2. Inspect repository basics:
   - Root files: `README*`, `LICENSE*`, `moon.mod`, `moon.pkg`, `.gitignore`, documentation, examples, tests.
   - MoonBit layout: packages, `src/`, `test/`, examples, generated files, vendored code.
   - Commit count on the current branch. Flag repositories with 10 or fewer commits as high risk unless the user gives a different contest rule.

3. Check MoonBit build health:
   - Prefer `moon check` from the repo root when the `moon` command is available.
   - Run `moon test` when tests exist or when it is cheap enough for the repo.
   - Treat `moon.mod` and `moon.pkg` as current valid MoonBit project files. Do not require `moon.mod.json` or `moon.pkg.json`.
   - If the toolchain is missing or commands fail for environmental reasons, separate that from project defects.

4. Review submission readiness:
   - Confirm the project is visibly MoonBit-related and not just a wrapper around unrelated code.
   - Check whether the README explains what the project does, how to build/test/use it, and what is complete.
   - Check root-level license status. Project-level license review should focus on the repository root.
   - Look for copied third-party code, fixtures, test data, generated code, or vendored dependencies that may need license attribution.
   - Look for signs that important source files are missing, generated artifacts are committed without sources, or examples/tests cannot be reproduced.

5. Optional proposal review:
   - If the user provides a proposal document path, read it when it is Markdown or PDF.
   - If a proposal document is present in the repo, review it briefly for consistency with the repo.
   - If no proposal is available, add a reminder that the submitted proposal should contain the correct project repository information and match the local repo.

## Report Format

Return normal Markdown by default. Write in Chinese unless the user explicitly asks for another language. Keep the report readable for a contestant in China.

Use sections like:

- Overall assessment
- Must fix before submission
- Risks that may trigger manual review
- Suggested improvements
- Evidence checked

Write concrete findings with file paths, command outcomes, and short explanations. Avoid overstating certainty: this is a self-review, not the organizer's final review.

## Important Review Rules

- Missing proposal in the repo is not a rejection reason for self-review.
- This skill reviews the local repository state only; remote Gitlink/GitHub consistency is outside scope.
- Current MoonBit projects may use `moon.mod` and `moon.pkg`; absence of `moon.mod.json` is not a problem.
- Do not expose or repeat personal sensitive information if found in proposal documents or repo files.
- If the repo has a clear blocking problem, say so directly and explain how the contestant can fix it.
