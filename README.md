# Sinuxnet Agents

Cursor / Claude Code **subagent** personas. Skills live in [`sinuxnet/skills`](https://github.com/sinuxnet/skills); agents live here.

## Quick install (manual)

```bash
# one agent
curl -fsSL https://raw.githubusercontent.com/sinuxnet/agents/main/agents/component-eval-architect.md \
  -o ~/.cursor/agents/component-eval-architect.md

# or clone and copy
git clone https://github.com/sinuxnet/agents.git
cp agents/agents/*.md ~/.cursor/agents/
# Claude Code: cp agents/agents/*.md ~/.claude/agents/
```

## Cursor plugin marketplace

This repo is a multi-plugin marketplace (`.cursor-plugin/marketplace.json`). Each plugin under `plugins/<name>/` exposes one agent.

## Layout

```text
agents/                         # catalog (edit here first)
  component-eval-architect.md
plugins/<name>/                 # Cursor-installable mirror
  .cursor-plugin/plugin.json
  agents/<name>.md
.cursor-plugin/marketplace.json
```

After editing a catalog file, sync into its plugin:

```bash
name=component-eval-architect
cp "agents/$name.md" "plugins/$name/agents/$name.md"
```

## Agents

| Agent | Role |
|-------|------|
| [`component-eval-architect`](agents/component-eval-architect.md) | Evaluation Harness / MVE architect (pairs with `build-evaluation-harness` in skills) |

## Related

- Skills: https://github.com/sinuxnet/skills
- Contributing: [docs/contributing.md](docs/contributing.md)

## License

MIT
