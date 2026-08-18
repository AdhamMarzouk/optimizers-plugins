# optimizers-plugins

Internal Claude Code plugin marketplace for Optimizers-built plugins.

## Plugins

| Plugin | Description | Skills |
|---|---|---|
| [`branding`](./branding) | Optimizers brand kit (colors, logo, typography, buttons/components, icons, patterns) exposed as Claude Code skills. | `scaffold` — build/fix UI to comply with the brand kit · `compliance-check` — audit-only, reports without editing · `frontend-dev` — day-to-day frontend work using the design system |

## Install

### From GitHub (once this repo is pushed)

```
claude plugin marketplace add <org-or-user>/optimizers-plugins
claude plugin install branding@optimizers-plugins
```

Replace `<org-or-user>/optimizers-plugins` with this repo's actual GitHub path. Requires read access to
the repo if it's private.

### Verify

```
claude plugin validate "E:\Optimizers\optimizers-plugins"
claude plugin validate "E:\Optimizers\optimizers-plugins\branding"
claude plugin details branding@optimizers-plugins
```

## Adding a new plugin to this marketplace

1. Create a new folder at the repo root with its own `.claude-plugin/plugin.json` (see `branding/
   .claude-plugin/plugin.json` for the shape) plus whatever `skills/`, `commands/`, or `agents/` it needs.
2. Append an entry to `plugins[]` in `.claude-plugin/marketplace.json`:
   ```json
   {
     "name": "<plugin-name>",
     "source": "./<plugin-folder>",
     "description": "...",
     "version": "1.0.0",
     "author": { "name": "Optimizers", "email": "adhammarzouk200@gmail.com" }
   }
   ```
3. Validate both manifests (see above) before committing.
