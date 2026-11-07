# Module: app [AI]

Provides the top-level application layout, root entry page, global constants, types, polyfills, command hooks, and utility functions for the NextChat web and desktop interface.

## Key files
- `app/layout.tsx`: Root Next.js layout providing metadata, viewport configuration, script/manifest links, and analytics integrations (Vercel Speed Insights, Google Tag Manager, Google Analytics).
- `app/page.tsx`: Root page server component mounting the main Home chat UI and Vercel Analytics.
- `app/constant.ts`: Central registry of API URLs, routes, storage keys, timeouts, provider enums, and provider-specific endpoint route builders.
- `app/command.ts`: Custom React hooks for URL query command handling (useCommand) and chat colon/slash command parsing and execution (useChatCommand).
- `app/utils.ts`: General and AI-specific utility functions for clipboard copy, file downloads, DOM auto-grow calculations, Tauri platform bridging, message text parsing, and model capability checks.
- `app/typing.ts`: Core TypeScript interfaces and type definitions for chat messages, roles, image generation sizes, and state updater functions.
- `app/polyfill.ts`: Global Array.prototype.at polyfill.
- `app/global.d.ts`: TypeScript declarations for static assets and the Tauri window bridge API.

## Public interface
- RootLayout (React component in app/layout.tsx)
- App (React component in app/page.tsx)
- useCommand, useChatCommand, ChatCommandPrefix (app/command.ts)
- Enums: Path, ApiPath, SlotID, FileName, StoreKey, ServiceProvider, ModelProvider, GoogleSafetySettingsThreshold (app/constant.ts)
- Provider configs: Stability, Anthropic, OpenaiPath, Azure, Google, Baidu, ByteDance, Alibaba, Tencent, Moonshot, Iflytek, DeepSeek, XAI, ChatGLM, SiliconFlow, AI302 (app/constant.ts)
- trimTopic, copyToClipboard, downloadAs, readFromFile, isIOS, useWindowSize, useMobileScreen, isFirefox, selectOrCopy, autoGrowTextArea, getCSSVar, isMacOS, getMessageTextContent, getMessageTextContentWithoutThinking, getMessageImages, isVisionModel, isDalle3, getTimeoutMSByModel (app/utils.ts)
- Types and constants: Updater, ROLES, MessageRole, RequestMessage, DalleSize, DalleQuality, DalleStyle, ModelSize (app/typing.ts)

## Dependencies
- react
- react-router-dom
- next
- @vercel/speed-insights/next
- @vercel/analytics/react
- @next/third-parties/google
- ./config/client
- ./config/server
- ./components/home
- ./components/ui-lib
- ./client/api
- ./locales
- ./utils/stream
- ./store

## AI touchpoints [AI]
- `app/constant.ts`
- `app/utils.ts`
- `app/typing.ts`
- `app/command.ts`

## Open questions
- app/constant.ts and app/utils.ts were truncated in the provided file list; some model constants and helper functions are partially omitted.
