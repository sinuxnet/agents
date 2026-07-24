# Contributing

## Add an agent

1. Create `agents/<name>.md` with frontmatter:

```markdown
---
name: my-agent
description: One line of what + when to use.
model: inherit
---

Persona body…
```

2. Mirror into a plugin:

```bash
name=my-agent
mkdir -p "plugins/$name/.cursor-plugin" "plugins/$name/agents"
cp "agents/$name.md" "plugins/$name/agents/$name.md"
```

3. Add `plugins/$name/.cursor-plugin/plugin.json` (`name`, `version`, `description`, `author`, `license`).

4. Register in `.cursor-plugin/marketplace.json` `plugins` array (`name`, `source`, `description`).

5. Link the companion skill in `related_skills` (repo `sinuxnet/skills`) when there is one — do not paste the full skill into this repo.

## Conventions

- **Catalog SSOT:** edit `agents/*.md`, then copy into `plugins/.../agents/`.
- Keep agents as **persona + gates**; long workflows belong in skills.
- `name` is kebab-case and matches the filename.
