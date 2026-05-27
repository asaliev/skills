# Agent Skills

Private repository for installable agent skills.

## Available Skills

| Skill | Purpose | Use When |
| --- | --- | --- |
| `code-review` | Reviews code changes for readability problems and overengineering. | You want prioritized findings for a diff, snippet, branch comparison, staged changes, or patch. |
| `apply-code-review` | Implements review findings or explains why a finding was declined or deferred. | You already have a code review report and want the findings handled. |

## Install

Use the repository URL form that already works with your normal git setup.

With Vercel Labs `skills`:

```bash
npx skills add git@github.com:asaliev/skills.git --skill <skill-name>
npx skills add https://github.com/asaliev/skills --skill <skill-name>
```

With `agent-skills-cli`:

```bash
skills install git@github.com:asaliev/skills.git -s <skill-name>
skills install https://github.com/asaliev/skills -s <skill-name>
```

Examples:

```bash
npx skills add git@github.com:asaliev/skills.git --skill code-review
skills install https://github.com/asaliev/skills -s apply-code-review
```

For a private GitHub repository, use the SSH keys, git credential helpers, `.netrc`, or token environment variables supported by your installer.

## List Available Skills

```bash
npx skills add git@github.com:asaliev/skills.git --list
skills list -p .
```

## Repository Layout

Each skill lives in `skills/<skill-name>/` and includes a `SKILL.md` file. Skills can also include agent-specific metadata under `agents/`.

```text
skills/
  apply-code-review/
    SKILL.md
    agents/
      openai.yaml
  code-review/
    SKILL.md
    agents/
      openai.yaml
```
