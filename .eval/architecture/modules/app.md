# Module: app [AI]

Serves as the root Next.js application shell and core configuration module, defining the base layout, home entry point, global constants (AI provider URLs, storage keys, route paths), slash/query command hooks, and shared utilities.

## Key files
- `app/layout.tsx`: Root HTML layout defining viewport, metadata, analytics integrations, stylesheet imports, and client runtime config injection
- `app/page.tsx`: Root page server component rendering the Home view and Vercel Analytics
- `app/constant.ts`: Central definition of provider API base URLs, path enums, storage keys, request timeouts, and provider-specific endpoint routes
- `app/command.ts`: React hooks for handling URL query parameter commands and chat input colon/slash prefix commands
- `app/utils.ts`: Shared helper functions for clipboard actions, Tauri/browser downloads, responsive layout, message parsing, thinking content filtering, and model vision/timeout detection
- `app/typing.ts`: Core TypeScript interfaces and type aliases for message roles, request messages, and image/model size constraints
- `app/global.d.ts`: Ambient TypeScript declarations for asset modules and Tauri desktop window bindings
- `app/polyfill.ts`: Runtime polyfill for Array.prototype.at

## Public interface
- RootLayout({ children }: { children: React.ReactNode })
- App()
- useCommand(commands?: Commands)
- useChatCommand(commands?: ChatCommands)
- ChatCommandPrefix
- Path
- ApiPath
- StoreKey
- ServiceProvider
- ModelProvider
- RequestMessage
- MessageRole
- trimTopic(topic: string)
- copyToClipboard(text: string)
- downloadAs(text: string, filename: string)
- readFromFile()
- useWindowSize()
- useMobileScreen()
- getMessageTextContent(message: RequestMessage)
- getMessageTextContentWithoutThinking(message: RequestMessage)
- getMessageImages(message: RequestMessage)
- isVisionModel(model: string)
- isDalle3(model: string)
- getTimeoutMSByModel(model: string)

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
