# 0k-plugins

The Claude Code plugin marketplace for
[0k-software](https://github.com/0k-software).

## Installation

From any Claude Code session, register the marketplace:

```
/plugin marketplace add 0k-software/0k-plugins
```

Then install any plugin from the list below.

## Available plugins

### kata

0k-software org skills — commit, rebase, issue management, branch workflows, PR
creation, plan-driven implementation, and more.

**Categories:** workflow, git, github, skills

**Install:**

```
/plugin install kata@0k-plugins
```

Once installed, every skill is available as `/kata:<skill-name>` (for example
`/kata:commit`, `/kata:create-pr`, `/kata:rebase`).

**Repository:** https://github.com/0k-software/kata

---

## Enabling across an org's projects

Add this to a project's `.claude/settings.json` to register the marketplace and
auto-enable a plugin for everyone who opens the project:

```json
{
  "extraKnownMarketplaces": {
    "0k-plugins": {
      "source": {
        "source": "github",
        "repo": "0k-software/0k-plugins"
      }
    }
  },
  "enabledPlugins": {
    "kata@0k-plugins": true
  }
}
```

This is the standard Claude Code mechanism for distributing plugins to a team —
no custom scripts or hooks required. Claude Code handles installation and
updates automatically. See the
[plugin marketplaces docs](https://docs.claude.com/en/docs/claude-code/plugin-marketplaces)
for details.

## Marketplace structure

```
.claude-plugin/
└── marketplace.json    marketplace manifest (plugins, sources)
.github/
└── workflows/
    └── check.yml       Prettier formatting check on PRs and main
.prettierrc.yml         Prettier config (Markdown: proseWrap, printWidth)
```

## Support

- Issues with the marketplace itself:
  https://github.com/0k-software/0k-plugins/issues
- Issues with `kata`: https://github.com/0k-software/kata/issues

## License

This marketplace is MIT licensed. Individual plugins are licensed under their
own terms — see each plugin's repository for details.
