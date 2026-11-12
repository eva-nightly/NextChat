# Module: app [AI]

Serves as the root module for the NextChat web and desktop application, defining the Next.js page and layout entry points, global constants, command hooks, shared types, polyfills, and core utility functions across web and Tauri desktop environments.

## Key files
- `app/layout.tsx`: Root Next.js layout defining HTML structure, metadata, client configuration injection, service worker scripts, and Google/Vercel analytics integrations.
- `app/page.tsx`: Root page entry point rendering the main Home UI component and analytics.
- `app/constant.ts`: Central registry of constants including API base URLs, service providers, route paths, model identifiers, store keys, and timeout configurations.
- `app/command.ts`: React hooks for handling URL search parameter commands and in-chat slash/colon command parsing.
- `app/utils.ts`: General utility helpers for clipboard operations, file download/upload, UI measuring, thinking message extraction, vision model detection, and cross-platform (Web/Tauri) compatibility.
- `app/typing.ts`: Core TypeScript type definitions for chat messages, roles, and image generation dimensions.
- `app/global.d.ts`: Global TypeScript type shims and Window declarations for Tauri runtime APIs.
- `app/polyfill.ts`: Polyfill for Array.prototype.at.

## Public interface
- RootLayout({ children }: { children: React.ReactNode })
- App()
- useCommand(commands?: Commands)
- useChatCommand(commands?: ChatCommands)
- trimTopic(topic: string)
- copyToClipboard(text: string)
- downloadAs(text: string, filename: string)
- readFromFile()
- useWindowSize()
- useMobileScreen()
- selectOrCopy(el: HTMLElement, content: string)
- autoGrowTextArea(dom: HTMLTextAreaElement)
- getCSSVar(varName: string)
- isMacOS()
- getMessageTextContent(message: RequestMessage)
- getMessageTextContentWithoutThinking(message: RequestMessage)
- getMessageImages(message: RequestMessage)
- isVisionModel(model: string)
- isDalle3(model: string)
- getTimeoutMSByModel(model: string)
- enum Path
- enum ApiPath
- enum ServiceProvider
- enum ModelProvider
- enum StoreKey
- enum FileName
- enum SlotID
- enum GoogleSafetySettingsThreshold
- type RequestMessage
- type MessageRole

## Dependencies
- react
- react-router-dom
- next
- @vercel/speed-insights/next
- @vercel/analytics/react
- @next/third-parties/google
- app/config/client
- app/config/server
- app/components/home
- app/components/ui-lib
- app/locales
- app/client/api
- app/store
- app/utils/stream

## AI touchpoints [AI]
- `app/constant.ts`
- `app/utils.ts`
- `app/typing.ts`

## Open questions
- _none_
