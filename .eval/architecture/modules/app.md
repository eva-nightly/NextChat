# Module: app [AI]

Serves as the root module for NextChat, providing the top-level Next.js page/layout wrappers, global typing, polyfills, cross-platform Tauri/web utilities, chat slash commands, and central provider/path/store constants.

## Key files
- `app/layout.tsx`: Next.js root HTML layout injecting client/server configurations, meta tags, manifest, service worker registration, and analytics scripts.
- `app/page.tsx`: Next.js root page entry rendering the Home client component and Vercel analytics.
- `app/constant.ts`: Central registry of routes, API paths, storage keys, service providers, model endpoints, and request timeout configurations.
- `app/utils.ts`: Shared helper functions for clipboard management, Tauri/browser file saving, UI sizing, text extraction, vision model checks, and timeout handling.
- `app/command.ts`: Hooks for URL search param commands and in-chat slash command parsing and matching.
- `app/typing.ts`: Common TypeScript types for message roles, request messages, image generation parameters, and state updaters.
- `app/global.d.ts`: Global TypeScript declarations for asset imports and the window.__TAURI__ interface.
- `app/polyfill.ts`: Array.prototype.at polyfill for compatibility in older browser environments.

## Public interface
- useCommand(commands?: Commands)
- useChatCommand(commands?: ChatCommands)
- ChatCommandPrefix
- RootLayout({ children }: { children: React.ReactNode })
- App()
- trimTopic(topic: string): string
- copyToClipboard(text: string): Promise<void>
- downloadAs(text: string, filename: string): Promise<void>
- readFromFile(): Promise<string>
- useWindowSize(): { width: number; height: number }
- useMobileScreen(): boolean
- autoGrowTextArea(dom: HTMLTextAreaElement): number
- getMessageTextContent(message: RequestMessage): string
- getMessageTextContentWithoutThinking(message: RequestMessage): string
- getMessageImages(message: RequestMessage): string[]
- isVisionModel(model: string): boolean
- isDalle3(model: string): boolean
- getTimeoutMSByModel(model: string): number
- Path
- ApiPath
- StoreKey
- ServiceProvider
- ModelProvider
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
- `app/typing.ts`

## Open questions
- _none_
