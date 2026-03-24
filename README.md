# claude_cookiecutter

A [Cookiecutter](https://cookiecutter.readthedocs.io/) template that scaffolds a fully configured
[Claude Code](https://docs.anthropic.com/en/docs/claude-code) project structure — so you can skip
the boilerplate and start building immediately.

## What You Get

```
your_project/
├── CLAUDE.md                        # Claude's instruction manual (read every session)
└── .claude/
    ├── settings.json                # Allow / deny rules for Claude's tool use
    ├── rules/
    │   ├── code-style.md            # Formatting, naming, and comment conventions
    │   ├── testing-standards.md     # Coverage requirements and test patterns
    │   └── api-conventions.md       # REST URL structure, response envelopes, versioning
    ├── commands/
    │   ├── review.md                # `project:review`   – structured PR review with live diff
    │   ├── fix-issue.md             # `project:fix-issue` – fetch a GitHub issue and fix it
    │   └── changelog.md             # `project:changelog` – generate a Keep-a-Changelog entry
    ├── skills/
    │   ├── write-tests.md           # Auto-invoked when asked to write tests
    │   ├── refactor.md              # Auto-invoked when asked to refactor code
    │   └── debug.md                 # Auto-invoked when a stack trace or error is pasted
    └── agents/
        ├── code-reviewer.md         # Isolated subagent for deep code review
        ├── docs-writer.md           # Isolated subagent for documentation generation
        └── security-auditor.md      # Isolated subagent for security audits
```

## Prerequisites

- Python ≥ 3.8
- [Cookiecutter](https://cookiecutter.readthedocs.io/en/stable/README.html#installation)

```bash
pip install cookiecutter
```

## Usage

### From GitHub (recommended)

```bash
cookiecutter gh:tinix84/claude_cookiecutter
```

### From a local clone

```bash
git clone https://github.com/tinix84/claude_cookiecutter.git
cookiecutter claude_cookiecutter/
```

You will be prompted for:

| Variable | Default | Description |
|----------|---------|-------------|
| `project_name` | `my_project` | Human-readable project name |
| `project_slug` | auto-derived | Directory name (snake_case) |
| `project_description` | — | One-line description |
| `author_name` | — | Your name |
| `author_email` | — | Your email |
| `version` | `0.1.0` | Starting version |
| `primary_language` | `python` | Main programming language |
| `package_manager` | `npm` | Package manager for commands |

## After Scaffolding

1. **Fill in `CLAUDE.md`** with your actual build commands, architecture decisions, and gotchas.
2. **Review `.claude/settings.json`** and adjust the allow/deny permissions to match your workflow.
3. **Customize the rules** in `.claude/rules/` to reflect your team's actual standards.
4. **Add project-specific commands** in `.claude/commands/` for your recurring workflows.
5. **Commit `.claude/` to your repository** — it is infrastructure, treat it like one.

## Claude Code Folder Reference

| Path | Purpose |
|------|---------|
| `CLAUDE.md` | Main instruction file; Claude reads it at the start of every session |
| `.claude/settings.json` | Permissions: what Claude can and cannot execute |
| `.claude/rules/*.md` | Scoped rules activated per file path or always-on conventions |
| `.claude/commands/*.md` | Custom slash commands (`project:<name>`) with shell interpolation |
| `.claude/skills/*.md` | Context-triggered automations that activate without explicit invocation |
| `.claude/agents/*.md` | Specialized subagents with isolated context, tools, and model settings |

## Further Reading

- [Claude Code – Best Practices](https://docs.anthropic.com/en/docs/claude-code/best-practices)
- [Claude Code – Features Overview](https://docs.anthropic.com/en/docs/claude-code/overview)

