# Agent Working Agreement

Instructions for any AI coding agent (Claude Code, Codex, etc.) making changes to this repository. Read this before you touch anything.

This file covers HOW to work in this repo (git workflow, safety). For WHAT good content looks like (knowledge base entries, decision logic, style), read `docs/contributing.md`.

## Git workflow (non-negotiable)

1. **Branch first.** Never commit to `main`. Before making any change, create a branch: `git checkout -b <short-topic-name>`. If you are already on a feature branch, stay on it.

2. **Open a PR, do not merge it.** When the work is ready, push the branch and open a pull request against `main`. Leave the merge decision to a human. Do not merge your own PR.

3. **Never force-push `main`.** No `git push --force` to `main`, ever. No `git reset --hard` on `main` followed by a push. If history on `main` looks wrong, stop and ask a human. (Force-pushing a feature branch you own is fine when needed.)

4. **New commits, not amends, on shared history.** Prefer a new commit over `git commit --amend` or interactive rebase once anything is pushed. If a pre-commit hook fails, fix the cause and make a new commit. Never use `--no-verify` or skip signing unless a human explicitly asks.

5. **Stage files by name.** Use `git add <path>`, not `git add -A` or `git add .`. Never commit secrets (`assets/config.yaml` and `custom/` are gitignored for a reason). Scan the diff before committing.

## Commits and PRs

- One logical change per commit. Write a clear message that explains the WHY, not just the what.
- Keep PRs small and single-purpose so a human can actually review them.
- In the PR description, summarize what changed and why, and note any eval results.

## Before you open a PR

- Run the relevant scenarios in `evals/` against your changes and note the results. Decision-logic changes especially must not regress expected behavior.
- Re-read your actual diff. Confirm it does what you intended, not just what you meant to type.

## Editing rules specific to this skill

- `references/` is the shared backend layer (applies to every property management company). `custom/` is per-company overrides and is gitignored. Put shared rules in `references/`, never in `custom/`.
- Follow the writing style in `docs/contributing.md`: warm, direct, plain English, short sentences. **No em dashes** anywhere. Use commas, periods, parentheses, or rewrite.
- No specific dollar amounts in guidance (costs vary by region). Use relative terms.
- Safety first. This skill affects real tenants in real homes. Never recommend something a vendor would call dangerous, and never ask a tenant to do something risky to save a dispatch fee.

## When in doubt

Stop and ask the human. Escalation is correct behavior, not failure. This applies to you, the coding agent, exactly as it applies to the maintenance coordinator the skill describes.
