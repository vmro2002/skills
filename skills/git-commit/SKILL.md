---
name: git-commit
description: Create small, focused, reviewable, Git commit with consistent naming conventions.
disable-model-invocation: true
---

## Commit Message Format

Use Conventional Commits:

`type(scope): description`

### Types
- `feat`: Add functionality
- `fix`: Fix a bug
- `refactor`: Restructure code without changing behavior
- `perf`: Improve performance
- `test`: Add or update tests
- `docs`: Documentation changes
- `chore`: Maintenance, dependencies, or tooling
- `ci`: CI/CD configuration changes
- `build`: Build system or build dependencies
- `style`: Formatting-only changes that don't affect behavior

### Naming Rules
- Use a concise, imperative description (e.g., `add`, `fix`, `remove`, `prevent`).
- Keep the title under 72 characters when practical.
- Don't end the title with a period.
- Use a relevant, lowercase scope when applicable.
- Describe the change, not the act of making it.
- Omit the scope when no meaningful scope exists.

Examples:
- `feat(chat): add message reactions`
- `fix(auth): prevent duplicate OTP requests`
- `refactor(orders): extract payment validation`
- `perf(stores): optimize nearby store queries`
- `test(delivery): cover distance calculation`
- `docs(api): document upload endpoints`
- `chore(deps): update dependencies`
- `ci: cache dependencies during builds`

## Commit Size
- Prefer one logical change per commit.
- Aim for roughly 50–200 changed lines when practical, but do not treat this as a hard limit.
- Commits of 200–400 lines are acceptable for cohesive changes.
- For larger commits, consider splitting unrelated work into smaller commits.
- Never split changes merely to meet a line-count target if doing so creates broken or incoherent intermediate states.
- Keep each commit independently understandable and working whenever practical.

## When to Split Commits
Create separate commits when changes:
- Address different concerns or unrelated tasks.
- Can be reviewed independently.
- Have different purposes, such as a feature and unrelated formatting fixes.

Keep tightly coupled changes together when they form one logical unit, such as a database migration and the application code that requires it.

## Commit Body
Use a body only when additional context is useful.

Explain:
- Why the change was needed.
- Important implementation decisions or trade-offs.
- Breaking changes or migration requirements.

Do not repeat the title in the body.

## Workflow
1. Inspect the Git status and diff before committing.
2. Identify logical groups of changes.
3. Check for unrelated modifications, secrets, debug code, and generated files.
4. Stage only the files belonging to the intended commit.
5. Write a concise Conventional Commit message.
6. Run relevant tests, lint checks, or other required validation before committing.
7. Review the staged diff to ensure it matches the commit message.
8. Commit the changes.
9. Verify the final Git status.

## Safety Rules
- Never commit secrets, credentials, or environment files containing sensitive values.
- Never discard or overwrite unrelated user changes.
- Never use destructive Git commands to clean up changes without explicit authorization.
- Do not stage every file blindly when unrelated changes may exist.
- Do not claim tests passed unless they were actually executed successfully.
- Do not create empty commits unless explicitly requested.

## Final Principle
Optimize for reviewability, clarity, and safe changes—not commit count or line count. Every commit should clearly communicate what changed and keep unrelated work separate.