# claude-skills

Stuff I got tired of instructing Claude to do.

This repo is a [Claude Code plugin marketplace](https://code.claude.com/docs/en/plugins/). Each plugin ships one or more Skills.

## Install

Add the marketplace, then install a plugin:

```bash
# Add this marketplace (owner/repo)
claude plugin marketplace add jtreutel/claude-skills

# Install a plugin — <plugin>@<marketplace-name>
claude plugin install working-style@claude-skills
```

Or do the same from inside a Claude Code session with `/plugin marketplace add jtreutel/claude-skills` and `/plugin install working-style@claude-skills`.

Verify:

```bash
claude plugin list                  # shows working-style@claude-skills
claude plugin details working-style # shows the skill inventory
```

A skill appears in the `/` menu as `/<plugin>:<skill>` — for example `/working-style:working-style`.

## Plugins

| Plugin | What it does |
|--------|--------------|
| `working-style` | Applies my engineering and technical-writing preferences: Simplified Technical English, lean dependencies, production-ready defaults, explain-the-why, and IaC state safety. |

## Repo layout

```
claude-skills/
├── .claude-plugin/
│   └── marketplace.json        # lists every plugin
└── plugins/
    └── <plugin>/
        ├── .claude-plugin/
        │   └── plugin.json      # plugin manifest (optional)
        └── skills/
            └── <skill>/
                └── SKILL.md      # the skill
```

## Add another skill or plugin

1. Create `plugins/<plugin>/skills/<skill>/SKILL.md`. Claude Code auto-discovers skills in `skills/`.
2. Add a `plugins/<plugin>/.claude-plugin/plugin.json` with a `name`.
3. Add the plugin to the `plugins` array in `.claude-plugin/marketplace.json`.
4. Validate before you push:

```bash
claude plugin validate .
```

Set `version` in `plugin.json` only (not in the marketplace entry), and bump it on each release. Third-party marketplaces do not auto-update, so users run `claude plugin update <plugin>@claude-skills`.
