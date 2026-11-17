# Module: app [AI]

Provides root Next.js app shell components, application-wide constants and API paths for LLM providers, URL search param/chat command hooks, type definitions, and client utilities for text/clipboard/UI management and message processing.

## Key files
- `app/layout.tsx`: Root HTML layout configuring metadata, viewport, PWA manifest, service worker, styling, and Google/Vercel analytics scripts.
- `app/page.tsx`: Main server component page rendering the Home component and Vercel analytics.
- `app/constant.ts`: Central constants repository defining provider API base URLs, paths, service/model provider enums, storage keys, and timeouts.
- `app/command.ts`: React hooks (useCommand, useChatCommand) for handling URL query-string commands and chat input colon commands.
- `app/utils.ts`: Platform, DOM, clipboard, file, timeout, and message content parsing utilities (handling text, vision, and thinking outputs).
- `app/typing.ts`: Shared TypeScript types for message roles (system, user, assistant), request message formats, and model/image sizes.
- `app/polyfill.ts`: Polyfill for Array.prototype.at.
- `app/global.d.ts`: Ambient module declarations and Window interface extension for Tauri desktop capabilities.

## Public interface
- RootLayout({ children }: { children: React.ReactNode })
- App()
- useCommand(commands?: Commands)
- useChatCommand(commands?: ChatCommands)
- ChatCommandPrefix
- trimTopic(topic: string)
- copyToClipboard(text: string)
- downloadAs(text: string, filename: string)
- readFromFile()
- isIOS()
- useWindowSize()
- useMobileScreen()
- isFirefox()
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
- ROLES
- Path
- ApiPath
- StoreKey
- ServiceProvider
- ModelProvider

## Dependencies
- react
- react-router-dom
- next
- @next/third-parties/google
- @vercel/speed-insights/next
- @vercel/analytics/react

## AI touchpoints [AI]
- `app/constant.ts`
- `app/utils.ts`
- `app/typing.ts`

## Open questions
- _none_
