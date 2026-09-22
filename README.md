# XFree App

Grok-style mobile shell for X. No signup. Chats stay in the browser.

| Mode | What it does |
| --- | --- |
| **Cloud** | `POST /api/nvidia/chat` → proxied to [www.xfree.in](https://www.xfree.in) (MiniMax M3 / Auto / Kimi) |
| **Local** | Ollama on this device (`localhost:11434`, default `llama3.2:1b`) |
| **Voice** | Web Speech listen → think → speak (Jarvis loop) |

## Deploy

Vercel project rooted at this repository:

1. Import [CodesbyFebin/xfree-app](https://github.com/CodesbyFebin/xfree-app)
2. Framework preset: Other
3. Output: static (`index.html`)

After deploy:

- `/` — XFree App
- `/grok` — same shell (clean URL alias)
- `/api/*` — rewrite to `https://www.xfree.in/api/*`

Microphone is allowed (`Permissions-Policy: microphone=(self)`).

## Studio desk is separate

Do **not** replace [app.xfree.in](https://app.xfree.in/) (`public/studio/index.html` in `CodesbyFebin/xfree`). That file is the command center.

To also serve this shell at `https://app.xfree.in/grok`, copy `index.html` there as `public/studio/grok.html` and add the `/grok` rewrite in that project's `vercel.json`.
