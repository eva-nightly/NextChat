# Module: app/components [AI]

(part 1 of 3) Provides the primary user interface and presentation components for NextChat, including the chat interface, session management, markdown/artifact rendering, export utilities, authentication forms, and layout shell. (part 2 of 3) Provides UI views and configuration panels for prompt templates (masks), Model Context Protocol (MCP) servers, OpenAPI plugin integrations, chat history searching, message selection, and LLM model parameter tuning. (part 3 of 3) Provides user interface components for the NextChat application, including core UI controls, sidebar navigation, settings modals, real-time voice chat integration via rt-client, Stable Diffusion image generation interfaces, and audio visualizers.

_This module does not fit in one model call, so it was read in 3 parts and their summaries were combined without a further model call._

## Key files
- `app/components/home.tsx`: Top-level application container managing routing, global layout, theme switching, model list fetching, and MCP initialization.
- `app/components/chat.tsx`: Main chat window handling streaming messages, session configuration, prompt/mask integration, tool actions, and user input.
- `app/components/chat-list.tsx`: Sidebar list of chat sessions with drag-and-drop reordering, deletion, and session selection.
- `app/components/markdown.tsx`: Markdown renderer with code block folding, KaTeX math parsing, Mermaid diagrams, and HTML artifact execution.
- `app/components/artifacts.tsx`: Sandboxed iframe preview and sharing manager for HTML artifacts generated during chats.
- `app/components/exporter.tsx`: Multi-format message exporter supporting image, markdown text, and JSON exports.
- `app/components/auth.tsx`: Authentication page for configuring access codes and custom API keys for providers.
- `app/components/emoji.tsx`: Emoji picker and model avatar renderer displaying brand icons matching specific LLMs.
- `app/components/error.tsx`: Client error boundary providing crash display, error reporting links, and data reset options.
- `app/components/button.tsx`: Re-usable icon button component for UI actions.
- `app/components/input-range.tsx`: Custom slider input component for numeric configuration values.
- `app/components/mask.tsx`: Manages mask prompt templates, avatar presentation, and mask configuration dialogs
- `app/components/mcp-market.tsx`: Provides the MCP server management page to configure, inspect, and poll status/tools for Model Context Protocol servers
- `app/components/model-config.tsx`: Renders configuration controls for LLM parameters (model, temperature, top_p, max_tokens, penalties, system prompts, history count)
- `app/components/new-chat.tsx`: Displays the new chat initialization screen with quick-start mask options
- `app/components/plugin.tsx`: Allows browsing, importing, configuring, and parsing OpenAPI function tools for chat sessions
- `app/components/message-selector.tsx`: Provides UI controls to filter, search, and batch select chat messages
- `app/components/search-chat.tsx`: Renders the full-text search interface across saved browser chat sessions
- `app/components/ui-lib.tsx`: Shared base UI library providing Modal, Popover, Toast, ListItem, Input, Select, and dynamic modal/toast triggers
- `app/components/sidebar.tsx`: Main sidebar navigation component with draggable resize handlers, hotkey listeners, MCP status checking, and session navigation
- `app/components/settings.tsx`: Settings page view and modals for prompt template editing, search, model provider parameters, and sync options
- `app/components/realtime-chat/realtime-chat.tsx`: Interactive real-time audio and text chat client leveraging the RTClient library for bidirectional LLM audio streaming
- `app/components/realtime-chat/realtime-config.tsx`: Configuration component for Realtime Chat API provider (OpenAI/Azure), model selection, voice, and temperature
- `app/components/sd/sd.tsx`: Stability AI image generation view displaying task statuses, prompts, and generated output images
- `app/components/sd/sd-panel.tsx`: Form controls and parameter definitions (prompts, aspect ratio, style, seed) for Stable Diffusion models
- `app/components/sd/sd-sidebar.tsx`: Sidebar interface for configuring and dispatching Stable Diffusion generation tasks
- `app/components/tts-config.tsx`: Text-to-speech engine, model, voice, and speed setting controls
- `app/components/voice-print/voice-print.tsx`: Canvas-based animated audio frequency visualizer for voice interactions

## Public interface
- Home
- Loading
- WindowContent
- useSwitchTheme
- useLoadData
- Chat
- SessionConfigModel
- ChatList
- ChatItem
- Markdown
- PreCode
- Mermaid
- HTMLPreview
- ArtifactsShareButton
- Artifacts
- ExportMessageModal
- MessageExporter
- RenderExport
- AuthPage
- Avatar
- AvatarPicker
- EmojiAvatar
- getEmojiUrl
- ErrorBoundary
- IconButton
- InputRange
- MaskAvatar(props: { avatar: string; model?: ModelType })
- MaskConfig(props: { mask: Mask; updateMask: Updater<Mask>; extraListItems?: JSX.Element; readonly?: boolean; shouldSyncFromGlobal?: boolean })
- McpMarketPage()
- useMessageSelector()
- MessageSelector(props: { selection: Set<string>; updateSelection: Updater<Set<string>>; defaultSelectAll?: boolean; onSelected?: (messages: ChatMessage[]) => void })
- ModelConfigList(props: { modelConfig: ModelConfig; updateConfig: (updater: (config: ModelConfig) => void) => void })
- NewChat()
- PluginPage()
- SearchChatPage()
- SideBar(props: { className?: string })
- useDragSideBar()
- useHotKey()
- SideBarContainer(props: { children: React.ReactNode; onDragStart: (e: MouseEvent) => void; shouldNarrow: boolean; className?: string })
- SideBarHeader(props: { title?: string | React.ReactNode; subTitle?: string | React.ReactNode; logo?: React.ReactNode; children?: React.ReactNode; shouldNarrow?: boolean })
- SideBarBody(props: { children: React.ReactNode; onClick?: (e: React.MouseEvent<HTMLDivElement, MouseEvent>) => void })
- SideBarTail(props: { primaryAction?: React.ReactNode; secondaryAction?: React.ReactNode })
- Modal(props: ModalProps)
- showModal(props: ModalProps)
- Toast(props: ToastProps)
- showToast(content: string, action?: ToastProps['action'], delay?: number)
- Popover(props: { children: JSX.Element; content: JSX.Element; open?: boolean; onClose?: () => void })
- Card(props: { children: JSX.Element[]; className?: string })
- ListItem(props: { title?: string; subTitle?: string | JSX.Element; children?: JSX.Element | JSX.Element[]; icon?: JSX.Element; className?: string; onClick?: (e: MouseEvent) => void; vertical?: boolean })
- List(props: { children: React.ReactNode; id?: string })
- Input(props: InputProps)
- PasswordInput(props: HTMLProps<HTMLInputElement> & { aria?: string })
- Select(props: React.DetailedHTMLProps<React.SelectHTMLAttributes<HTMLSelectElement> & { align?: 'left' | 'center' }, HTMLSelectElement>)
- TTSConfigList(props: { ttsConfig: TTSConfig; updateConfig: (updater: (config: TTSConfig) => void) => void })
- RealtimeChat(props: RealtimeChatProps)
- RealtimeConfigList(props: { realtimeConfig: RealtimeConfig; updateConfig: (updater: (config: RealtimeConfig) => void) => void })
- Sd()
- ControlParam(props: { columns: any[]; data: any; onChange: (field: string, val: any) => void })
- ControlParamItem(props: { title: string; subTitle?: string; required?: boolean; children?: JSX.Element | JSX.Element[]; className?: string })
- VoicePrint(props: { frequencies?: Uint8Array; isActive?: boolean })

## Dependencies
- react
- react-router-dom
- next/dynamic
- next/image
- @hello-pangea/dnd
- react-markdown
- remark-math
- remark-breaks
- rehype-katex
- remark-gfm
- rehype-highlight
- mermaid
- emoji-picker-react
- html-to-image
- nanoid
- use-debounce
- clsx
- lodash-es
- openapi-client-axios
- js-yaml
- react-dom/client
- next/link
- rt-client
- app/store
- app/locales
- app/constant
- app/utils
- app/config/client
- app/lib/audio
- app/mcp/actions

## AI touchpoints [AI]
- `app/components/auth.tsx`
- `app/components/chat.tsx`
- `app/components/mask.tsx`
- `app/components/model-config.tsx`
- `app/components/realtime-chat/realtime-config.tsx`
- `app/components/sd/sd-panel.tsx`
- `app/components/sd/sd.tsx`
- `app/components/settings.tsx`
- `app/components/home.tsx`
- `app/components/emoji.tsx`
- `app/components/mcp-market.tsx`
- `app/components/plugin.tsx`
- `app/components/realtime-chat/realtime-chat.tsx`
- `app/components/tts-config.tsx`
- `app/components/sd/sd-sidebar.tsx`

## Open questions
- How does the MCP action state synchronize real-time tool availability changes between the server/daemon and the client UI without polling?
