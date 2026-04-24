# VaultWares Agent Branding Reference

> **Agent Branding Reference (local mirror)**
>
> This file is a local copy for agents that cannot reach the internet.
> Always prefer the live version: <https://raw.githubusercontent.com/p-potvin/vaultwares-docs/main/agents/branding.mdx>

---

## Identity

**Brand name:** VaultWares
**Tagline:** *Build secure. Build fast. Build right.*
**Owner / Maintainer:** [@p-potvin](https://github.com/p-potvin)

---

## Voice & Tone

| Attribute | Guidance |
|---|---|
| **Professional** | Clear, direct, and technically precise. No filler words. |
| **Confident** | State things definitively; avoid "maybe" or "I think". |
| **Helpful** | Anticipate follow-up questions. Surface the right next step. |
| **Concise** | Short sentences. Bullet points over paragraphs where possible. |

Agents must never adopt a casual or playful tone in documentation, commit messages, or PR descriptions. Save personality for comments only when it aids comprehension.

---

## Visual Identity

### Colors

| Token | Hex | Usage |
|---|---|---|
| `vault-black` | `#0A0A0A` | Primary background |
| `vault-white` | `#F5F5F5` | Primary foreground |
| `vault-gold` | `#C9A84C` | Accent, highlights, CTAs |
| `vault-charcoal` | `#1E1E1E` | Card / surface background |
| `vault-muted` | `#6B6B6B` | Placeholder text, subtle labels |

### Typography

- **Headings:** Inter (700 weight)
- **Body:** Inter (400 weight)
- **Code / Mono:** JetBrains Mono

### Logo Usage

- Always use the official SVG/PNG from `vaultwares-docs/assets/`.
- Do not recolor, stretch, or add drop shadows to the logo.
- Minimum clear space: equal to the height of the "V" letterform on all sides.

---

## Repository Conventions

### Template
All new repositories **must** be bootstrapped from [`p-potvin/vaultwares-template`](https://github.com/p-potvin/vaultwares-template). This ensures the correct:
- Folder layout
- `.github` guidelines and Copilot instructions
- Agent infrastructure (`agents/`, `vaultwares-agentciation/`)
- Base `.gitignore` and `requirements.txt`

### Naming
| Artifact | Convention | Example |
|---|---|---|
| Repositories | `kebab-case` | `vault-auth-service` |
| Branches | `feat/slug` or `fix/slug` | `feat/add-branding-guide` |
| Python files | `snake_case.py` | `audio_capture.py` |
| TypeScript components | `PascalCase.tsx` | `VaultButton.tsx` |
| Docker images | `vaultwares/<name>:<tag>` | `vaultwares/api:latest` |

---

## Agent-Specific Rules

1. **Never hardcode secrets.** Read credentials from environment variables or GCP Secret Manager.
2. **Always include a CorrelationId** (`c` + 6 alphanumeric chars) in log entries and error responses.
3. **Prefer the live branding doc** over this local copy when internet access is available.
4. **Do not modify `ui/` primitives** directly — only extend via `features/` components.
5. **Log with `logging` module** (Python) or structured JSON (Node) — no `print()` / `console.log()` in production paths.

---

## Changelog

| Date | Change |
|---|---|
| 2026-04-24 | Initial local mirror created from `vaultwares-docs` branding spec |
