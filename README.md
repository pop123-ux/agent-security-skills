<div align="center">

# 🛡️ Agent Security Skills

**Production-grade security [Agent Skills](https://docs.claude.com/en/docs/claude-code/skills) for Claude Code, Claude agents, and OpenClaw.**

Drop-in `SKILL.md` packs that teach your AI coding agent to design secure APIs, implement bulletproof authentication, and review code like a merciless senior engineer — before insecure code ever ships.

![License](https://img.shields.io/badge/license-MIT-green)
![Skills](https://img.shields.io/badge/skills-3-blue)
![Format](https://img.shields.io/badge/format-SKILL.md-purple)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)

⭐ **If these save you from one security bug, consider starring the repo.**

</div>

---

## What are Agent Skills?

[Agent Skills](https://docs.claude.com/en/docs/claude-code/skills) are folders containing a `SKILL.md` file that extends an AI agent with focused, reusable expertise. When a task matches a skill's description, the agent loads it on demand — no fine-tuning, no plugins, just Markdown.

These skills work with **Claude Code**, **Claude agents (Agent SDK)**, **OpenClaw**, and any agent runtime that supports the `SKILL.md` convention.

## The Skills

| Skill | What it does | Use it when |
|-------|--------------|-------------|
| 🔐 [**api-security**](skills/api-security/) | OWASP API Top 10 patterns: JWT/OAuth2 auth, input validation (Zod), rate limiting, security headers, parameterized queries, and a full security checklist. | Designing or hardening REST/GraphQL/WebSocket APIs. |
| 👤 [**secure-auth-patterns**](skills/secure-auth-patterns/) | Authentication & authorization done right: JWT + refresh tokens, sessions, OAuth2/social login, RBAC, permission systems, resource ownership, password security. | Building login, SSO, or access-control systems. |
| 🛡️ [**git-sentinel**](skills/git-sentinel/) | Turns the agent into a "merciless senior engineer" that audits staged changes for security flaws, bugs, and tech debt — and gives a clear APPROVE / REJECT verdict. | Reviewing code before you commit. |

Each skill is self-contained with copy-paste-ready code examples (Node/TypeScript) and clear *USE WHEN / DON'T USE WHEN* guidance.

## Quick Start

### Claude Code

Clone into your project's skills directory:

```bash
git clone https://github.com/pop123-ux/agent-security-skills.git
cp -r agent-security-skills/skills/* .claude/skills/
```

Then just ask: *"Review my staged changes"* or *"Secure this API endpoint"* — Claude Code loads the matching skill automatically.

### OpenClaw

Copy any skill folder into your workspace `skills/` directory and start a new session:

```bash
cp -r agent-security-skills/skills/api-security ~/.openclaw/workspace/skills/
```

### Any agent

The skills are plain Markdown. Point your agent at a `SKILL.md`, or paste its contents into your system prompt as focused security context.

## Why use these?

- **Security by default** — encode OWASP best practices once, apply them on every task.
- **No lock-in** — just `SKILL.md` files. Read them, fork them, adapt them.
- **Battle-tested patterns** — JWT pitfalls, RBAC, rate limiting, injection prevention, secure headers — the stuff that actually gets shipped wrong.

## Repo layout

```
agent-security-skills/
├── README.md
├── LICENSE
└── skills/
    ├── api-security/          # OWASP API Top 10 patterns
    │   └── SKILL.md
    ├── secure-auth-patterns/  # AuthN/AuthZ, JWT, OAuth2, RBAC
    │   └── SKILL.md
    └── git-sentinel/          # AI senior code reviewer
        ├── SKILL.md
        ├── sentinel.js
        └── package.json
```

## Contributing

Found a better pattern? Spotted a flaw? PRs and issues are very welcome — see [CONTRIBUTING.md](CONTRIBUTING.md). Ideas for new security skills (CSP, SSRF defense, secrets management, threat modeling) are especially appreciated.

## License

[MIT](LICENSE) — use freely, attribution appreciated.

---

<div align="center">

Built by [**@pop123-ux**](https://github.com/pop123-ux) · If this helped, drop a ⭐ to help others find it.

</div>
