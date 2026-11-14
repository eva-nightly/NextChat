# Module: app [AI]

Provides the top-level application shell, page routing layout, core global types, URL/chat command parsing hooks, shared constants for AI service providers and endpoints, and UI/model utility helpers.

## Key files
- `app/layout.tsx`: Root HTML layout configuring metadata, viewport, client/server config hydration, and analytics scripts.
- `app/page.tsx`: Entry page component rendering the primary Home view and Vercel Analytics.
- `app/constant.ts`: Central constants, routes, API endpoints, model provider configurations, and storage keys.
- `app/command.ts`: Hooks for handling URL search parameter commands and in-chat slash/colon command shortcuts.
- `app/utils.ts`: Helper utilities for message content extraction, vision/DALL-E model detection, clipboard, file export, and UI measurements.
- `app/typing.ts`: Core TypeScript interfaces and type definitions for messages, roles, and image generation dimensions.
- `app/polyfill.ts`: Polyfills Array.prototype.at for environments lacking native support.
- `app/global.d.ts`: Ambient module declarations and Window interface extensions including Tauri runtime APIs.

## Public interface
- RootLayout({ children }: { children: React.ReactNode })
- App()
- useCommand(commands?: Commands)
- useChatCommand(commands?: ChatCommands)
- ChatCommandPrefix
- trimTopic(topic: string): string
- copyToClipboard(text: string): Promise<void>
- downloadAs(text: string, filename: string): Promise<void>
- readFromFile(): Promise<string>
- getMessageTextContent(message: RequestMessage): string
- getMessageTextContentWithoutThinking(message: RequestMessage): string
- getMessageImages(message: RequestMessage): string[]
- isVisionModel(model: string): boolean
- isDalle3(model: string): boolean
- getTimeoutMSByModel(model: string): number

## Dependencies
- react
- react-router-dom
- next
- @vercel/speed-insights/next
- @next/third-parties/google
- @vercel/analytics/react

## AI touchpoints [AI]
- `app/constant.ts`
- `app/utils.ts`

## Open questions
- _none_
