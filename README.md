# Vibecoder Skills — reusable UI / motion / design / code-quality resources

A personal catalog of external libraries, component collections, and agent skills to pull from across projects. Curated by Cliff.

Each entry: **what it is**, **best used for**, and **how to pull it in**.

> Note on "skills": some of these ship as installable **agent skills** (Cursor/Claude Code), some are **npm/CLI component libraries**, and a couple are **browse-and-copy component sites**. The type is labelled per entry.

Last updated: 2026-09-24

---

## 1. Transitions & Motion

### transitions.dev
- **Link:** https://github.com/Jakubantalik/transitions.dev
- **Type:** CSS snippets + CLI + agent skill
- **What it is:** An interactive collection of ~18 production-ready CSS transitions (card resize, number pop-ins, modal open/close, page transitions, etc.). Self-contained CSS with semantic custom properties and `prefers-reduced-motion` support.
- **Best used for:** Dropping polished, tokenized motion into any web UI without hand-rolling keyframes. The "Refine" panel lets an agent suggest/apply transitions to a running app.
- **How to pull in:** `npx transitions-dev add [name]`, or install as an agent skill. (Already installed globally as the `transitions-dev` + `transitions-polish` skills.)

### shadcn-animated
- **Link:** https://github.com/sopo/shadcn-animated
- **Type:** Component library (React/TS)
- **What it is:** Animated versions of shadcn/ui components. Drop-in replacements built with Framer Motion + Tailwind + TypeScript.
- **Best used for:** Projects already on shadcn/ui that want polished animation without swapping design systems.
- **How to pull in:** npm install / component docs site (drop-in per component).

### Theatre.js
- **Link:** https://www.theatrejs.com/
- **Type:** JS animation library (open source, 7.7k+ stars)
- **What it is:** A professional motion library — "create in code, perfect in the browser." Sequence editor, graph editor, dope sheet, easing presets. Works with THREE.js, React Three Fiber, HTML/CSS/SVG, WebGPU; drives JS variables so you own the render.
- **Best used for:** Cinematic / keyframed animation and 3D scene choreography beyond what CSS transitions cover — landing-page hero moments, scroll storytelling. Heavier than transitions.dev; reach for it only when the motion is the point.
- **How to pull in:** `npm install @theatre/core @theatre/studio`.

### product-film ✅ INSTALLED
- **Link:** https://github.com/Rieranthony/product-film-skill
- **Type:** Agent skill (Claude Code) — **installed at `~/.claude/skills/product-film`**
- **What it is:** Generates showreel-grade **product videos in code with Remotion**, built from the product's own design system, components, logo, and voice. 7-step flow (design discovery → interview → brand kit → music sync → scene build → review stills/drafts → verified render). Outputs muted web loop, music version, WebM, and a poster — all verified for color, duration, seamless loop. Deps: Node/Bun, Remotion (free for individuals/small teams), Python (uv) + ffmpeg.
- **Best used for:** Landing-page loops, launch/promo/demo reels for an app or SaaS — a code-native alternative to Reelfolio that reuses real components. Natural fit for the radix-showreel work.
- **How to pull in:** Already installed. Reinstall/update: clone the repo and copy `plugins/product-film/skills/product-film` into `~/.claude/skills/`, or `/plugin marketplace add Rieranthony/product-film-skill` then `/plugin install product-film@product-film-skill` in an interactive terminal.

### brag / brag-slim ✅ INSTALLED
- **Link:** https://github.com/latent-spaces/brag
- **Type:** Agent skill — **installed at `~/.claude/skills/brag` and `~/.claude/skills/brag-slim`**
- **What it is:** Turns the current project into a short, shareable **launch video** (motion + music + share copy) from one command — reads the project code directly, no live URL needed. `/brag` uses Hyperframes; `/brag-slim` is a single-file version (built with tools already on the machine, tuned for Opus 5.5). Needs Node 22+ and ffmpeg.
- **Best used for:** Fast "show what I built" launch clips for any shipped project. Lighter/faster than product-film (which builds a fuller Remotion film from the design system).
- **How to pull in:** Already installed. Usage: `let's /brag` (or `/brag-slim`) from a project dir; flags `--tone`, `--voice`, `--full`.

---

## 2. UI Component Libraries

### React Bits
- **Link:** https://github.com/DavidHDev/react-bits
- **Type:** Component library (copy-paste, 48k+ stars)
- **What it is:** 200+ free, customizable animations for text, backgrounds, UI, and micro-interactions. Four variants per component (JS-CSS, JS-Tailwind, TS-CSS, TS-Tailwind). Includes creative tools (Background Studio, Shape Magic, Texture Lab). Minimal-dependency, tree-shakeable. Vue + Svelte ports exist.
- **Best used for:** **Landing pages and marketing surfaces** — flashy text/background effects. Heavier WebGL/three.js/GSAP components are overkill for internal tools/CRMs.
- **How to pull in:** Copy-paste, or via shadcn / jsrepo CLI.

### Kobra
- **Link:** https://kobra.systems/
- **Type:** Component library site (React)
- **What it is:** 50+ reusable React components (form controls, navigation, overlays, feedback) plus agent-focused pieces like chat interfaces and code blocks. Styled layer built on top of open-source primitives (input-otp, shadcn). Free tier + Pro.
- **Best used for:** Production React apps needing accessible, animated, ready-made components — including AI/agent chat UIs.
- **How to pull in:** Browse site, copy components (some Pro-gated).

### Beautiful UI
- **Link:** https://www.beautifului.dev/
- **Type:** Component library site (copy-paste)
- **What it is:** 20+ primitives built specifically for **AI-native interfaces** — loading/thinking traces, streaming text, approval cards, chat composer, prompt bar, task rows, recommendation cards, flowcharts, diff displays. Made by Turbo (design studio).
- **Best used for:** Building agent/LLM app surfaces (like Rex, OnIt, Lens chat views) where you need purpose-built AI interaction components.
- **How to pull in:** Copy-paste ready from the site.

### loading-dev
- **Link:** https://github.com/jakubkrehel/loading
- **Type:** Component library (React 19+)
- **What it is:** 28+ animated loading indicators/spinners (Arc, Atom, Blocks, Wave, Orbit, etc.). Customizable size/color/duration, `playState` control, respects reduced motion. MIT. Requires React 19+.
- **Best used for:** Consistent, accessible loading states across React apps. Live previews at loading.dev.
- **How to pull in:** `npm install loading-dev`.

### KokonutUI
- **Link:** https://kokonutui.com/
- **Type:** Component library site (React/Tailwind, open source)
- **What it is:** 100+ open-source React components designed to be consumed by coding agents (agent-friendly copy-paste).
- **Best used for:** General React/Tailwind building blocks in agent workflows — an alternative/complement to shadcn-animated and Kobra.
- **How to pull in:** Copy from the site.

### toggles.dev
- **Link:** https://toggles.dev/
- **Type:** Component snippets (theme toggles)
- **What it is:** A collection of beautiful animated theme (light/dark) toggle icons.
- **Best used for:** Dropping a polished dark-mode toggle into any app instead of a plain switch.
- **How to pull in:** Copy the snippet.

### 21st.dev
- **Link:** https://21st.dev/
- **Type:** Component registry (React/Tailwind/TS, 12,000+ components)
- **What it is:** A community registry of hand-crafted React components, page templates, and shadcn themes. Registry model — code is copied into your project (you own it). Install via shadcn CLI, or paste a prompt so an agent (Cursor/Claude/v0) rebuilds it in your codebase.
- **Best used for:** Designed-from-scratch heroes, pricing tables, and full page templates — agent-ready. Free tier limits daily copies. Complements React Bits / KokonutUI.
- **How to pull in:** shadcn CLI, or agent prompt from the component page.

### 23rd ✅ INSTALLED (skill)
- **Link:** https://github.com/radiumcoders/23rd.dev
- **Type:** shadcn/ui registry + agent skill — **skill installed at `~/.claude/skills/23rd`**
- **What it is:** A small, opinionated collection of ~11 polished shadcn/ui components for React + Svelte 5 — ASCII Fluid, Gooey Color Picker, Shader Gradient, starfield, orb, page-tilt, hero atmospheres, WebGL washes, 404s. Next.js 16 / React 19 / Tailwind 4 / Base UI. Copy-paste, you own the source.
- **Best used for:** Distinctive hero/background flourishes on landing pages (same "landing only, not internal tools" caution as React Bits). The installed skill knows the install commands, props, and when *not* to use each.
- **How to pull in:** Components: `pnpm dlx shadcn@latest add @23rd/<name>`. Skill: already installed.

---

## 3. Design & UI Agent Skills

### emilkowalski/skills
- **Link:** https://github.com/emilkowalski/skills
- **Type:** Agent skill collection (Cursor/Claude)
- **What it is:** 11+ specialized skills encoding UI/design "taste" for agents — animation creation & review, Apple WWDC design principles, UI library selection, Swift, mobile-native web optimization, Sonner toast integration. Premise: "Agents don't have great taste" — these prevent common easing/design mistakes.
- **Best used for:** Giving coding agents production-quality UI judgment. (The `animate` / `animate-expo` / `mobile-native` skills in this stack are already installed globally.)
- **How to pull in:** `npx skills@latest add emilkowalski/skills`.

### visualize
- **Link:** https://github.com/display-dev/visualize
- **Type:** Agent skill (Claude Code, Cursor, Codex, OpenCode, etc.)
- **What it is:** A skill for generating polished, **on-brand HTML artifacts** without the generic AI look. 35 templates (marketing, ops, technical, decision, long-form, data), 40 native design systems + 63 brand styles (Airbnb, Apple, Cohere, Mistral…). `/visualize teach` captures a project's brand into `DESIGN.md` + `PRODUCT.md`; iteration verbs (`polish`, `simplify`, `bolder`, `quieter`, `animate`, `review`); a deterministic slop/accessibility/perf detector.
- **Best used for:** Any AI-generated HTML deliverable that must look branded and intentional — brochures, one-pagers, dashboards, reports (e.g. the Partner Summit HTML brochure, value-prop pages). Strong anti-slop story built in.
- **How to pull in:** Install as an agent skill per the repo README.

---

## 4. Anti-AI-Slop (writing + design)

### no-ai-slop
- **Link:** https://github.com/petergyang/no-ai-slop
- **Type:** Agent skill (ChatGPT / Claude Code)
- **Slop type:** Writing / copy
- **What it is:** Detects and removes 20+ AI writing patterns ("It's not X. It's Y.", "What nobody tells you is…", weasel attribution, corporate jargon) while preserving authentic voice. Edit mode, detect-only mode, and a satire generator. 24 distinct slop categories.
- **Best used for:** Cleaning AI-assisted copy — decks, brochures, UI microcopy, emails — so it reads human. Pairs with the `stop-slop` / `no-ai-slop` writing skills.
- **How to pull in:** `npx` install as a ChatGPT/Claude Code skill.

### uizze.sh
- **Link:** https://uizze.sh/
- **Type:** Agent skill (UI taste)
- **Slop type:** Visual / UI design
- **What it is:** A free "UI taste" skill that stops coding agents shipping AI slop — encodes design judgment so agent-built UI looks intentional.
- **Best used for:** A drop-in taste layer for any agent-built UI. Overlaps the installed `unslop-ui` and emilkowalski taste skills — pick one primary to avoid conflicting rules.
- **How to pull in:** Install the skill from uizze.sh.

### open-design — anti-ai-slop.md
- **Link:** https://github.com/nexu-io/open-design/blob/main/craft/anti-ai-slop.md
- **Type:** Design-standards doc (from `nexu-io/open-design`, 97.9k stars)
- **Slop type:** Visual / UI design
- **What it is:** A tiered, enforceable checklist for making UI look human-crafted, not template-AI. **P0 Cardinal Sins** (no default Tailwind indigo, no gradient hero, SVG icons not emoji, design-system fonts, no "AI dashboard tile" patterns, no unverified metrics, no filler copy), **P1 Soft Tells** (vary the Hero→Features→Pricing order, no placeholder-image CDNs, limit raw hex, cap accent usage), **P2 Polish Tells**. Guiding principle: ~80% proven patterns + ~20% distinctive choice.
- **Best used for:** A pre-ship rubric for any landing page / dashboard UI to strip visual AI-slop. Complements the installed `unslop-ui` / `no-ai-slop` skills. Parent repo `nexu-io/open-design` is worth browsing as a broader design-standards reference.
- **How to pull in:** Read the doc as a checklist, or feed it to an agent as design rules.

---

## 5. Skill Directories / Discovery

### awesome-claude-skills
- **Link:** https://github.com/travisvn/awesome-claude-skills
- **Type:** Curated awesome-list (meta-resource)
- **What it is:** A curated directory of Claude skills — official Anthropic skills (docs, design, dev, comms), community skills (browser automation, security testing, iOS, etc.), creation guides, best practices, and guidance on when to use Skills vs MCP / prompts / subagents.
- **Best used for:** Discovering new skills to install, and as a reference when building custom skills. Check here first when hunting for a skill that solves a recurring task.
- **How to pull in:** Browse the list; install linked skills per their own instructions.

### Skill hubs — ui-skills.com & skills.sh
- **Links:** https://ui-skills.com · https://skills.sh
- **Type:** Skill marketplaces / directories
- **What they are:** Two hubs that host installable UI/design/dev agent skills (the sources behind the kail_designs lists below).
- **Best used for:** Browsing and installing individual UI-craft skills.

### kail_designs — curated UI-skill lists (X threads)
- **Links:** https://x.com/kail_designs/status/2102265246325047711 · https://x.com/kail_designs/status/2102687065720926651
- **Type:** Curated skill lists (reference)
- **What they are:** Two threads by @kail_designs recommending UI/design agent skills he uses regularly.
  - **List 1 — "make your UI look better instantly":** frontend-design, apple-design, beautiful-shadows, accessibility, design-review, emil-design-eng, shadcn, adapt, better-interface, interaction-design (all on ui-skills.com).
  - **List 2 — specific purposes:** web-design-guidelines (Vercel Labs), minimalist-ui, caveman (token-saving compressed mode), brandkit (brand-kit image gen), claude-handoff, critique (design critique), firecrawl-search, seo-audit, ai-seo (all on skills.sh).
- **Best used for:** A shortlist of vetted UI/design/SEO skills to evaluate. Note overlap with what's already installed (apple-design / emil-design-eng ≈ emilkowalski/skills; shadcn; design-review).
- **How to pull in:** Install individual skills from ui-skills.com / skills.sh as needed.

### csaba_kissi — anti-slop UI toolkit (X thread)
- **Link:** https://x.com/csaba_kissi/status/2103015949058400497
- **Type:** Curated resource list (reference)
- **What it is:** 5 picks — **uizze.sh** (UI taste anti-slop skill), **reactbits.dev** (already catalogued as React Bits), **kokonutui.com** (100+ agent-ready React components), **toggles.dev** (theme toggle icons), **obra/superpowers** (repeatable agent dev workflow). All five are catalogued individually above.
- **Best used for:** Source thread; the individual entries are the actionable version.

### DevDsgn — 5 design skills (X thread)
- **Link:** https://x.com/DevDsgn/status/2103043406549364891
- **Type:** Curated skill list (reference)
- **What it is:** 5 design skills — Anthropic Frontend Design (`anthropics/skills`), UI/UX Pro Max (`nextlevelbuild…`), Taste Skill (`Leonxlnx/taste`), Impeccable (`pbakaus/impeccable`), Designer Skills (`Owl-Listener/…`).
- **Best used for:** More UI-taste skills to evaluate. Heavy overlap with what's installed and with the kail_designs lists (Anthropic Frontend Design ≈ frontend-design; Taste ≈ minimalist-ui/brandkit source; Impeccable ≈ critique). Treat as candidates, install at most one taste skill to avoid conflicting rules.
- **How to pull in:** Install individual skills from their repos.

---

## 6. Code Quality & Vibe-Coding Discipline

De-slopping *code* (not copy or visuals) and keeping AI-assisted codebases maintainable. Two flavours: **analyzers/cleaners** that find and fix debt, and **rulesets** that prevent it up front.

### debtmap
- **Link:** https://github.com/iepathos/debtmap
- **Type:** CLI analyzer (Rust)
- **What it is:** A technical-debt analyzer that scores and ranks bug hotspots across complexity, test-coverage gaps, git-history churn, coupling, and code purity. Languages: Rust, Python, JS, TS, Go, Solidity. Outputs TUI, JSON, Markdown (for LLMs), Graphviz.
- **Best used for:** Finding *where* to refactor first; JSON/Markdown export into CI or an agent workflow.
- **How to pull in:** Install the Rust CLI; run against a repo.

### desloppify
- **Link:** https://github.com/peteromallet/desloppify
- **Type:** AI agent framework (Python 3.11+)
- **What it is:** A scan → AI-review → triage → fix → rescan loop that turns "slop code" into engineered code. Mechanical detection (dead code, duplication, complexity) plus LLM review of naming/abstractions/module boundaries. State persists in `.desloppify/`. 29 languages, GitHub scorecard badges, CI health gates.
- **Best used for:** Systematically upgrading a quickly-built codebase beyond what linting catches.
- **How to pull in:** Python package; runs as an agent loop.

### vibe-audit (interactive feature cleanup)
- **Link:** https://mcpmarket.com/tools/skills/vibe-audit-interactive-feature-cleanup
- **Type:** Agent skill
- **What it is:** Interactive dead-code / abandoned-experiment / orphaned-file audit. Presents findings one-by-one with git-history context and lets you decide keep/deprecate/remove — safety-first, no auto-delete.
- **Best used for:** Pruning experimental features and unused components after prototyping sprints.
- **How to pull in:** Install the skill from MCP Market.

### vibe code cleanup (andyfischer gist)
- **Link:** https://gist.github.com/andyfischer/7e064cf1672e32377cfe224b91bda82a
- **Type:** Skill / checklist (gist)
- **What it is:** An 8-point cleanup guide for AI-generated code — move complex inline types to top level, un-inline imports, dedupe, drop unnecessary backwards-compat, remove journal-style / verbose comments.
- **Best used for:** A quick pre-PR pass over code generated in a session.
- **How to pull in:** Copy as a skill / reference checklist.

### Vibecodex — vibe-coding-rules
- **Link:** https://github.com/yerdaulet-damir/vibe-coding-rules
- **Type:** Ruleset + reference apps (CLAUDE.md / .cursor/rules / .claude/skills)
- **What it is:** 54 production architecture rules for AI-assisted coding across FastAPI (Python), Next.js 15 (TS), and Go 1.22+ — hexagonal architecture, idempotency, feature colocation, RSC, consumer-side interfaces, graceful shutdown. Ships pre-built config dirs agents auto-load, plus three working reference apps.
- **Best used for:** Dropping guardrails into a project so the agent enforces production patterns every session (prevents 1400-line god files). Note: opinionated toward FastAPI/Next/Go — adapt for other stacks.
- **How to pull in:** Copy the `CLAUDE.md` / `.cursor/rules` / `.claude/skills` into a project.

### karpathy vibe-to-agentic
- **Link:** https://github.com/LearnPrompt/andrej-karpathy-skills/blob/main/karpathy-vibe-to-agentic/SKILL.md
- **Type:** Agent skill (from `andrej-karpathy-skills`)
- **What it is:** A protocol for taking a working prototype to production: (1) audit for hidden assumptions/failure modes, (2) define GIVEN/WHEN/THEN success criteria, (3) incrementally clean up with the agent while the human keeps judgment. "Vibe coding raises the floor; agentic engineering raises the ceiling." Parent repo collects skills from Karpathy's posts.
- **Best used for:** The moment a prototype "kind of works" and needs to become maintainable.
- **How to pull in:** Install the skill from the repo.

### obra/superpowers
- **Link:** https://github.com/obra/superpowers
- **Type:** Agent skill collection
- **What it is:** Open-source skills that give coding agents a repeatable dev workflow (rather than improvising each session).
- **Best used for:** Standardizing how an agent plans, edits, and verifies across a project.
- **How to pull in:** Install per the repo README.

---

## 7. Specialized Skills

### before-skills — ASO (App Store Optimization)
- **Link:** https://github.com/alexszczurek/before-skills
- **Type:** Agent skill
- **What it is:** An ASO skill for writing and auditing iOS App Store listings — names, subtitles, keyword fields, screenshots, localization, featuring. Follows a fixed 6-step keyword process instead of guessing; rules carry their reasoning and are marked Apple-confirmed vs industry-inferred; reflects 2025–2026 App Store guidelines.
- **Best used for:** Any iOS app listing (e.g. if OnIt or a future app ships to the App Store).
- **How to pull in:** `npx skills add alexszczurek/before-skills`.

### TypeLLM
- **Link:** https://github.com/TypeLLM/TypeLLM
- **Type:** Python library (NOT a skill) — *not installed; per-project*
- **What it is:** Type-safe structured generation for LLMs without touching model weights — constrain outputs to schemas (str/int/bool/enum), optional thinking/budget, vision, field dependency graphs, probability distributions, option-order-bias reduction via permutation averaging. Built on SGLang; runs against a GPU server (Qwen3 variants etc.). Apache 2.0.
- **Best used for:** Reliable structured extraction/classification in an LLM app where you self-host a model. Overkill unless you're running SGLang on a GPU; for hosted Claude, prefer Anthropic tool-use / structured outputs.
- **How to pull in:** Per-project into a venv: `pip install -U typellm` + point at an SGLang server. Not installed globally (would pull heavy deps and needs a GPU server to be useful).

---

## 8. 3D & Interactive Web Graphics

Heavier creative tools for standout visuals — landing pages and marketing surfaces, not internal tools.

### Spline
- **Link:** https://spline.design/
- **Type:** Browser-based 3D design tool
- **What it is:** Create interactive 2D/3D scenes (animation, physics, particles) with AI-assisted and manual tools. Exports to web (HTML/JS, React, Next.js), iOS, Android; integrates with Webflow, Framer, Wix.
- **Best used for:** 3D hero scenes, animated brand objects, gamified marketing moments. Watch bundle weight on real pages.
- **How to pull in:** Design in the app, embed via its React/JS component or exported asset.

### Unicorn Studio
- **Link:** https://unicorn.studio/
- **Type:** Interactive-graphics tool ("craft interactive graphics that ship")
- **What it is:** Build dynamic, interactive visual effects for the web without hand-coding shaders/canvas work; export to embed on live pages.
- **Best used for:** Eye-catching animated backgrounds and interactive hero effects on marketing sites.
- **How to pull in:** Create in-app, embed the generated snippet.

### paper.design
- **Link:** https://paper.design/
- **Type:** Design-to-code canvas (MCP / agent-connected)
- **What it is:** A "connected canvas for teams shipping with agents" — designs export as HTML/CSS and agents sync changes back, bidirectionally. Works with real data (not lorem), connects to IDEs/CLI/agents over MCP. Used by Vercel, Perplexity, Tailwind Labs, PostHog.
- **Best used for:** Closing the design→code gap on web-standards projects where an agent does the boilerplate. Strong fit given the agent-first workflow across these projects.
- **How to pull in:** Design in Paper, connect via MCP to the coding agent.

---

## 9. Design Assets & Inspiration

Non-code resources — fonts, galleries, portfolio media.

### bestfreefonts.com
- **Link:** https://bestfreefonts.com/
- **Type:** Font directory
- **What it is:** A curated selection of ~214 free fonts organized by category (sans, serif, display, script, mono).
- **Best used for:** Sourcing a typeface fast without licensing hassle. Confirm each font's license before commercial use.
- **How to pull in:** Download from the listing.

### Inspora
- **Link:** https://inspora.design/
- **Type:** Design-inspiration gallery
- **What it is:** Curated design work across Web, Branding, Product, Motion, Illustration, 3D, Print.
- **Best used for:** Reference and direction-setting before designing a new UI or brand surface.
- **How to pull in:** Browse.

### Reelfolio
- **Link:** https://reelfolio.io/
- **Type:** Showreel generator (paid)
- **What it is:** Turns screenshots / screen recordings into polished animated showreels — 200+ motion templates, multiple aspect ratios, 1080p/4K export, commercial rights.
- **Best used for:** Portfolio, social, and client-presentation reels of a shipped product without video-editing work.
- **How to pull in:** Upload assets in-app; ~$108/yr for watermark-free export.

---

## Quick pick guide

| Need | Reach for |
|------|-----------|
| Tokenized CSS transitions | transitions.dev |
| Animated shadcn components | shadcn-animated |
| Landing-page eye candy | React Bits |
| General React components (incl. chat UI) | Kobra |
| AI-app interface primitives | Beautiful UI |
| Loading spinners | loading-dev |
| Give an agent UI taste | emilkowalski/skills |
| De-slop AI writing | no-ai-slop |
| De-slop AI visual/UI design | open-design — anti-ai-slop.md |
| Branded HTML artifacts (no AI look) | visualize |
| Find where the code debt is | debtmap |
| Auto-clean code slop (agent loop) | desloppify |
| Prune dead code / abandoned features | vibe-audit |
| Quick pre-PR code cleanup pass | vibe code cleanup (andyfischer gist) |
| Guardrails so the agent writes prod code | Vibecodex |
| Take a prototype to production | karpathy vibe-to-agentic |
| Repeatable agent dev workflow | obra/superpowers |
| More agent-ready React components | KokonutUI |
| Dark-mode toggle icon | toggles.dev |
| Stop agent shipping UI slop | uizze.sh |
| iOS App Store listing (ASO) | before-skills |
| Registry of agent-ready components | 21st.dev |
| Code-driven cinematic / 3D animation | Theatre.js |
| Product video / launch reel (in code) | product-film ✅ installed |
| Fast "show what I built" launch clip | brag / brag-slim ✅ installed |
| Distinctive shadcn hero/background bits | 23rd ✅ installed |
| Type-safe LLM output (self-hosted GPU) | TypeLLM |
| 3D hero scene | Spline |
| Interactive animated background | Unicorn Studio |
| Design→code with an agent (MCP) | paper.design |
| Free fonts | bestfreefonts.com |
| Design inspiration | Inspora |
| Turn screenshots into a showreel | Reelfolio |
| Discover more Claude skills | awesome-claude-skills, ui-skills.com, skills.sh, kail_designs / csaba_kissi / DevDsgn lists |
