# CLAUDE.md Best Practices Checklist

Based on Anthropic's official guidance: https://www.anthropic.com/engineering/claude-code-best-practices

## Contents

- File Locations (valid placements to check)
- Structure Checklist (essential sections, organization)
- Content Quality Checklist (conciseness, specificity, actionability)
- Emphasis Techniques (for critical instructions)
- Anti-Patterns to Remove (security, unnecessary content, structural issues)
- Modular Organization Pattern (.claude/rules/ directory)
- Recommended CLAUDE.md Template
- Scoring Criteria

## File Locations

Valid CLAUDE.md placements to be aware of when optimizing:

| Location | Purpose |
|----------|---------|
| `./CLAUDE.md` | Project root, version-controlled |
| `./CLAUDE.local.md` | Project root, gitignored (personal) |
| `~/.claude/CLAUDE.md` | Global, applies to all sessions |
| Child directories | Loaded on-demand for nested files |
| Parent directories | Inherited in monorepos |

**Tip**: After optimization, user can press `#` while coding to incrementally add instructions to CLAUDE.md.

## Structure Checklist

### Essential Sections

| Section | Required | Description |
|---------|----------|-------------|
| Project Overview | Yes | 1-2 sentences explaining what the project is |
| Tech Stack | Yes | Key technologies, frameworks, versions |
| Quick Start | Yes | Essential commands (dev, test, build) |
| File Structure | Recommended | Key directories and their purpose |
| Critical Rules | Recommended | Must-follow patterns specific to project |
| Repo Etiquette | Recommended | Branching strategy, merge/PR conventions |
| Dev Environment | Optional | Setup requirements, dependencies |

### Organization

- [ ] Clear markdown headers (# for main, ## for sub)
- [ ] Scannable format (tables, bullet points)
- [ ] Logical grouping of related content
- [ ] Progressive disclosure (link to detailed docs)

## Content Quality Checklist

### Conciseness

- [ ] Under 40k tokens (CLAUDE.md + all @referenced files combined)
- [ ] Keep concise - every token has context cost
- [ ] No redundant explanations
- [ ] Commands shown with inline comments, not paragraphs
- [ ] Examples over explanations where possible

### Specificity

- [ ] Project-specific patterns, not generic advice
- [ ] Actual commands used in this project
- [ ] Real file paths and naming conventions
- [ ] Specific tools and their usage

### Actionability

- [ ] Copy-pasteable commands
- [ ] Clear do/don't examples
- [ ] Concrete file references (@docs/ARCHITECTURE.md)
- [ ] Workflow steps when applicable

## Emphasis Techniques

For critical instructions that must be followed, use emphasis markers:

```markdown
# Good - Clear emphasis for critical rules
IMPORTANT: Never commit directly to main branch.
YOU MUST run tests before pushing.
ALWAYS use the logger utility, never console.log.

# Also effective
**Critical**: API keys must never be hardcoded.
```

Anthropic teams use these markers to strengthen instruction-following. Use sparingly for truly critical rules.

## Anti-Patterns to Remove

### Security Issues (CRITICAL)

- [ ] No API keys or secrets
- [ ] No database credentials
- [ ] No internal URLs with auth tokens
- [ ] No security vulnerability details

### Unnecessary Content

- [ ] No generic coding best practices Claude knows
- [ ] No explanations of standard tools (git, npm, etc.)
- [ ] No theoretical advice without project context
- [ ] No duplicate information from other docs

### Structural Issues

- [ ] No walls of text without formatting
- [ ] No deeply nested structures (>3 levels)
- [ ] No outdated information
- [ ] No commented-out sections

## Modular Organization Pattern

For projects with complex rules, use `.claude/rules/` directory:

```
.claude/
├── rules/
│   ├── code-style.md      # TypeScript, naming, imports
│   ├── react-patterns.md  # React, state, hooks
│   ├── testing.md         # Test standards
│   ├── security.md        # Security rules
│   └── README.md          # Index of rules
```

Each rule file can have YAML frontmatter for path-specific loading:

```yaml
---
paths:
  - "src/**/*.ts"
  - "src/**/*.tsx"
---
```

**Note**: Glob patterns must be quoted (patterns starting with `*` or `{` are reserved YAML indicators).

## Recommended CLAUDE.md Template

```markdown
# Project Name

Brief description (1-2 sentences).

## Quick Start

\`\`\`bash
npm install
npm run dev    # Start dev (localhost:3000)
npm test       # Run tests
npm run build  # Production build
\`\`\`

## Tech Stack

React 19 + TypeScript + Vite + TanStack Query + Zustand

## File Structure

\`\`\`
src/
├── components/    # UI components
├── services/      # API layer
├── hooks/         # React Query hooks
├── store/         # Zustand stores
├── types/         # TypeScript types
└── utils/         # Utilities
\`\`\`

## Critical Rules

- Never use `any` type - use proper types or `unknown`
- Use barrel exports: `import { Button } from '@/components/ui'`
- Use `logger` utility, never `console.log`
- See @.claude/rules/ for detailed standards

## Repo Etiquette

- Branch from `main`, PR required for merge
- Commit message format: `type(scope): description`
- IMPORTANT: Run `npm test` before pushing

## Documentation

- @docs/ARCHITECTURE.md - System design
- @docs/COMPONENTS.md - UI library
- @CONTRIBUTING.md - Development guide
```

## Scoring Criteria

| Score | Description |
|-------|-------------|
| 9-10 | Excellent - Concise, specific, well-organized |
| 7-8 | Good - Minor improvements possible |
| 5-6 | Acceptable - Needs optimization |
| 3-4 | Poor - Major issues to address |
| 1-2 | Critical - Fundamental restructuring needed |

### Scoring Breakdown

- **Structure (25%)**: Headers, organization, scannability
- **Conciseness (25%)**: Line count, verbosity, token efficiency
- **Specificity (25%)**: Project-specific vs generic content
- **Security (15%)**: No sensitive information
- **Completeness (10%)**: Essential sections present
