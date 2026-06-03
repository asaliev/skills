# Skills

A collection of agent skills for personal use.

## Available Skills

| Skill | Purpose | Use When |
| --- | --- | --- |
| `code-review` | Reviews code changes for readability problems and overengineering. | You want a concise review of code changes with prioritized findings. |
| `apply-code-review` | Implements review findings or explains why a finding was declined or deferred. | You want review feedback applied consistently. |

## Installation

Use Vercel Labs `skills` with whichever repository URL works with your normal git setup.

```bash
npx skills add git@github.com:asaliev/skills.git
```

That command prompts you to select which skills to install from this repository.

If you already know the exact skill you want, pass it explicitly:

```bash
npx skills add git@github.com:asaliev/skills.git --skill <skill-name>
```

You can also use the HTTPS URL:

```bash
npx skills add https://github.com/asaliev/skills
```

For private repositories, use SSH keys, git credential helpers, `.netrc`, or token environment variables supported by your git setup.

## Contributing

Add new skills under `skills/<skill-name>/` with a `SKILL.md` file that includes `name` and `description` frontmatter.

Keep skills focused on one workflow, and include agent-specific metadata under `agents/` only when a skill needs it.

## License

See [LICENSE](LICENSE) for the MIT terms.
