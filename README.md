# Hi, I'm Pedram

Mechanical engineer (MSc, product development) now shipping AI products and agents — three live projects below, all built solo with modern AI tooling.

## Featured projects

### 🍳 Meelo — AI Chef
A conversational AI chef that plans meals, builds grocery lists, and walks you through recipes hands-free.

- **What it does:** Conversational meal planning with voice mode for cooking, auto-generated grocery lists, and personalised recipes based on diet, time, and what's in the fridge.
- **Stack:** React + TypeScript PWA, Supabase (auth, DB, storage), Gemini with tool calls for structured meal/recipe generation, Web Speech API for voice.
- **Why these choices:** Gemini's tool calling gives reliable structured output for meal plans without brittle parsing; Supabase keeps the backend small enough for one person to ship and iterate.
- **Trade-off I made:** Shipped voice mode before account-level personalisation — voice was the differentiator users actually noticed in testing.
- Live: https://meelo-chef.lovable.app
- Code: https://github.com/pedramhajigholi-cloud/meelio-your-ai-chef

### 🤖 Job Hunter — AI Agent
An automation I built for myself: finds, ranks, and shortlists Nordic tech roles every weekday so I don't have to scroll job boards.

- **What it does:** Runs on a GitHub Actions cron (07:00 weekdays), pulls live listings from Sweden, Norway, and Denmark, ranks them with the Claude API against a structured role profile, and emails a shortlist with match scores and reasoning.
- **Stack:** Python, GitHub Actions, Claude API, structured prompts with an explicit scoring rubric.
- **Why these choices:** GitHub Actions = free, observable, version-controlled scheduling. An LLM ranks better than keyword filtering because it reasons over fit, not just title overlap.
- **Trade-off I made:** Chose an LLM ranking pass over keyword filtering — slower and pricier per run, but lets me iterate the rubric in plain English in minutes.
- Code: https://github.com/pedramhajigholi-cloud/job-agent

### 🔌 Meelo MCP Server
A Python MCP server that exposes Meelo's data as tools any MCP-aware LLM client (Claude Desktop, etc.) can call — so Meelo lives wherever you already talk to an LLM, not just inside its own app.

- **What it does:** Exposes three tools — `get_meal_plan(days)`, `get_recipe(recipe_id)`, and `get_taste_profile()` — over the Model Context Protocol. Once configured in Claude Desktop, asking "what's Pedram cooking for dinner?" causes Claude to call the server and return the answer.
- **Stack:** Python, official `mcp` SDK (FastMCP high-level interface), stdio transport. v1 is shaped exactly like Meelo's real Supabase schema, so swapping to live data later is a one-line change inside each tool.
- **Why these choices:** FastMCP removes the protocol boilerplate so the work stays on tool design, not transport plumbing.
- **Trade-off I made:** Proved the end-to-end protocol with schema-shaped fixtures first and pushed the live Supabase swap to v2 — small, scoped follow-up instead of a blocker.
- Code: https://github.com/pedramhajigholi-cloud/meelo-mcp-server

## How I work

- **Ship to learn.** I'd rather have something rough in real use this week than a perfect plan next month.
- **Make trade-offs explicit.** Every shortcut is a decision, not an accident — voice before personalisation, LLM ranking over keyword filtering. I want to be able to explain why.
- **Stay close to the user.** I test on real people early and let what they actually notice steer the roadmap.
- **Use AI tooling pragmatically.** I reach for what gets me to working software fastest, then refactor when something actually hurts.

## What I'm interested in

- AI-powered consumer products
- Health, nutrition, and fitness tech
- Real-world AI workflows and automation

## Get in touch

- Email: pedram.hajigholi@gmail.com
- LinkedIn: https://www.linkedin.com/in/pedramhajigholi/
