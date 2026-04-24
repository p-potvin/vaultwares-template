# VaultWares Template

![VaultWares](https://raw.githubusercontent.com/p-potvin/vaultwares-docs/main/assets/vaultwares-banner.png)

> **The Official Golden Template for all VaultWares repositories.**
> Bootstrap any new VaultWares project from this template to get the correct folder layout, `.github` guidelines, agent infrastructure, and base configuration out of the box.

---

## 🚀 Using this Template

Click **"Use this template"** on GitHub, or run:

```bash
gh repo create my-new-project --template p-potvin/vaultwares-template
```

---

## 📁 Repository Structure

```text
.
├── .github/
│   ├── CONTRIBUTING.md          # Contribution guidelines (canonical copy)
│   └── copilot-instructions.md  # GitHub Copilot agent instructions
├── agents/
│   ├── branding.md              # Local mirror of VaultWares branding reference
│   ├── image_agent.py           # Image generation & editing agent
│   ├── text_agent.py            # Text generation & captioning agent
│   ├── video_agent.py           # Video analysis & effects agent
│   └── workflow_agent.py        # ComfyUI / Diffusion workflow agent
├── vaultwares-agentciation/     # Core multi-agent framework (submodule)
├── CONTRIBUTING.md              # Root-level contribution guidelines
├── agent_manifest.md            # Agent registry & architecture reference
├── agent_collaboration_instructions.md
├── agent_id.txt
├── requirements.txt
└── run_coordinated_system.py    # Full system entrypoint
```

---

## 🤖 Multi-Agent System

This template ships a Redis-based multi-agent coordination system built on the **ExtrovertAgent** and **LonelyManager** framework from `vaultwares-agentciation`.

| Agent             | Type       | Skills                                                        |
| ----------------- | ---------- | ------------------------------------------------------------- |
| **TextAgent**     | `text`     | Text generation, captioning, prompt engineering, VQA          |
| **ImageAgent**    | `image`    | Image generation, editing, masking, inpainting, outpainting   |
| **VideoAgent**    | `video`    | Video trimming, frame sampling, effects, analysis, captioning |
| **WorkflowAgent** | `workflow` | Workflow parsing, ComfyUI/Diffusion export, validation        |

### Quick Start

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Start Redis
redis-server vaultwares-agentciation/redis.conf

# 3. Run the full coordinated system
python run_coordinated_system.py

# Or run agents individually:
python run_lonely_manager.py &
python run_worker_agent.py --type text --id text-agent-1 &
python run_worker_agent.py --type image --id image-agent-1 &
```

---

## 📋 Standards & Compliance

All code in VaultWares repositories must follow the guidelines in [`CONTRIBUTING.md`](./CONTRIBUTING.md):

- ✅ Strict TypeScript (`"strict": true`, no `any`)
- ✅ Parameterized SQL — no string interpolation
- ✅ Zod validation for all external inputs
- ✅ Type hints on all Python functions
- ✅ MVVM strictly enforced for C#/WinUI 3
- ✅ No secrets committed — use GCP Secret Manager in production
- ✅ CorrelationId on every request for traceability

---

## Local TLS Baseline for Future API Consumers

If a future repo created from this template will call the VaultWares API during local development, standardize on:

- `mkcert` for local development certificates
- `https://localhost:8000` for the local API base URL
- `https://localhost:5174` for a local web frontend when using Vite

Do not introduce new local API consumers that default to plaintext `http://localhost:*` when HTTPS is available

---

## 🔗 VaultWares Documentation

| Resource               | Link                                                           |
| ---------------------- | -------------------------------------------------------------- |
| Branding Guide         | [`agents/branding.md`](./agents/branding.md)                   |
| Agent Skills Reference | `vaultwares-agentciation/skills.md`                            |
| Extrovert Agent Spec   | `vaultwares-agentciation/extrovert.agent.md`                   |
| Lonely Manager Spec    | `vaultwares-agentciation/lonely-manager.agent.md`              |
| Live Docs              | [vaultwares-docs](https://github.com/p-potvin/vaultwares-docs) |

---

## 📄 License

See [LICENSE](./LICENSE) for details.
