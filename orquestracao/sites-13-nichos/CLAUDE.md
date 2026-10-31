# CLAUDE.md

Rules for every Claude agent working in this repository. Read fully before acting.

## 1. Communication
- Be terse. No preambles, no recaps, no filler, no flattery.
- Report only: what was done, what is blocked, what is next. Max 5 lines unless asked.
- Ask a question only when blocked or when an action is in the "Ask first" list. One question at a time.
- Never narrate tool calls. Never repeat the user's request back.
- Final message of a task: outcome + file paths + one next step.

## 2. Project structure
Create this layout at the start and keep it consistent:

```
/
├── CLAUDE.md
├── README.md
├── docs/
│   ├── specs/          # one spec per site (analysis output)
│   ├── changes/        # per-site changes dictated by the user
│   ├── INDEX.md        # number → niche → reference → folder → status → URL
│   ├── design/         # design tokens, palettes, typography per niche
│   ├── content/        # copy per niche (JSON/MD)
│   └── logs/           # status.md, decisions.md
├── references/         # notes on the source sites (no copied assets)
├── shared/             # shared components, utils, base template
├── sites/
│   ├── 01-<niche-slug>/
│   ├── ...
│   └── 14-portfolio/
└── scripts/            # build, lint, deploy helpers
```

- Folder names: lowercase, kebab-case, numbered for sites.
- One site = one self-contained folder deployable on its own.
- Keep `docs/logs/status.md` updated: one line per site with state (todo / building / qa / ready / deployed).

## 3. Code best practices
- Prefer simple, readable code. No dead code, no unused dependencies.
- Semantic HTML, accessible by default (alt text, labels, contrast, keyboard focus).
- Mobile-first, responsive, no horizontal scroll.
- Performance: optimized images, lazy loading, no blocking scripts, Lighthouse target ≥ 90.
- SEO basics per site: title, meta description, Open Graph, favicon, sitemap if applicable.
- Use design tokens (CSS variables) for colors, spacing, type. No magic numbers.
- Reuse shared components; do not duplicate across sites.
- Never hardcode secrets. Use `.env` + `.env.example`. `.env` is always gitignored.
- Lint and build must pass before any commit.

## 4. Clone mode
- The job is to clone the reference sites faithfully (sections, layout, components, behavior), then adapt them to the niche.
- No creativity. Do not invent sections, features, copy, colors, or design ideas. Only exceptions: an invented business name per niche (the portfolio is always named Koda), and Unsplash images that fit the niche.
- The user decides every change (palette, layout arrangement, graphic elements). Record them in `docs/changes/NN-slug.md`. Without a recorded change, stay as close to the reference as possible.
- Niche swap = direct substitution: same structure, tone, and length; only niche terms change. Unknown facts, prices, people's names, testimonials: use `[TODO]` and log in `docs/logs/open-questions.md`.
- Do not copy the reference's logos, brand names, trademarks, photos, illustrations, or verbatim text. Use the invented business name (text wordmark), Unsplash images, and simple SVG icons, or user-supplied assets.
- Sites are numbered (01–13 niche sites, 14 portfolio). Refer to them by number. Koda palette (black primary, blue secondary) applies only to site 14. The Koda logo image is never used in any site unless the user explicitly says so.

## 5. Git
- Small, atomic commits. Conventional Commits: `feat:`, `fix:`, `docs:`, `chore:`, `refactor:`.
- Branch per site or task: `site/03-fitness`, `chore/setup`.
- Never force-push. Never commit `node_modules`, `.env`, build output.
- Orca worktrees: each worker agent has its own worktree and branch `agent/<role>`. Workers commit only inside their owned folders and never push. Only the Orchestrator merges to `main` and pushes.
- Before starting a phase, update your worktree from `main`.
- Commit message: imperative, ≤ 72 chars.
- Sole author: ianeusantiago@gmail.com. Set `user.email` to it locally in the repo.
- No `Co-Authored-By` trailers and no AI attribution ("Generated with Claude", etc.) in commits, PRs, README, or code. Verify with `git log` before every push.

## 6. Ask first (never do without explicit user approval)
- Logging into any account (Vercel, GitHub, other).
- Creating the GitHub repository (ask for account/username and visibility first).
- Deploying anything to Vercel.
- Publishing, sending messages, spending money, deleting data.
- Entering passwords, tokens or API keys. The user does this personally.

## 7. Orchestration rules
- Orchestrator plans, delegates, reviews. It does not write site code itself.
- The portfolio site is always built last and deployed last. Its company name is Koda (given by the user). It aggregates all the other sites (name, niche, thumbnail, link).
- Every task handed to an agent must include: goal, inputs, output path, definition of done.
- Agents write results to files, not long chat messages.
- Agents never edit another agent's owned folder without telling the orchestrator.
- Blockers go to `docs/logs/status.md` and are escalated immediately.

## 8. Definition of done (per site)
- Matches the reference structure and the user's recorded changes, with niche content (no invented content).
- Responsive and accessible.
- Build passes, no console errors, no broken links.
- Registered in `docs/logs/status.md` as `ready`.
