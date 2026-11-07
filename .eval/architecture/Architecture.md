# Architecture

NextChat is a Next.js (App Router) web/desktop client for many LLM providers. The browser-side UI (app/components) is driven by Zustand stores persisted to IndexedDB (app/store, app/utils/store) and talks to providers through a client adapter layer (app/client) that normalizes chat, streaming, tool-calling, speech and image generation across OpenAI, Azure, Anthropic, Gemini, DeepSeek, Qwen, Ernie, Hunyuan, GLM, Moonshot, Spark, xAI, SiliconFlow and 302.AI. Requests go through edge route handlers in app/api, which authenticate access codes, inject server-held API keys from app/config/server, enforce model/path allow-lists, and proxy to upstream providers (optionally via Cloudflare AI Gateway); next.config.mjs adds additional rewrite-based proxies and CORS headers. Cross-cutting concerns include i18n dictionaries (app/locales), builtin prompt presets (app/masks, scripts/fetch-prompts.mjs), Model Context Protocol tool execution via server actions (app/mcp), realtime voice chat built on Web Audio worklets (app/lib, public), cloud sync via WebDAV/Upstash (app/utils/cloud), and a Jest/jsdom test suite (test) covering model helpers, token estimation, MCP guards and config parsing. Note: route handlers declare runtime='edge' despite documentation describing a node runtime.

## Modules

| module | summary | AI |
| --- | --- | --- |
| `(root)` | Next.js, Jest and Prettier configuration including CORS headers and rewrite proxies to upstream AI providers. | [AI] |
| `app` | Root layout/page, global constants (providers, endpoints, paths), chat command hooks, shared types and core utility helpers. | [AI] |
| `app/api` | Edge route handlers that authenticate, filter and proxy requests to 16+ AI providers plus WebDAV/Upstash/KV helpers. | [AI] |
| `app/client` | Client-side LLM abstraction (ClientApi/LLMApi) with per-provider adapters for chat streaming, tools, speech and images. | [AI] |
| `app/components` | React UI: chat, sidebar, masks, settings, plugins, MCP market, markdown/artifacts, realtime voice chat and Stable Diffusion views. | [AI] |
| `app/config` | Build, client (meta-tag) and server (env var) configuration readers including per-provider keys and URLs. | [AI] |
| `app/lib` | AudioHandler wrapping Web Audio API for worklet-based recording, streaming playback and WAV export. | — |
| `app/locales` | i18n dictionaries for 20+ languages with fallback merging, language detection and STT locale mapping. | [AI] |
| `app/masks` | Builtin prompt presets (masks) in cn/tw/en with model configs and a build script emitting public/masks.json. | [AI] |
| `app/mcp` | Server actions and SDK wrappers spawning stdio MCP clients, listing tools and executing tool-call requests. | — |
| `app/store` | Zustand stores for sessions, model config, access credentials, masks, plugins, prompts, SD tasks, sync and updates. | [AI] |
| `app/utils` | SSE streaming/tool orchestration, model catalog & token helpers, persistence wrappers, cloud sync, provider signatures, TTS. | [AI] |
| `public` | AudioWorklet recorder processor and a Service Worker caching files under /api/cache. | — |
| `scripts` | Script fetching and bundling community prompt templates into public/prompts.json. | [AI] |
| `test` | Jest unit tests for utils, model helpers, token estimation, config, chat store and MCP access guards. | [AI] |

## Module dependencies

```mermaid
graph LR
  m1["app"] --> m5["app/config"]
  m1["app"] --> m4["app/components"]
  m1["app"] --> m10["app/store"]
  m2["app/api"] --> m5["app/config"]
  m2["app/api"] --> m1["app"]
  m2["app/api"] --> m11["app/utils"]
  m2["app/api"] --> m3["app/client"]
  m3["app/client"] --> m1["app"]
  m3["app/client"] --> m10["app/store"]
  m3["app/client"] --> m5["app/config"]
  m3["app/client"] --> m11["app/utils"]
  m4["app/components"] --> m10["app/store"]
  m4["app/components"] --> m7["app/locales"]
  m4["app/components"] --> m1["app"]
  m4["app/components"] --> m6["app/lib"]
  m4["app/components"] --> m11["app/utils"]
  m4["app/components"] --> m5["app/config"]
  m4["app/components"] --> m3["app/client"]
  m4["app/components"] --> m9["app/mcp"]
  m5["app/config"] --> m1["app"]
  m5["app/config"] --> m11["app/utils"]
  m7["app/locales"] --> m10["app/store"]
  m7["app/locales"] --> m5["app/config"]
  m7["app/locales"] --> m1["app"]
  m7["app/locales"] --> m11["app/utils"]
  m8["app/masks"] --> m10["app/store"]
  m10["app/store"] --> m3["app/client"]
  m10["app/store"] --> m11["app/utils"]
  m10["app/store"] --> m1["app"]
  m11["app/utils"] --> m1["app"]
  m6["app/lib"] --> m12["public"]
  m0["(root)"] --> m14["test"]
  m0["(root)"] --> m2["app/api"]
  m14["test"] --> m11["app/utils"]
  m14["test"] --> m3["app/client"]
  m14["test"] --> m1["app"]
  m14["test"] --> m5["app/config"]
  m14["test"] --> m10["app/store"]
  m14["test"] --> m9["app/mcp"]
```

_`[AI]` marks modules with AI/LLM touchpoints (prompt files, model API calls, agent logic)._
