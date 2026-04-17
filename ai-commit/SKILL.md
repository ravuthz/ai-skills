---
name: ai-commit
description: Generate high-quality git commit messages from staged changes and optionally commit them automatically.
allowed-tools: Bash
---

# AI Commit Generator

## Purpose

Generate structured commit messages from staged git changes using Conventional Commits.

## Workflow

### 1. Get staged diff

```bash
git diff --cached
```

If empty → stop.

### 2. Analyze changes

Classify:

- feat, fix, refactor, chore, docs, perf, test

Detect:

- scope (folder/module)
- breaking changes
- intent of changes

### 3. Generate message

Format:
<type>(scope?): <summary>

- key changes
- why it matters

Rules:

- imperative mood
- ≤ 72 char summary
- no emojis
- no vague wording

### 4. Preview

Show message before commit.

### 5. Commit (if requested)

```bash
git commit -m "<message>"
```

## Behavior Rules

- Do NOT commit unless user explicitly asks
- Suggest split if diff is too large
- Ask if unclear intent

## Optional

Auto-stage:

```bash
git add -A
```
