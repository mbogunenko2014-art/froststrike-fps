# NEXUS AI — browser assistant in one file

Single-file web AI chat (HTML + CSS + vanilla JS, no build step, no frameworks).

- Live LLM via free keyless `text.pollinations.ai` (OpenAI-compatible, SSE streaming) — answers any question like mainstream AI assistants
- Mind picker: ⚡ Flash / 🧠 Smart / 🔬 Deep / 👑 Ultra (top-tier GPT-5/6 + Claude-class models via gen.pollinations.ai with a free `sk_` key from enter.pollinations.ai)
- Image upload (📎): photos are downscaled in-browser and sent as OpenAI vision content parts; thumbnails shown in chat, full image never persisted
- Identity guard: the assistant always presents itself as NEXUS AI (system prompt + response sanitizer)
- Request cascade (stream → JSON per queued model → GET fallback → offline engine), 35 s per-attempt timeout — no hangs, no missing answers
- Offline fallback engine: math evaluation, date/time, coin/dice, persistent notes («запомни…»), small talk
- Markdown-lite rendering with code blocks, chat history in localStorage, regenerate, stop generation, TXT export, dark/light theme, fully responsive
