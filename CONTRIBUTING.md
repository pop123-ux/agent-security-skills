# Contributing

Thanks for considering a contribution! This repo is a curated set of security-focused Agent Skills.

## Ways to help

- **Improve a skill** — tighten a pattern, fix an inaccuracy, add a missing edge case.
- **Add a new security skill** — e.g. CSP hardening, SSRF defense, secrets management, threat modeling, dependency auditing.
- **Report issues** — found a flaw or an outdated practice? Open an issue.

## Adding a new skill

1. Create `skills/<your-skill>/SKILL.md`.
2. Start with a one-line description and clear **USE WHEN / DON'T USE WHEN** guidance.
3. Include copy-paste-ready, correct examples. Prefer secure-by-default code.
4. Add a row to the table in the root `README.md`.
5. Open a PR describing what the skill does and why it's useful.

## Standards

- Accuracy first — security advice must be correct and current.
- No secrets, API keys, or credentials in examples (use placeholders).
- Keep skills focused; one concern per skill.
