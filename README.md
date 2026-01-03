# Claude Registry

A community marketplace of Claude Code plugins for productivity, code quality, and developer workflows.

## Installation

Add this marketplace to Claude Code:

```bash
/plugin marketplace add Goodsmileduck/goodsmileduck-claude-registry
```

Or using a local path:

```bash
/plugin marketplace add /path/to/goodsmileduck-claude-registry
```

## Available Plugins

### claude-md-optimizer

Analyzes and optimizes CLAUDE.md files following Anthropic's official best practices.

**Install:**
```bash
/plugin install claude-md-optimizer@claude-registry
```

**Features:**
- Audit existing CLAUDE.md against best practices checklist
- Identify anti-patterns and security issues
- Generate optimization recommendations
- Score your configuration (1-10 scale)
- Apply improvements automatically or suggest changes

**Usage:**
```bash
/claude-md-optimizer
```

## Repository Structure

```
.claude-plugin/
├── plugin.json           # Root plugin manifest
└── marketplace.json      # Marketplace definition

plugins/
└── claude-md-optimizer/  # CLAUDE.md optimization plugin
    ├── .claude-plugin/
    │   └── plugin.json
    └── skills/
        └── claude-md-optimizer/
            ├── SKILL.md
            └── references/
                └── best-practices.md
```

## Contributing

Want to add a plugin to this marketplace?

1. Fork this repository
2. Create your plugin in `plugins/your-plugin-name/`
3. Add proper `.claude-plugin/plugin.json` manifest
4. Add entry to `.claude-plugin/marketplace.json`
5. Submit a pull request

### Plugin Requirements

- Must have `.claude-plugin/plugin.json` with name, description, and version
- Follow kebab-case naming convention
- Include useful description and keywords
- Test your plugin locally before submitting

## License

MIT
