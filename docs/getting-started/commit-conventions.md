# Commit Message Conventions

All repositories in the `THD-Spatial-AI` and `enerplanet` organizations follow the [Conventional Commits](https://www.conventionalcommits.org/) specification, originally adopted by the EU Commission component library.

Commit messages are automatically validated on every pull request. A PR cannot be merged until all commit messages pass the check.

## Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

Only the first line is required. Body and footer are optional.

## Types

| Type | When to use |
|---|---|
| `feat` | A new feature |
| `fix` | A bug fix |
| `docs` | Documentation changes only |
| `style` | Formatting or whitespace — no logic changes |
| `refactor` | Code restructuring without new features or bug fixes |
| `perf` | Performance improvements |
| `test` | Adding or updating tests |
| `chore` | Build process, tooling, or dependency updates |

## Rules

- **Use imperative mood** — write `add login endpoint`, not `added login endpoint`
- **No capital letter** at the start of the subject
- **No period** at the end of the subject
- **Max 100 characters** per line
- Scope is optional but recommended — use it to indicate the affected area (e.g. `api`, `auth`, `docs`)

## Examples

```
feat(api): add geospatial query endpoint
fix(auth): correct token expiry validation
docs: update installation instructions
chore(ci): upgrade actions/checkout to v4
refactor(parser): simplify coordinate transformation logic
test(export): add unit tests for GeoJSON output
```

## Breaking changes

Add a `BREAKING CHANGE:` footer when a change is not backwards compatible:

```
feat(api): replace coordinate system

BREAKING CHANGE: all endpoints now return WGS84 instead of ETRS89
```

## Common mistakes

| Wrong | Correct |
|---|---|
| `updated readme` | `docs: update readme` |
| `Fix bug` | `fix: correct null pointer in parser` |
| `feat: Add new endpoint.` | `feat: add new endpoint` |
| `WIP` | `chore: scaffold route handler` |

## Using AI to fix commit messages

If your PR fails the commit lint check, you can ask an AI assistant to fix it:

> *"My commit message `update greeting message in main function` failed the conventional commits check. Please rewrite it in the correct format."*

The AI will suggest something like `feat(main): update greeting message` which you can apply with:

```bash
git commit --amend -m "feat(main): update greeting message"
git push --force-with-lease
```
