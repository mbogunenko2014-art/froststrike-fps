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
- Prompt library (▤), chat sessions with search, web-search capsule, regenerate, stop generation, TXT export
- Real web answers: when web-search is on, NEXUS looks the query up via the Wikipedia API (ru → en fallback) and injects the found extracts into the model context; source links appear under the answer
- Video plugin: text like \u00ab\u0441\u0434\u0435\u043b\u0430\u0439 \u0432\u0438\u0434\u0435\u043e \u2026\u00bb or the Plugins panel opens the Video Studio \u2014 AI scenes (Pollinations) are animated (Ken Burns + crossfades + titles + synthesized ambient music) and recorded to a downloadable WebM via canvas.captureStream + MediaRecorder, with live progress and stop; falls back to a live animation preview if the browser cannot record
- Nexus Code plugin (\u00ab/\u043a\u043e\u0434 \u2026\u00bb, \u00ab\u043d\u0430\u043f\u0438\u0448\u0438 \u0438\u0433\u0440\u0443 \u2026\u00bb or the Plugins panel): a multi-agent coding pipeline \u2014 Architect (plan) \u2192 Coder (single-file HTML app) \u2192 in Ultra mode two reviewer agents (Claude Mini and Open Code) audit the code twice and the Coder merges fixes \u2014 result card can Run the code in a sandboxed iframe preview, Copy it or Download nexus-code.html
- More built-in plugin tools: Timer (\u00ab\u0442\u0430\u0439\u043c\u0435\u0440 \u043d\u0430 5 \u043c\u0438\u043d\u0443\u0442\u00bb \u2014 beep + toast + voice at fire), Pick-for-me (\u00ab\u0432\u044b\u0431\u0435\u0440\u0438 \u0438\u0437: \u2026\u00bb \u2014 random choice), Day counter (\u00ab\u0441\u043a\u043e\u043b\u044c\u043a\u043e \u0434\u043d\u0435\u0439 \u0434\u043e 8 \u043c\u0430\u0440\u0442\u0430\u00bb \u2014 10 plugins in total, each toggleable)
- Built-in plugins (menu "Плагины" next to web-search, everything works offline): accurate calculator (incl. "15% от …"), unit converter (length/mass/volume, °C↔°F) and number systems (binary/octal/hex), exact date and time, secure password generator (length 8–64, crypto.getRandomValues), dice/coin/random numbers — each result is computed in the app and injected into the model context as a verified fact; plugins can be toggled off individually, work in offline fallback mode, and are openable by voice command
- Follow-up chips under each answer («Объясни проще» / «Подробнее» / «Приведи примеры») — one tap continues the dialogue
- Input draft: unsent text is autosaved and restored after reload
- Markdown-lite rendering with code blocks, chat history in localStorage, fully responsive
- Mobile (phones): bottom navigation bar (new chat / chats / prompts / settings), settings as a bottom-sheet, voice input (ru-RU) via SpeechRecognition, popups repositioned above the nav bar, reduced blur cost
- Voice control: wake word «Нексус» — opens sites in a new tab (YouTube, Google, Wikipedia, GitHub, mail, weather…, any domain, or a Google search fallback), plus app commands (new chat, clear history, settings, chats, prompts, web search on/off, mind flash/smart/deep/ultra, scroll, fullscreen, close, help); if the popup blocker interferes, an inline «Открыть» action bar appears
- Voice session: after a command the mic keeps listening for more commands; dictation ends the session; all recognition errors (no mic permission, offline, no speech, unsupported browser) are explained via on-screen toasts; non-HTTPS (opening from a file) is detected and reported
- Read-aloud answers: NEXUS can speak responses via SpeechSynthesis (ru-RU), toggled by the speaker button or voice command
- Voice dialogue mode (loop button): mic listens → you speak → NEXUS answers aloud → listens again, no keyboard needed; «стоп»/«хватит» disables it, mic tap stops the mode
- Long memory: «запомни …» saves a note, «что ты помнишь» lists, «забудь всё» clears; names captured automatically; notes are injected into every LLM request; memory card with counters in settings
- Every drawing prompt is auto-translated and expanded into a vivid English image prompt before generation (fallback to raw text offline)
