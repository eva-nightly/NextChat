# Module: app [AI]

Serves as the root Next.js application layer and core utility module, providing root layout/page entry points, global constants for AI providers and storage keys, message/command parsing utilities, and shared type definitions.

## Key files
- `app/layout.tsx`: Root application layout integrating server/client configuration meta tags, analytics, service worker registration, and base styling.
- `app/page.tsx`: Main Next.js server component page rendering the Home chat component alongside analytics.
- `app/constant.ts`: Central registry of AI provider base URLs, endpoints, routing paths, storage keys, and model timeout constants.
- `app/command.ts`: React hooks for processing URL query commands and chat slash/colon commands.
- `app/utils.ts`: Helper utilities for DOM manipulation, clipboard/file operations, Tauri desktop bridge detection, message text/image extraction, and model capabilities check.
- `app/typing.ts`: Core message and generation type definitions including roles, request formats, and image generation dimensions.
- `app/polyfill.ts`: Runtime polyfills such as Array.prototype.at.
- `app/global.d.ts`: Global TypeScript type declarations for asset imports and the window.__TAURI__ desktop runtime API.

## Public interface
- RootLayout(props: { children: React.ReactNode })
- App()
- useCommand(commands?: Commands)
- useChatCommand(commands?: ChatCommands)
- copyToClipboard(text: string): Promise<void>
- downloadAs(text: string, filename: string): Promise<void>
- getMessageTextContent(message: RequestMessage): string
- getMessageTextContentWithoutThinking(message: RequestMessage): string
- getMessageImages(message: RequestMessage): string[]
- isVisionModel(model: string): boolean
- isDalle3(model: string): boolean
- getTimeoutMSByModel(model: string): number
- autoGrowTextArea(dom: HTMLTextAreaElement): number

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
- ./locales
- ./client/api
- ./utils/stream
- ./store

## AI touchpoints [AI]
- `app/constant.ts`
- `app/utils.ts`
- `app/typing.ts`

## Open questions
- _none_
