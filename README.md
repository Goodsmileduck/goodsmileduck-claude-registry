# Claude Registry - Community Plugin Marketplace

[![GitHub stars](https://img.shields.io/github/stars/Goodsmileduck/goodsmileduck-claude-registry?style=social)](https://github.com/Goodsmileduck/goodsmileduck-claude-registry)
[![GitHub forks](https://img.shields.io/github/forks/Goodsmileduck/goodsmileduck-claude-registry?style=social)](https://github.com/Goodsmileduck/goodsmileduck-claude-registry/fork)
[![GitHub issues](https://img.shields.io/github/issues/Goodsmileduck/goodsmileduck-claude-registry)](https://github.com/Goodsmileduck/goodsmileduck-claude-registry/issues)
[![GitHub last commit](https://img.shields.io/github/last-commit/Goodsmileduck/goodsmileduck-claude-registry)](https://github.com/Goodsmileduck/goodsmileduck-claude-registry/commits/main)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Compatible-blueviolet)](https://claude.ai/code)

> **A community marketplace of Claude Code plugins** for productivity, code quality, and developer workflows.

Discover, install, and share plugins that enhance your Claude Code experience. From CLAUDE.md optimization to custom workflows - find the tools you need in one place.

---

## Table of Contents

- [Why Use Claude Registry?](#why-use-claude-registry)
- [Quick Start](#quick-start)
- [Available Plugins](#available-plugins)
  - [claude-md-optimizer](#claude-md-optimizer)
- [Installation](#installation)
- [Repository Structure](#repository-structure)
- [Contributing](#contributing)
  - [Plugin Requirements](#plugin-requirements)
- [License](#license)

---

## Why Use Claude Registry?

- **Curated Collection**: Quality plugins reviewed and organized for easy discovery
- **One-Command Install**: Add the marketplace once, install any plugin instantly
- **Community Driven**: Open-source plugins from the Claude Code community
- **Best Practices**: All plugins follow Claude Code plugin standards

## Quick Start

Add this marketplace to Claude Code and start installing plugins:

```bash
# Add the marketplace
/plugin marketplace add Goodsmileduck/goodsmileduck-claude-registry

# Install any plugin
/plugin install claude-md-optimizer@claude-registry
```

---

## Available Plugins

### claude-md-optimizer

Analyzes and optimizes CLAUDE.md files following Anthropic's official best practices.

| Feature | Description |
|---------|-------------|
| **Audit** | Check existing CLAUDE.md against best practices checklist |
| **Identify** | Find anti-patterns and security issues |
| **Recommend** | Generate optimization recommendations |
| **Score** | Rate your configuration (1-10 scale) |
| **Apply** | Automatically apply improvements or suggest changes |

**Install:**
```bash
/plugin install claude-md-optimizer@claude-registry
```

**Usage:**
```bash
/claude-md-optimizer
```

---

## Installation

### Option 1: Marketplace Install (Recommended)

Add the marketplace to access all plugins:

```bash
/plugin marketplace add Goodsmileduck/goodsmileduck-claude-registry
```

Then install any plugin from the registry:

```bash
/plugin install <plugin-name>@claude-registry
```

### Option 2: Local Path

For development or offline use:

```bash
# Clone the repository
git clone https://github.com/Goodsmileduck/goodsmileduck-claude-registry.git

# Add marketplace from local path
/plugin marketplace add /path/to/claude-registry
```

---

## Repository Structure

```
claude-registry/
├── .claude-plugin/
│   ├── plugin.json           # Root plugin manifest
│   └── marketplace.json      # Marketplace definition
└── plugins/
    └── claude-md-optimizer/  # CLAUDE.md optimization plugin
        ├── .claude-plugin/
        │   └── plugin.json
        └── skills/
            └── claude-md-optimizer/
                ├── SKILL.md
                └── references/
                    └── best-practices.md
```

---

## Contributing

Contributions are welcome! If you have a plugin idea or want to share your workflows:

1. Fork the repository
2. Create your plugin in `plugins/your-plugin-name/`
3. Add proper `.claude-plugin/plugin.json` manifest
4. Add entry to `.claude-plugin/marketplace.json`
5. Submit a Pull Request

### Plugin Requirements

| Requirement | Description |
|-------------|-------------|
| **Manifest** | Must have `.claude-plugin/plugin.json` with name, description, and version |
| **Naming** | Follow kebab-case naming convention |
| **Description** | Include useful description and keywords |
| **Testing** | Test your plugin locally before submitting |

---

## License

MIT License

---

**Found this useful?** Star the repo and help others discover Claude Code plugins!

[![Star this repo](https://img.shields.io/github/stars/Goodsmileduck/goodsmileduck-claude-registry?style=social)](https://github.com/Goodsmileduck/goodsmileduck-claude-registry)
