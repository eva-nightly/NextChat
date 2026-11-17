# Architecture

NextChat is a Next.js (App Router) multi-provider LLM chat client. The browser-side app (app/components, app/store, app/client) renders chat sessions, masks (system prompts), plugins/MCP tools, Stability AI image generation, TTS and realtime voice; state is persisted in IndexedDB via Zustand wrappers in app/utils. Requests to LLM providers (OpenAI, Azure, Anthropic, Google, DeepSeek, Baidu, ByteDance, Alibaba, Tencent, Moonshot, iFlytek, xAI, ChatGLM, SiliconFlow, 302.AI) flow from per-provider client adapters in app/client/platforms through edge API route handlers in app/api, which enforce access codes, inject server-held API keys (app/config/server.ts), filter models and optionally route through Cloudflare AI Gateway. Shared constants/types live in app/constant.ts and app/typing.ts; i18n in app/locales; built-in personas in app/masks; MCP server lifecycle in app/mcp. Root config (next.config.mjs) adds reverse-proxy rewrites and CORS; Jest tests in test/ cover utils, model tables, MCP guards and validators.

## Modules

| module | summary | AI |
| --- | --- | --- |
| `(root)` | Next.js build/runtime config (AI provider proxy rewrites, CORS), Jest and Prettier setup. | [AI] |
| `app` | App shell (layout/page), central constants and provider enums, shared types, URL/chat command hooks and client utilities. | [AI] |
| `app/api` | Edge route handlers proxying requests to LLM providers with auth, key injection, model filtering, plus artifacts/WebDAV/Upstash storage endpoints. | [AI] |
| `app/client` | Client-side LLMApi abstraction, ClientApi factory, abort controller pool and per-provider streaming chat adapters. | [AI] |
| `app/components` | React UI: chat, sidebar, settings, masks, plugins, MCP market, markdown/artifacts, SD image generation, TTS and realtime voice chat. | [AI] |
| `app/config` | Build, client and server configuration loaders including provider API keys, access codes and model restrictions. | [AI] |
| `app/lib` | AudioHandler for Web Audio recording, streaming PCM playback and visualization. | — |
| `app/locales` | i18n dictionaries for many languages, language detection/persistence and STT language mappings. | [AI] |
| `app/masks` | Built-in persona/system-prompt presets (en/cn/tw) with runtime store and build export script. | [AI] |
| `app/mcp` | Model Context Protocol server management, tool discovery and execution via server actions and stdio clients. | — |
| `app/store` | Zustand persistent stores for access credentials, chat sessions, config, masks, plugins, prompts, SD tasks, sync and updates. | [AI] |
| `app/utils` | Helpers for SSE streaming/tool orchestration, model table resolution, IndexedDB persistence, cloud sync, TTS, signing and formatting. | [AI] |
| `public` | Browser scripts: service worker file cache on /api/cache and AudioWorklet recorder processor. | — |
| `scripts` | Maintenance script fetching and compiling community prompts into public/prompts.json. | [AI] |
| `test` | Jest unit/integration tests for utils, model tables, MCP guards, validators and config. | [AI] |

## Module dependencies

```mermaid
graph LR
  m1["app"] --> m5["app/config"]
  m2["app/api"] --> m5["app/config"]
  m2["app/api"] --> m1["app"]
  m2["app/api"] --> m11["app/utils"]
  m2["app/api"] --> m3["app/client"]
  m3["app/client"] --> m5["app/config"]
  m3["app/client"] --> m1["app"]
  m3["app/client"] --> m10["app/store"]
  m3["app/client"] --> m11["app/utils"]
  m4["app/components"] --> m10["app/store"]
  m4["app/components"] --> m9["app/mcp"]
  m4["app/components"] --> m3["app/client"]
  m4["app/components"] --> m7["app/locales"]
  m4["app/components"] --> m1["app"]
  m4["app/components"] --> m8["app/masks"]
  m4["app/components"] --> m11["app/utils"]
  m4["app/components"] --> m6["app/lib"]
  m5["app/config"] --> m1["app"]
  m5["app/config"] --> m11["app/utils"]
  m7["app/locales"] --> m1["app"]
  m7["app/locales"] --> m5["app/config"]
  m7["app/locales"] --> m10["app/store"]
  m7["app/locales"] --> m11["app/utils"]
  m8["app/masks"] --> m10["app/store"]
  m10["app/store"] --> m3["app/client"]
  m10["app/store"] --> m11["app/utils"]
  m11["app/utils"] --> m1["app"]
  m11["app/utils"] --> m10["app/store"]
  m6["app/lib"] --> m12["public"]
  m14["test"] --> m11["app/utils"]
  m14["test"] --> m9["app/mcp"]
  m14["test"] --> m10["app/store"]
  m14["test"] --> m5["app/config"]
  m14["test"] --> m3["app/client"]
  m14["test"] --> m1["app"]
```

_`[AI]` marks modules with AI/LLM touchpoints (prompt files, model API calls, agent logic)._
