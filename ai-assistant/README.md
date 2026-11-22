# NEXUS AI — browser assistant in one file

Single-file web AI chat (HTML + CSS + vanilla JS, no build step, no frameworks).
Dark glassmorphism interface over an atmospheric SVG scenery (wooden hut, slate mountains, drifting fog) with desktop window layout (icon rail + collapsible sidebar + macOS-style window dots) and an adaptive mobile layout with drawers.

- Live LLM via free keyless `text.pollinations.ai` (OpenAI-compatible, SSE streaming) — answers any question like mainstream AI assistants
- Mind picker: ⚡ Flash / 🧠 Smart / 🔬 Deep / 👑 Ultra (top-tier GPT-5/6 + Claude-class models via gen.pollinations.ai with a free `sk_` key from enter.pollinations.ai)
- Image upload (📎): photos are downscaled in-browser and sent as OpenAI vision content parts; thumbnails shown in chat, full image never persisted
- Image generation (🎨 mode or `/img <prompt>`): free keyless generation via image.pollinations.ai (flux); with a Pollinations key it upgrades to Nano Banana (google/gemini-nano-banana-2.1) via gen.pollinations.ai, with automatic fallback; «ещё вариант» re-rolls the seed
- Identity guard: the assistant always presents itself as NEXUS AI (system prompt + response sanitizer)
- Request cascade (stream → JSON per queued model → GET fallback → offline engine), 35 s per-attempt timeout — no hangs, no missing answers
- Offline fallback engine: math evaluation, date/time, coin/dice, persistent notes («запомни…»), small talk
- Settings screen («Внешний вид и данные»): provider status cards with key check, background animation toggle, background brightness slider, double-confirm history wipe
- Prompt library (▤), chat sessions with search, web-search capsule (searchgpt model first, graceful fallback), regenerate, stop generation, TXT export
- Markdown-lite rendering with code blocks, chat history in localStorage, fully responsive
- Mobile (phones): bottom navigation bar (new chat / chats / prompts / settings), settings as a bottom-sheet, voice input (ru-RU) via SpeechRecognition, popups repositioned above the nav bar, reduced blur cost
- Voice control: wake word «Нексус» — opens sites in a new tab (YouTube, Google, Wikipedia, GitHub, mail, weather…, any domain, or a Google search fallback), plus app commands (new chat, clear history, settings, chats, prompts, web search on/off, mind flash/smart/deep/ultra, scroll, fullscreen, close, help); if the popup blocker interferes, an inline «Открыть» action bar appears
- Voice session: after a command the mic keeps listening for more commands; dictation ends the session; all recognition errors (no mic permission, offline, no speech, unsupported browser) are explained via on-screen toasts; non-HTTPS (opening from a file) is detected and reported
- Read-aloud answers: NEXUS can speak responses via SpeechSynthesis (ru-RU), toggled by the speaker button or voice command
