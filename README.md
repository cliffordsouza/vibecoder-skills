# Vibecoder Skills — reusable UI / motion / design / code-quality resources

A personal catalog of external libraries, component collections, and agent skills to pull from across projects. Curated by Cliff.

Each entry: **what it is**, **best used for**, and **how to pull it in**.

> Note on "skills": some of these ship as installable **agent skills** (Cursor/Claude Code), some are **npm/CLI component libraries**, and a couple are **browse-and-copy component sites**. The type is labelled per entry. Entries marked **✅ INSTALLED** are global agent skills already in `~/.claude/skills/`; everything else is a project library / tool / site you pull in when needed.

> **Index skill:** a global `vibecoder-skills` skill (`~/.claude/skills/vibecoder-skills`) mirrors this catalog as a quick router, so the agent is catalog-aware in every project and pick-and-chooses the right resource per task. Keep its `SKILL.md` in sync when this file changes.

> **Proactive suggestions:** when building an app/tool/dashboard/website whose type or aesthetic matches an entry here, the agent surfaces the relevant resources up front (a short 1–3 pick shortlist with why each fits) rather than waiting to be asked — honouring the per-category cautions. Standing ask from Cliff (2026-10-12).

> **Anti-slop house rule (always on):** never use the AI "eyebrow" section-header — small all-caps + wide letter-spacing in a muted/desaturated accent tint (the pattern itself is the tell, on any background; e.g. a light-blue tracked-out `WHERE RADIX STANDS`). It's a clear giveaway of AI/Claude-built UI. Use sentence/Title-case headings with real size/weight/color hierarchy instead. Standing rule from Cliff (2026-10-12); the installed `unslop-ui` + `open-design anti-ai-slop.md` cover the wider tell list.

Last updated: 2026-10-08

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

### Annimate ⬇️ starter pack vendored
- **Link:** https://annnimate.com/ · free pack vendored here: `vendor/annimate-starter-pack/`
- **Type:** GSAP animated-component library (React / Vue / plain HTML) — copy-paste or MCP. Not a skill. Free 16-component starter pack (vendored); full 118 is paid (Solo €87/qtr or €240/yr; Reveal Kit / Menu Kit €149 one-time each).
- **What it is (vendored 16):** text-reveal, accordion, dual-scramble, curtain-slider, scale-slider, split-flap-board, magnetic-tag-cloud, process-rail, echo-headline, pricing (digit-roll + monthly/yearly), rotating-words, elastic-divider, feature-dialog, image-fly-in, ascii-overlay, multi-level-drawer-menu. Each folder has `.jsx` / `.vue` / `.html`+`.css`+`.js` + an `example` (previews stripped — watch them on the site).
- **Best used for:** Scroll/hero motion + flashy sections on **landing/marketing surfaces** (GSAP-heavy — landing only, not internal tools, same as React Bits). Needs GSAP (`npm i gsap @gsap/react`); a few need `three`.
- **How to pull in:** Copy from `vendor/annimate-starter-pack/<component>/` into the project. Full library via annnimate.com copy or its MCP (paid).

### Arc / uiarc.dev
- **Link:** https://uiarc.dev/
- **Type:** React UI library + blocks (shadcn CLI / copy / MCP) — source lands in your project. Not a skill. Free tier browsable + installable; **Arc Pro $199 one-time** for the Pro components/blocks.
- **What it is:** 163 components (line chart, date range picker, command palette…) + 91 **blocks** (dashboards, checkout, inbox triage). "The React UI library your AI agents can build with" — every item has a Markdown doc page + an `llms.txt` index for agents. You own + edit the source/tokens/motion.
- **Best used for:** Real app UIs *and* internal tools (unlike the landing-only motion libs) — especially the blocks for dashboards/checkout/inbox flows. A broad general-purpose alternative to 21st.dev.
- **How to pull in:** shadcn CLI add, copy source, or connect the Arc MCP (interactive `/mcp`).

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

### motion-graphics-music-video (makevoid)
- **Link:** https://github.com/makevoid/motion-graphics-music-video-skill (no-AI-model variant: https://github.com/makevoid/motion-graphics-music-video-skill-noimage)
- **Type:** Claude Code plugin + agent skill (MIT) - not installed
- **What it is:** Turns **a song + a creative prompt** into a full animated **character music video**. Researches the brief, writes a PLAN.md (characters, scenes, cost estimate) for approval, then generates in reviewed sub-agent waves: GPT Image 2.5 character sheets, MiniMax H3 animation on green screen, p5.js motion graphics/overlays (lights, smoke, paper, riso FX), Python audio analysis/stems/cutouts, Swift VFX, FFmpeg assembly. Paid via fal.ai (~$30 + ~3M Opus tokens for a ~3 min song). Needs Ruby 3.2+, Node 22+, Python, FFmpeg, ImageMagick; Swift optional. Author notes it runs better from the terminal than the desktop app.
- **Best used for:** Stylised, character-driven music videos and fun viral-style clips where AI-generated characters are the point. **Not** for brand/partner reels that need real people's likenesses, exact domains/numbers or official logos - use product-film there (assessed for the Radix "Off the Bench" partnerships reel, 2026-10-07). Its p5 FX sketches and beat/energy analysis are worth borrowing on their own.
- **How to pull in:** In a terminal: `claude plugin marketplace add makevoid/motion-graphics-music-video-skill` then `claude plugin install motion-graphics-music-video@makevoid-music-video --scope user`; set the fal key via `/plugin configure motion-graphics-music-video`; run `/motion-graphics-music-video:motion-graphics-music-video` and supply song + prompt.

---

## 2. UI Component Libraries

### React Bits
- **Link:** https://github.com/DavidHDev/react-bits
- **Type:** Component library (copy-paste, 49k+ stars; license MIT + Commons Clause, so you can use it in products but not resell the components themselves). No agent skill; the site is `reactbits.dev`.
- **What it is:** 200+ free, customizable animations for text, backgrounds, UI, and micro-interactions. Four variants per component (JS-CSS, JS-Tailwind, TS-CSS, TS-Tailwind). Includes creative tools (Background Studio, Shape Magic, Texture Lab). Minimal-dependency, tree-shakeable. Vue + Svelte ports exist.
- **Best used for:** **Landing pages and marketing surfaces** — flashy text/background effects. Heavier WebGL/three.js/GSAP components are overkill for internal tools/CRMs.
- **How to pull in (per project):** `npx shadcn@latest add @react-bits/SplitText-TS-TW` (suffix picks the flavour: JS or TS, then CSS or TW), or `npx jsrepo@latest add https://reactbits.dev/r/SplitText-TS-TW`, or copy from a component's Code tab. **MCP route:** it works through the shadcn MCP server; add the `@react-bits` registry to `components.json`, then `npx shadcn@latest mcp init --client claude` inside the project (see https://reactbits.dev/get-started/mcp).

### Kobra
- **Link:** https://kobra.systems/
- **Type:** Component library site (React)
- **What it is:** 50+ reusable React components (form controls, navigation, overlays, feedback) plus agent-focused pieces like chat interfaces and code blocks. Styled layer built on top of open-source primitives (input-otp, shadcn). Free tier + Pro.
- **Best used for:** Production React apps needing accessible, animated, ready-made components — including AI/agent chat UIs.
- **How to pull in:** Browse site, copy components (some Pro-gated).

### Beautiful UI
- **Link:** https://www.beautifului.dev/ · repo: https://github.com/slev12397/beautiful-ui
- **Type:** Component library site + shadcn registry (copy-paste; **no skill** — nothing to install globally)
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

### Amicro (micro-interactions) — library only
- **Link:** https://github.com/Subhan-code/Amicro--Micro-transitions- · demo: amicro.vercel.app
- **Type:** React component collection (copy-to-code TSX / shadcn registry) — npm `@subhanhq/amicro`, 2.6k⭐, MIT. (Ships an `amicro-design-system` skill but it's scoped to building the Amicro repo itself — **not installed**, no benefit in our projects.)
- **What it is:** Micro-interactions, transitions, hover/text effects, hooks, and **12 card layouts** (arc fan, linear/corner fan, stamp arc, cascade stagger, wheel fan, interactive + CoverFlow carousels, "Time Machine" card stack). Hardware-accelerated, built on Motion (`motion/react`) / framer-motion. React 18/19, Tailwind 3/4.
- **Best used for:** Eye-catching card galleries, carousels, and micro-interactions — **landing/marketing surfaces** (same caution as React Bits; the fancy card fans are overkill for internal tools). Copy-to-code = no runtime dep.
- **How to pull in (per project):** `npx @subhanhq/amicro@latest init` then `add <component>` (e.g. `card-arc-5`); or shadcn registry `@amicro` → `npx shadcn add @amicro/tilt-card`.

### fluid-functionalism ✅ INSTALLED (skill)
- **Link:** https://github.com/mickadesign/fluid-functionalism
- **Type:** shadcn registry (~30 components) + agent skill — **skill installed at `~/.claude/skills/fluid-functionalism`** (1k+ stars)
- **What it is:** A motion-forward shadcn/ui registry — spring-based motion (not durations), a fluid hover highlight that glides to the nearest item, Radix *and* Base UI flavours, blocks (app sidebar, settings dialog) and presets. Next.js 15 / React 19 / Tailwind 4 / Framer Motion. Load Inter with its `opsz` axis for weight animations.
- **Best used for:** Polished, legible state-change motion on real app UIs (not just landing pages) — a good fit given the standing "apply motion wherever applicable" rule. The installed skill knows the registry + install commands.
- **How to pull in:** Registry: `npx shadcn@latest registry add @fluid` then `npx shadcn@latest add @fluid/<item>` (prefix `base/` for Base UI). Skill: already installed.

### mdxcn ✅ INSTALLED (skill)
- **Link:** https://github.com/shadcn-labs/mdxcn · mdxcn.dev
- **Type:** MDX component library (shadcn-compatible registry) + agent skill — **skill installed at `~/.claude/skills/mdxcn`** (MIT)
- **What it is:** Markdown-friendly React components for MDX — callouts, steps, terminals, **text-based charts/diagrams drawn with glyphs (not SVG/canvas)**, and timelines. Customizable corners, glyphs, palettes, accents; TypeScript props; shadcn CLI + `registry.json`.
- **Best used for:** Docs, READMEs, changelogs, and content-heavy pages where you want callouts/steps/terminals and lightweight ASCII-style charts inline in MDX.
- **How to pull in:** Copy via the shadcn CLI from mdxcn.dev, or use the installed skill.

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

### lintapple (UI linter)
- **Link:** https://github.com/gholtzap/lintapple · demo: lintapple.vercel.app
- **Type:** CLI tool + Playwright integration (npm, Node 22+, MIT, 333⭐) — *per-project, not a global skill*
- **What it is:** A UI quality linter — "it should be impossible for AI to make a bad UI." Checks a **running page** against a `ui-policy.json`: fonts, text sizes, contrast, control sizes, screen bounds (spacing/alignment/equal-digit-widths/corner-radii need `data-ui-*` attrs). Each finding = rule + element + measured value + suggested fix. Exit 0 pass / 1 findings / 2 error.
- **Best used for:** A mechanical gate against AI-looking/sloppy UI — pairs directly with the anti-slop house rule. Encode the project's type scale, contrast, and control sizes once, then fail CI on drift. Can run in Playwright via `expectUI(page, testInfo)`.
- **How to pull in (per project):** `npm i -D lintapple && npx lintapple init` → set fonts/sizes + app URL in `ui-policy.json` → `npm run lint:ui` (or `npx lintapple <url> --json`, `--ready <selector>` for async pages).

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

### Inspiration galleries & directories (browse-only — no code/skill)
Direction-setting references before a new UI/brand surface. All browse-only; I can fetch specific listings/categories on request. For something *actionable* (a style you can apply), use Refero Styles below.
- **mkdir.directory** (https://mkdir.directory/) — **start here**: a directory of ~30 inspiration galleries; use it to pick the right gallery for the job. Most are generic "pretty site" galleries (Awwwards, Siteinspire, Land-book, The FWA, CSS Design Awards) that overlap Inspora/SEESAW — but it also indexes **element/section-specific** ones worth grabbing targeted refs from mid-build: **CollectUI** (by element), **Navbar Gallery**, **Footer.design**, **404s**, **Unsection** (page *sections* — pairs with the anti-slop header rule), **One Page Love** / **SaaS Landing Page** / **Saaspo** (landing), **Dark Mode Design**, **GSAP/Lenis Showcase** (motion). No need to catalog these individually — reach them through mkdir.
- **DesignEng** (https://www.designeng.tools/) — ~190 design-engineering resources by category, **plus free on-site utilities worth using mid-build: fluid type scale, fluid space scale, contrast checker, OKLCH palette generator, easing generator.**
- **Inspora** (https://inspora.design/) — curated work across Web, Branding, Product, Motion, Illustration, 3D, Print.
- **SEESAW** (https://www.seesaw.website/) — hand-picked sites, daily, filterable (Design, Portfolios, AI, Fintech…); lots of portfolios + new launches.
- **recent.design** (https://recent.design/) — broad across mediums: web/branding/motion/illustration/poster/print, launch videos, OG images, app screenshots & icons.

### Emergent Mind Labs - canvas demos and chart prompts (browse + copy a prompt)
Two galleries from the same maker. Neither has an API, MCP server, skill or installable code; the value is a working reference plus a prompt you paste into a coding agent. No licence is stated, so rebuild from the idea instead of copying their prompt or source into a product.
- **500 canvas demos** (https://www.emergentmind.com/visualizations): "500 Things You Can Make with JavaScript and Canvas". Every demo is one `<canvas>`, no WebGL, no libraries. Filter by category (physics, math, algorithms, machine learning, generative art, 3D, fluids, sound, simulation, emergence, fractals, games). Each demo page has a **Copy prompt** (single-file build, a "start simple" list, then a "make it beautiful" list) and a view-source link.
- **1,337 chart prompts** (https://www.emergentmind.com/chart-prompts): 1,337 line and bar chart styles (669 light, 668 dark) with illustrative data. Open any style at full size and copy a prompt that describes colours, type, spacing and marks so any agent and any charting library can reproduce the look.
- **Best used for:** giving a dashboard chart a distinct look instead of the library default; starting a canvas, physics or generative piece from a reference that already works.
- **How to use it:** browse, pick a style, then write your own prompt in the same shape (see the Chart lab page on the site, which does this with six original styles).

### Refero Styles ⭐ (actionable, not just browse)
- **Link:** https://styles.refero.design/
- **Type:** AI-readable design-system gallery + **MCP connector** (DESIGN.md per style)
- **What it is:** 2,000+ product-website styles, each with a **`DESIGN.md`** capturing colors, typography, spacing, and components — "AI-readable design systems from leading product websites." Sort by Trending/Popular/Newest. Ships an **MCP connection** for Claude/Cursor/Codex/v0/Lovable, plus DESIGN.md examples and design prompts. Beta, updated weekly.
- **Best used for:** Unlike the pure galleries, this is usable *mid-build* — pull a reference site's `DESIGN.md` as a concrete style brief to steer a new UI, or connect its MCP for live access. Strong fit for matching a target aesthetic fast.
- **How to pull in — three options:**
  1. **Free, no account:** grab a style's `DESIGN.md` from the site and feed it as design rules. (I can fetch one on request.)
  2. **Refero MCP** (145k+ screens, 12k+ user flows — live, agent-queryable). **Requires a Refero Pro subscription (~$45/quarter or annual); MCP access is Pro-only.** Steps: open https://refero.design/mcp → "Connect your tool" → pick **Claude Code** → copy the one-line config it shows and add it (this is an interactive-terminal step: `/mcp`, not doable from the desktop Code chat) → **restart** the tool → the first Refero call opens a browser to **sign in with your Refero account**, automatic after. Then ask e.g. "Find onboarding flows from fintech apps."
  3. **Refero Skill** ✅ INSTALLED (free, open source): `npx skills add https://github.com/referodesign/refero_skill` — installed as `~/.claude/skills/refero-design`. A research-first design *methodology* (research references → extract patterns → design with craft rules for type/color/spacing/motion). Reference-fetching is strongest when the Pro MCP is connected (not currently).
- **⚠️ Caveat on the skill:** it declares itself the *primary/default* UI-design skill and makes reference-research *mandatory* — it will try to drive any UI task and may conflict with the standing UI-craft stack (emil `animate`/`mobile-native` + `transitions-dev`/`transitions-polish` + `unslop-ui`). Without the Pro MCP its unique value (145k real screens) is unavailable, leaving methodology that overlaps that stack. Remove if it gets in the way: `rm -rf ~/.claude/skills/refero-design`.
- **Note:** The gallery + MCP themselves aren't an installed skill; option 3 is. All surfaced via the `vibecoder-skills` index.

### Reelfolio
- **Link:** https://reelfolio.io/
- **Type:** Showreel generator (paid)
- **What it is:** Turns screenshots / screen recordings into polished animated showreels — 200+ motion templates, multiple aspect ratios, 1080p/4K export, commercial rights.
- **Best used for:** Portfolio, social, and client-presentation reels of a shipped product without video-editing work.
- **How to pull in:** Upload assets in-app; ~$108/yr for watermark-free export.

---

## 10. Skill Collections & Bulk Installs (from @FareaNFts 20-repo list)

Source: https://x.com/FareaNFts/status/2103564316029120624 — a "20 trending repos this week" list (NOT a curated skill set). Handled skills-only: installed the genuine Claude Code agent skills, catalogued the rest, skipped platforms/libraries (PyTorch, Odoo, quiche, cline, self-hosted services).

### security-audit ✅ INSTALLED
- **Link:** https://github.com/cloudflare/security-audit-skill
- **Type:** Agent skill — **installed at `~/.claude/skills/security-audit`**
- **What it is:** Turns the agent into a security auditor — vulnerability review across web/auth, client-side, cloud, supply-chain, memory-safety, LLM/AI attack classes, with a full audit workflow + findings schema/validators.
- **Best used for:** Security passes on any project before deploy (OnIt, Rex, the portals). Gate the full workflow behind an explicit "audit" request.

### addyosmani/agent-skills ✅ INSTALLED (25 skills)
- **Link:** https://github.com/addyosmani/agent-skills
- **Type:** Agent skill collection — **all 25 installed to `~/.claude/skills/` (original names)**
- **What it is:** General production-engineering workflows: TDD, debugging-and-error-recovery, planning-and-task-breakdown, incremental-implementation, code-review-and-quality, performance-optimization, frontend-ui-engineering, context-engineering, spec-driven-development, shipping-and-launch, and 15 more.
- **Best used for:** Disciplined build workflow across all projects. Reinstall: `npx skills add addyosmani/agent-skills`.

### anthropics/knowledge-work-plugins ✅ INSTALLED (cherry-picked 14 of 252)
- **Link:** https://github.com/anthropics/knowledge-work-plugins
- **Type:** Plugin/skill mega-collection — installed **14 namespaced `kw-*` skills** (initially all 252, then pruned 2026-09-27 to cut context bloat and dedupe against Addy's higher-starred set + the design plugin).
- **Kept (14):** data → `kw-data-build-dashboard`, `kw-data-sql-queries`, `kw-data-data-visualization`, `kw-data-explore-data`, `kw-data-analyze`, `kw-data-statistical-analysis`, `kw-data-validate-data`; finance → `kw-finance-financial-statements`, `kw-finance-reconciliation`, `kw-finance-variance-analysis`; product → `kw-product-management-metrics-review`, `kw-product-management-roadmap-update`, `kw-product-management-product-brainstorming`; marketing → `kw-marketing-seo-audit`. These map to the Tableau/BigQuery dashboards, rebate/MDF/pricing finance, and product work.
- **Dropped (238):** all engineering (covered by Addy's 25), all design (covered by the `design:*` plugin + gstack), and irrelevant domains (Zoom SDKs, small-business, HR, legal, sales, bio-research, ops).
- **Note:** For any dropped skill later, grab its folder from the repo, or install the whole thing namespaced via `/plugin marketplace add anthropics/knowledge-work-plugins` in an interactive terminal.

### anthropics/financial-services — catalog only (not installed)
- **Link:** https://github.com/anthropics/financial-services
- **Type:** Finance plugin/skill collection (112 skills)
- **What it is:** Capital-markets skills — equity research, bond futures basis, swap-curve strategy, valuation review, NAV tie-out, IC memos, tear sheets (S&P, LSEG partner-built). Mostly buy-side/sell-side finance, not Radix's domain economics.
- **Best used for:** Cherry-pick if ever needed (e.g. `xlsx-author`, `ic-memo`). Install a single skill by copying its folder, or the whole plugin via marketplace.

### affaan-m/ECC — catalog only (not installed)
- **Link:** https://github.com/affaan-m/ECC
- **Type:** Personal skill mega-collection (**903 skills**)
- **What it is:** A huge grab-bag (homelab VLANs, energy procurement, Swift concurrency, Django/Go/Kotlin patterns, brand voice, agent orchestration…). Not installed — bulk-installing 903 would swamp context.
- **Best used for:** Browse and copy an individual `skills/<name>` folder if one is a perfect fit.

### Not installed (per-project tools / platforms from the same list)
Per-project dev tools — pull into a specific project as needed: alibaba/open-code-review, stablyai/orca (agents in worktrees), vectorize-io/hindsight (cross-session agent memory), Fission-AI/OpenSpec (spec-driven dev), superdesigndev/treg (agent-tool gateway), davila7/claude-code-templates (`npx claude-code-templates`).
Apps / libraries / platforms — not skills: anthropics/claude-code (already running), cline/cline (VS Code ext), cloudflare/quiche (Rust QUIC), odoo/odoo (ERP), pytorch/pytorch (ML), Tencent/WeKnora + TencentCloud/Octop (self-hosted services), paperclipai/paperclip (agent dashboard).

---

## 11. From @neerajjj6785 "Top 10 OpenCode skill repos"

Source: https://x.com/neerajjj6785/status/2104895659157684597 (2026-09-29). Scanned all 10; installed the additive/relevant, skipped duplicates. (Star counts on this list looked inflated, so decisions weighted relevance + non-duplication over raw stars.)

**Installed (trimmed to cores):**
- **Ponytail** ✅ — https://github.com/DietrichGebert/ponytail — anti-over-engineering "lazy senior dev" decision-ladder. Kept `ponytail`, `ponytail-review`, `ponytail-audit`, `ponytail-help` (dropped debt/gain scoreboards). Install: `npx skills add DietrichGebert/ponytail -g`.
- **Caveman** ✅ — https://github.com/JuliusBrussee/caveman — token-saving compressed output. Kept `caveman`, `caveman-compress`, `caveman-help` (dropped the ~10 "Caveman Cloud" telemetry skills + the bundled `cavecrew` workflow set, which duplicated Addy's). Install: `npx skills add JuliusBrussee/caveman -g`.
- **Archify** ✅ — https://github.com/tt-a1i/archify — description → interactive standalone-HTML diagrams (architecture/workflow/sequence/dataflow/lifecycle). Kept `archify`, `archify-review`. Fits the HTML-artifact work (brochures, showreels). Install: `npx skills add tt-a1i/archify -g`.

**Skipped (with reason):**
- **Understand-Anything** (Egonex-AI) — same type as a codebase→knowledge-graph tool; deduped in favour of Graphify.
- **Graphify** (Graphify-Labs) — codebase→knowledge graph, but it's a **pip tool** (`pip install graphifyy` + `graphify install`); not installed globally (needs Python + per-project setup, like TypeLLM). Pull it into a project when you actually want to graph a repo.
- **UI/UX Pro Max** (nextlevelbuilder) — design-system generator; overlaps the standing UI stack (emil/animate/unslop-ui/uizze). Skipped to avoid conflicting design rules.
- **Superpowers** (obra) — workflow mega-collection that duplicates Addy's 25 (installed). Would be a swap, not an add.
- **Impeccable** (pbakaus) — design critique; covered by the `design:*` plugin + gstack `design-review`.
- **Addy Osmani agent-skills** — already installed (25).
- **Awesome Claude Skills** (ComposioHQ) — a directory, not skills → see Discovery.

---

## 12. From @RoundtableSpace "10 repos that turn Claude Code and Codex into elite UI designers"

Source: https://x.com/RoundtableSpace/status/2110255627704455591 (2026-10-14), plus the Superdesign repo Cliff sent directly. Scanned all ten. Only three ship agent skills; the rest are libraries (pulled per project). Stars as of 2026-10-17.

**Installed (2 skills):**
- **animate-text** ✅ — from `marvkr/better-design` (`.agents/skills/animate-text`). A catalog of named text animations (soft blur in, typewriter, line reveal, stagger, crossfade, kinetic builds) as exact JSON specs, translatable to CSS, WAAPI, Motion, GSAP and more. Self-contained, narrow trigger. Installed at `~/.claude/skills/animate-text`.
- **Superdesign** ✅ (restricted) — skill from `superdesigndev/superdesign-skill` (MIT, 815⭐); the main repo `superdesigndev/superdesign` (7.4k⭐, "AI Product Design Agent", AGPLv3 + a commercial license on some files) is the agent itself. The skill drives the Superdesign CLI (`npx @superdesign/cli`), needs a Superdesign login, and sends design work to their cloud. **Its trigger was narrowed** to explicit requests ("use Superdesign") so it never starts on a generic design task or ships project context to a third party by accident. Re-installing overwrites that edit. Installed at `~/.claude/skills/superdesign`.

**Not installed, and why:**
- **Design Taste** — `madebymustafa/design-taste` (142⭐, 24 skills: ten genre packs plus taste-* craft skills). It **prescribes the banned eyebrow pattern**: uppercase, letter-spaced mono labels and kickers ("Labels and metadata in mono or small caps, letterspaced (0.08-0.15em), uppercase"), and most of its craft skills duplicate the installed stack. Install only if you strip that guidance: `npx skills add madebymustafa/design-taste`.
- **Better Design** (main skill + MCP) — `marvkr/better-design` (453⭐, MIT): an open-source design MCP server plus shadcn registry (31 brand-grade themes, design tokens, WCAG rules). Its skill is only a workflow layer over the MCP (`https://better-design.com/api/mcp`), and it overlaps `refero-design`. To use it: `npx skills add marvkr/better-design --skill better-design` and connect the MCP (`claude mcp add --transport http better-design https://better-design.com/api/mcp`). Not connected; it adds a third-party remote server to every session.

**Libraries (per project, nothing global):**
- **Canvas UI** — https://github.com/DavidHDev/canvas-ui (5k⭐, MIT + Commons Clause). Real HTML with WebGL effects running over it; React, Vue, Svelte, vanilla. Landing pages only. `npx shadcn@latest add @canvas-ui/liquid-react`; MCP via `npx shadcn@latest mcp init --client claude`.
- **Paper Shaders** — https://github.com/paper-design/shaders (3.7k⭐, Apache 2.0). Zero-dependency canvas shaders (mesh gradients, dot orbits and more), also designable in Paper. `npm i @paper-design/shaders-react` (or `@paper-design/shaders` for vanilla). Landing and hero backgrounds.
- **UI Layouts** — https://github.com/ui-layouts/uilayouts (3.8k⭐, MIT). Components, effects and blocks; ships a separate MCP for component search (`ui-layouts/mcp`). Needs `npm install motion clsx tailwind-merge`.
- **Motion Primitives** — https://github.com/ibelick/motion-primitives (6.7k⭐, MIT). Animated, customizable UI kit built on Motion. Good for app UIs as well as marketing pages. Same author as ui-skills.
- **Cursify** — https://github.com/ui-layouts/cursify (2.1k⭐). Cursor animation library for React and Next.js. Landing pages only. Needs `npm install motion clsx tailwind-merge`.
- **Hyperiux Components** — https://github.com/Hyperiux-Immersion-Labs/hyperiux-components (94⭐, MIT code, separate "Hyperiux Effects License" for effects). 50+ free effects and 100+ Pro for Next.js, installed with `npx hyperiux init`. It also has its own MCP. Read the effects license before commercial use. Landing pages only.
- **Trickle UI Kit** — https://github.com/akaieuan/trickle-UI-kit (45⭐, MIT). Pure-CSS text animations for React, zero runtime, SSR-safe. `npx shadcn@latest add https://tricklekit.dev/r/typewriter.json`. A lighter alternative to GSAP text effects.

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
| Lint/gate UI quality (fonts, contrast, sizing) | lintapple |
| Auto-clean code slop (agent loop) | desloppify |
| Prune dead code / abandoned features | vibe-audit |
| Quick pre-PR code cleanup pass | vibe code cleanup (andyfischer gist) |
| Guardrails so the agent writes prod code | Vibecodex |
| Take a prototype to production | karpathy vibe-to-agentic |
| Repeatable agent dev workflow | obra/superpowers |
| More agent-ready React components | KokonutUI |
| Dark-mode toggle icon | toggles.dev |
| A distinct look for a chart, or a canvas/physics starting point | Emergent Mind Labs (chart prompts, 500 canvas demos) |
| Stop agent shipping UI slop | uizze.sh |
| iOS App Store listing (ASO) | before-skills |
| Registry of agent-ready components | 21st.dev |
| Code-driven cinematic / 3D animation | Theatre.js |
| GSAP scroll/hero motion components (landing) | Annimate (vendored starter pack) |
| React components + blocks (dashboards/checkout) | Arc (uiarc.dev) |
| Product video / launch reel (in code) | product-film ✅ installed |
| Fast "show what I built" launch clip | brag / brag-slim ✅ installed |
| AI character music video from a song | motion-graphics-music-video (makevoid) |
| Distinctive shadcn hero/background bits | 23rd ✅ installed |
| Motion-forward shadcn components (app UIs) | fluid-functionalism ✅ installed |
| Fancy card fans / carousels / micro-interactions (landing) | Amicro |
| MDX callouts/steps/terminals/glyph charts | mdxcn ✅ installed |
| Type-safe LLM output (self-hosted GPU) | TypeLLM |
| Security audit / vuln review | security-audit ✅ installed |
| Disciplined build workflow (TDD, review, planning) | addyosmani/agent-skills ✅ installed |
| Dashboard / SQL / data-viz skills | kw-data-* ✅ installed |
| Stop the agent over-engineering | ponytail ✅ installed |
| Cheaper/faster compressed output | caveman ✅ installed |
| Description → interactive HTML diagram | archify ✅ installed |
| Named text-animation specs (soft blur, typewriter, line reveal) | animate-text ✅ installed |
| Design on the Superdesign canvas (only when asked) | Superdesign ✅ installed (restricted) |
| Pure-CSS text animations, zero runtime | Trickle UI Kit |
| Animated app UI kit on Motion | Motion Primitives |
| Cursor animations (landing only) | Cursify |
| WebGL / shader hero backgrounds (landing only) | Paper Shaders, Canvas UI |
| Components + effects + component-search MCP | UI Layouts, Hyperiux Components |
| Design MCP with 31 brand themes (not connected) | Better Design |
| 3D hero scene | Spline |
| Interactive animated background | Unicorn Studio |
| Design→code with an agent (MCP) | paper.design |
| Free fonts | bestfreefonts.com |
| Design inspiration (galleries + directories) | mkdir.directory, DesignEng, Inspora, SEESAW, recent.design |
| OKLCH palette / fluid type-scale / easing utilities | DesignEng (designeng.tools) |
| AI-readable design system (DESIGN.md) to match an aesthetic | Refero Styles |
| Turn screenshots into a showreel | Reelfolio |
| Discover more Claude skills | awesome-claude-skills, ui-skills.com, skills.sh, kail_designs / csaba_kissi / DevDsgn lists |
