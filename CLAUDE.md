# Cariflow Site — Claude Code Context

## Project
Static marketing site for **Cariflow LLC** — AI workflow automation consultancy targeting healthcare SMBs.
- Domain: `gocariflow.com` (primary) | `getcariflow.com` (redirect)
- Repo: `cariflow-site` (public) → Cloudflare Pages CI/CD → auto-deploy on `main` push
- DNS: Namecheap (NS may be delegated to Cloudflare — verify before DNS changes)

## Stack
- Pure static HTML/CSS/JS — no build toolchain unless explicitly added
- No frameworks unless task requires it; prefer vanilla first
- Local preview: `python3 -m http.server 8080` or `npx serve .`

## Branch Strategy
- `main` = production (protected — always deployable)
- Feature work on short-lived branches: `feature/<slug>` or `fix/<slug>`
- Merge to main when preview URL looks good; Cloudflare deploys automatically

## Brand
- **Colors:** Deep navy `#1A2F45` | Calm blue `#2E7BC4`
- **Logo:** Bold open C arc with signal-strength icon (3 graduating horizontal lines) inside the opening; wordmark CARIFLOW
- **Tagline:** *THE WAY IT WAS MEANT TO*
- **Tone:** Professional but approachable; healthcare-aware (HIPAA credibility); no jargon overload

## Site Goals (V1)
1. Establish credibility for healthcare SMB and general SMB prospects
2. Explain WaaS (Workflow-as-a-Service) offering clearly
3. Drive to a single CTA: book a free consultation
4. HIPAA compliance positioning front and center

## Key Pages / Sections (V1 scope)
- Hero + CTA
- Problem / Solution
- Services (Starter / Growth / Agentic tiers)
- HIPAA Trust Signal section
- About (Dave / Cariflow story brief)
- Contact / Book a Call

## DO NOT
- Add npm dependencies without checking with Dave first
- Modify DNS records without explicit instruction
- Push directly to `main` during active dev — use feature branch

## Owner
Dave Horton (DaveOps) — dave@gocariflow.com
Related ops repo: `cariflow-ops` (private) — task state in `TODO.md`
