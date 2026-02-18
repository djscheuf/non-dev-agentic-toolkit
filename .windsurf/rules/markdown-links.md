---
trigger: "**/*.md"
---

# Markdown Link Formatting Rules

When creating or updating markdown documentation in this repository, always use proper markdown link syntax for internal references.

## Core Principle

**Use clickable markdown links, not plain text paths**, to make it easier for users to navigate related content.

## Link Format

```markdown
[descriptive text](relative/path/from/repo/root)
```

## Examples

### ❌ Wrong (plain text paths)
```markdown
See .windsurf/workflows/research.md for details
Check the docs/project-context-and-audience.md file
Refer to examples/toyota-kata-scientific-thinking.md
```

### ✅ Correct (markdown links)
```markdown
See [the research workflow](.windsurf/workflows/research.md) for details
Check [the project context document](docs/project-context-and-audience.md)
Refer to [the Toyota Kata example](examples/toyota-kata-scientific-thinking.md)
```

## Path Guidelines

1. **Use relative paths from repository root** - Start with the top-level folder (e.g., `docs/`, `.windsurf/`, `examples/`)
2. **Make link text descriptive** - Use meaningful descriptions, not just "this file" or "here"
3. **Apply to all internal references** - Workflows, rules, docs, examples, templates

## Common Link Patterns

### Workflows
```markdown
[the research workflow](.windsurf/workflows/research.md)
[the decision facilitation workflow](.windsurf/workflows/decision-facilitation.md)
[the Wardley Mapping workflow](.windsurf/workflows/wardley-mapping.md)
```

### Documentation
```markdown
[the project context](docs/project-context-and-audience.md)
[the research workflow guide](docs/using-the-research-workflow.md)
[understanding the research pattern](docs/understanding-research-workflow-pattern.md)
```

### Examples
```markdown
[the Toyota Kata example](examples/toyota-kata-scientific-thinking.md)
[the Wardley Mapping example](examples/facilitating-wardley-mapping.md)
```

### Rules
```markdown
[the active partner rule](.windsurf/rules/active-partner.md)
[the markdown link rules](.windsurf/rules/markdown-links.md)
```

### Templates
```markdown
[the Research Note template](templates/Research%20Note.md)
```
