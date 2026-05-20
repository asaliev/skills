# Agent Skills

Private repository for installable agent skills.

## Structure

```text
skills/
  code-review/
    SKILL.md
    agents/
      openai.yaml
```

Each skill lives in `skills/<skill-name>/` and must contain a `SKILL.md` file with YAML frontmatter:

```yaml
---
name: code-review
description: When to use this skill
---
```

## Install

Use the repository URL form that already works with your normal git setup.

With Vercel Labs `skills`:

```bash
npx skills add git@github.com:asaliev/skills.git --skill code-review
npx skills add https://github.com/asaliev/skills --skill code-review
```

With `agent-skills-cli`:

```bash
skills install git@github.com:asaliev/skills.git -s code-review
skills install https://github.com/asaliev/skills -s code-review
```

For a private GitHub repository, SSH keys, git credential helpers, `.netrc`, or supported token environment variables can be used by the installer, depending on the CLI and URL form.

## List Skills

```bash
npx skills add git@github.com:asaliev/skills.git --list
skills list -p .
```
