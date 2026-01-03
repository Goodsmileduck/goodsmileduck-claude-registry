---
name: claude-md-optimizer
description: "Analyzes and optimizes CLAUDE.md files following Anthropic's official best practices. Use when reviewing existing CLAUDE.md for improvements, or when user mentions CLAUDE.md is too long or ineffective."
---

# Optimize CLAUDE.md

Analyze, audit, and optimize CLAUDE.md files based on Anthropic's official best practices for effective Claude Code configuration.

## Degrees of Freedom

This is a **medium-freedom** task. Follow the structured workflow but adapt recommendations based on the specific project's needs, tech stack, and team conventions.

## Workflow

Copy this checklist and track your progress:

```
Optimization Progress:
- [ ] Step 1: Analyze current CLAUDE.md state
- [ ] Step 2: Audit against best practices checklist
- [ ] Step 3: Identify and prioritize issues
- [ ] Step 4: Generate recommendations
- [ ] Step 5: Apply or present changes
```

### 1. Analyze Current State

Read the existing CLAUDE.md (if present) and assess:
- Current structure and organization
- Content categories present
- Length and verbosity
- Presence of anti-patterns

### 2. Audit Against Best Practices

Compare against the checklist in [references/best-practices.md](references/best-practices.md).

Score each category:
- **Present & Good** - Follows best practices
- **Present but Needs Work** - Exists but could be improved
- **Missing** - Should be added
- **Anti-pattern** - Should be removed/fixed

### 3. Generate Recommendations

Prioritize changes by impact:

**High Priority:**
- Remove sensitive information (API keys, credentials)
- Fix anti-patterns (generic advice, excessive length)
- Add missing critical sections (project structure, commands)

**Medium Priority:**
- Improve organization and scannability
- Add missing helpful sections
- Condense verbose explanations

**Low Priority:**
- Formatting improvements
- Minor restructuring
- Optional enhancements

### 4. Apply Changes

Either:
- **Suggest mode**: Present recommendations for user approval
- **Apply mode**: Directly edit CLAUDE.md with improvements

## Optimization Principles

### Keep It Concise

CLAUDE.md is loaded into context every time. Total limit: **40k tokens** (CLAUDE.md + all @referenced files combined).

```markdown
# BAD: Verbose explanation
## Testing Guidelines
When running tests in this project, you should use the npm test command.
This will execute all test files and provide output. Make sure tests pass.

# GOOD: Concise and actionable
## Testing
npm test                    # Run all tests
npm run test:coverage       # With coverage report
```

### Be Specific, Not Generic

Include YOUR project's actual patterns, not theoretical best practices.

```markdown
# BAD: Generic advice
Follow clean code principles and write maintainable code.

# GOOD: Project-specific guidance
Use `logger` from @/utils, never console.log (tree-shaken in production).
Query keys must use queryKeys factory from @/lib/queryKeys.
```

### Use Progressive Disclosure

For large documentation, split into separate files and reference them:

```markdown
# In CLAUDE.md
See @.claude/rules/testing.md for testing standards.
See @docs/ARCHITECTURE.md for system design.

# NOT: 500 lines of testing docs inline
```

### Include Actual Commands

Show the commands your team uses:

```markdown
## Development
npm run dev     # Start dev server (localhost:3000)
npm test        # Run tests in watch mode
npm run build   # Production build
```

### Use Emphasis for Critical Rules

For must-follow instructions, use emphasis markers:

```markdown
IMPORTANT: Never commit directly to main.
YOU MUST run tests before pushing.
ALWAYS use logger utility, never console.log.
```

## Output Format

When optimizing, provide:

1. **Summary** - Brief assessment (1-2 sentences)
2. **Score** - X/10 rating with breakdown
3. **Critical Issues** - Must-fix problems
4. **Recommendations** - Prioritized improvements
5. **Optimized CLAUDE.md** - The improved file (if applying changes)

## Example Assessment

```
## CLAUDE.md Optimization Report

**Summary:** Good foundation but overly verbose. Contains generic advice that adds token cost without value.

**Score:** 6/10
- Structure: 8/10 (well-organized sections)
- Conciseness: 4/10 (too verbose, 2000+ lines)
- Specificity: 5/10 (mix of specific and generic)
- Security: 9/10 (no sensitive data found)

**Critical Issues:**
1. File exceeds 500 lines - should use modular rules files
2. Contains generic "best practices" not specific to project

**Recommendations:**
1. [HIGH] Move detailed rules to .claude/rules/*.md files
2. [HIGH] Remove generic coding advice Claude already knows
3. [MED] Add missing quick-start commands section
4. [LOW] Consolidate duplicate information in docs/
```

## Resources

### references/
- [best-practices.md](references/best-practices.md) - Complete checklist for CLAUDE.md optimization
