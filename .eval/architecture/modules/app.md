# Module: app [AI]

Provides the top-level Next.js layout, root page entry point, global constants, command hooks, type definitions, and core utility helpers for chat manipulation and multi-provider AI endpoints.

## Key files
- `app/layout.tsx`: Next.js root layout defining metadata, viewport settings, client config DOM injection, styles, and analytics integration.
- `app/page.tsx`: Root page entry component rendering the main Home view and Vercel analytics.
- `app/constant.ts`: Defines application-wide constants, service provider enums, endpoint URLs, and API routes for supported AI models.
- `app/command.ts`: React hooks for processing URL query commands and chat colon-prefixed command shortcuts.
- `app/utils.ts`: Client utility functions for clipboard access, file I/O, responsive sizing, and parsing multimodal message contents.
- `app/typing.ts`: Shared TypeScript types for chat roles, request messages, and image generation specifications.
- `app/polyfill.ts`: Polyfills Array.prototype.at for legacy JavaScript runtimes.
- `app/global.d.ts`: Ambient type declarations for static assets and Tauri desktop window APIs.

## Public interface
- RootLayout({ children }: { children: React.ReactNode })
- App()
- useCommand(commands?: Commands)
- useChatCommand(commands?: ChatCommands)
- ChatCommandPrefix
- copyToClipboard(text: string)
- downloadAs(text: string, filename: string)
- readFromFile()
- useWindowSize()
- useMobileScreen()
- autoGrowTextArea(dom: HTMLTextAreaElement)
- getMessageTextContent(message: RequestMessage)
- getMessageTextContentWithoutThinking(message: RequestMessage)
- getMessageImages(message: RequestMessage)
- isVisionModel(model: string)
- getTimeoutMSByModel(model: string)
- ServiceProvider
- ModelProvider
- Path
- ApiPath
- StoreKey
- RequestMessage
- MessageRole

## Dependencies
- react
- react-router-dom
- next
- @vercel/speed-insights/next
- @vercel/analytics/react
- @next/third-parties/google

## AI touchpoints [AI]
- `app/constant.ts`
- `app/utils.ts`
- `app/command.ts`

## Open questions
- _none_
