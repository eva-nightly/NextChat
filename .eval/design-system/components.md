# Components

Every row is an applied `// @uxid` identifier. Ids are path-derived and permanent.

| identifier | file | flow | type | description |
| --- | --- | --- | --- | --- |
| `app/components/artifacts::Artifacts` | app/components/artifacts.tsx | all | component | Function component. Hooks: useParams, useState, useRef, useEffect. Renders: div, a, IconButton, GithubIcon, ReloadButtonIcon, ArtifactsShareButton, Loading, HTMLPreview. |
| `app/components/artifacts::ArtifactsShareButton` | app/components/artifacts.tsx | all | component | Function component. Props: getCode, id, style, fileName. Hooks: useState, useMemo. Renders: div, a, IconButton, LoadingButtonIcon, ExportIcon, Modal, DownloadIcon, CopyIcon. |
| `app/components/artifacts::HTMLPreview` | app/components/artifacts.tsx | all | component | Wrapped component. Hooks: useRef, useState, useEffect, useImperativeHandle, useMemo. Renders: iframe. |
| `app/components/auth::AuthPage` | app/components/auth.tsx | all | component | Function component. Hooks: useNavigate, useAccessStore, useEffect. Renders: div, TopBanner, IconButton, LeftIcon, BotIcon, PasswordInput. |
| `app/components/auth::TopBanner` | app/components/auth.tsx | all | component | Function component. Hooks: useState, useMobileScreen, useEffect. Renders: div, span, a, Logo, Arrow, Delete. |
| `app/components/button::IconButton` | app/components/button.tsx | all | component | Function component. Renders: button, div. |
| `app/components/chat-list::ChatItem` | app/components/chat-list.tsx | all | component | Function component. Hooks: useRef, useEffect, useLocation. Renders: div, Draggable, MaskAvatar, DeleteIcon. |
| `app/components/chat-list::ChatList` | app/components/chat-list.tsx | all | component | Function component. Hooks: useChatStore, useNavigate, useMobileScreen. Renders: div, DragDropContext, Droppable, ChatItem. |
| `app/components/chat::Chat` | app/components/chat.tsx | all | component | Function component. Hooks: useChatStore. Renders: _Chat. |
| `app/components/chat::ChatAction` | app/components/chat.tsx | all | component | Function component. Hooks: useRef, useState. Renders: div. |
| `app/components/chat::ChatActions` | app/components/chat.tsx | all | component | Function component. Hooks: useAppConfig, useNavigate, useChatStore, usePluginStore, useAllModels, useMemo, +3 more. Renders: div, ChatAction, StopIcon, BottomIcon, SettingsIcon, LoadingButtonIcon, ImageIcon. |
| `app/components/chat::ClearContextDivider` | app/components/chat.tsx | all | component | Function component. Hooks: useChatStore. Renders: div. |
| `app/components/chat::DeleteImageButton` | app/components/chat.tsx | all | component | Function component. Renders: div, DeleteIcon. |
| `app/components/chat::EditMessageModal` | app/components/chat.tsx | all | component | Function component. Hooks: useChatStore, useState. Renders: div, input, Modal, IconButton, CancelIcon, ConfirmIcon, List, ListItem. |
| `app/components/chat::MCPAction` | app/components/chat.tsx | all | component | Arrow function component. Hooks: useNavigate, useAccessStore, useState, useEffect. Renders: ChatAction, McpToolIcon. |
| `app/components/chat::PromptHints` | app/components/chat.tsx | all | component | Function component. Hooks: useState, useRef, useEffect. Renders: div. |
| `app/components/chat::PromptToast` | app/components/chat.tsx | all | component | Function component. Hooks: useChatStore. Renders: div, span, BrainIcon, SessionConfigModel. |
| `app/components/chat::SessionConfigModel` | app/components/chat.tsx | all | component | Function component. Hooks: useChatStore, useMaskStore, useNavigate. Renders: div, Modal, IconButton, ResetIcon, CopyIcon, MaskConfig, ListItem. |
| `app/components/chat::ShortcutKeyModal` | app/components/chat.tsx | all | component | Function component. Renders: div, span, Modal, IconButton, ConfirmIcon. |
| `app/components/emoji::Avatar` | app/components/emoji.tsx | all | component | Function component. Renders: div, LlmIcon, EmojiAvatar. |
| `app/components/emoji::AvatarPicker` | app/components/emoji.tsx | all | component | Function component. Renders: EmojiPicker. |
| `app/components/emoji::EmojiAvatar` | app/components/emoji.tsx | all | component | Function component. Renders: Emoji. |
| `app/components/error::ErrorBoundary` | app/components/error.tsx | all | component | Class component. Renders: div, h2, pre, code, a, IconButton, GithubIcon, ResetIcon. |
| `app/components/exporter::ExportMessageModal` | app/components/exporter.tsx | all | component | Function component. Renders: div, Modal, MessageExporter. |
| `app/components/exporter::ImagePreviewer` | app/components/exporter.tsx | all | component | Function component. Hooks: useChatStore, useAppConfig, useRef, useMobileScreen. Renders: div, span, img, PreviewActions, NextImage, MaskAvatar, Avatar, Markdown. |
| `app/components/exporter::JsonPreviewer` | app/components/exporter.tsx | all | component | Function component. Renders: div, PreviewActions, Markdown. |
| `app/components/exporter::MarkdownPreviewer` | app/components/exporter.tsx | all | component | Function component. Renders: div, pre, PreviewActions. |
| `app/components/exporter::MessageExporter` | app/components/exporter.tsx | all | component | Function component. Hooks: useSteps, useState, useChatStore, useMessageSelector, useMemo. Renders: div, option, input, MarkdownPreviewer, JsonPreviewer, ImagePreviewer, Steps, List, +1 more. |
| `app/components/exporter::PreviewActions` | app/components/exporter.tsx | all | component | Function component. Hooks: useState, useAppConfig. Renders: input, div, IconButton, CopyIcon, DownloadIcon, LoadingIcon, ShareIcon, RenderExport. |
| `app/components/exporter::RenderExport` | app/components/exporter.tsx | all | component | Function component. Hooks: useRef, useEffect. Renders: div, Markdown. |
| `app/components/exporter::Steps` | app/components/exporter.tsx | all | component | Function component. Renders: div, span. |
| `app/components/home::Home` | app/components/home.tsx | all | component | Function component. Hooks: useSwitchTheme, useLoadData, useHtmlLang, useEffect, useHasHydrated. Renders: Loading, ErrorBoundary, Router, Screen. |
| `app/components/home::Loading` | app/components/home.tsx | all | component | Function component. Renders: div, BotIcon, LoadingIcon. |
| `app/components/home::Screen` | app/components/home.tsx | all | component | Function component. Hooks: useAppConfig, useLocation, useMobileScreen, useEffect. Renders: div, Routes, Route, Artifacts, AuthPage, Sd, SideBar. |
| `app/components/home::WindowContent` | app/components/home.tsx | all | component | Function component. Renders: div. |
| `app/components/input-range::InputRange` | app/components/input-range.tsx | all | component | Function component. Props: onChange, title, value, className, min, max, +2 more. Renders: div, input. |
| `app/components/markdown::CustomCode` | app/components/markdown.tsx | all | component | Function component. Hooks: useChatStore, useAppConfig, useRef, useState, useEffect. Renders: div, button, code. |
| `app/components/markdown::Markdown` | app/components/markdown.tsx | all | component | Function component. Hooks: useRef. Renders: div, LoadingIcon, MarkdownContent. |
| `app/components/markdown::Mermaid` | app/components/markdown.tsx | all | component | Function component. Hooks: useRef, useState, useEffect. Renders: div. |
| `app/components/markdown::PreCode` | app/components/markdown.tsx | all | component | Function component. Hooks: useRef, useState, useWindowSize, useChatStore, useDebouncedCallback, useAppConfig, +1 more. Renders: pre, span, Mermaid, FullScreen, ArtifactsShareButton, IconButton, ReloadButtonIcon, HTMLPreview. |
| `app/components/mask::ContextPromptItem` | app/components/mask.tsx | all | component | Function component. Hooks: useState. Renders: div, option, DragIcon, Select, Input, IconButton, DeleteIcon. |
| `app/components/mask::ContextPrompts` | app/components/mask.tsx | all | component | Function component. Renders: div, DragDropContext, Droppable, Draggable, ContextPromptItem, AddIcon, IconButton. |
| `app/components/mask::MaskAvatar` | app/components/mask.tsx | all | component | Function component. Renders: Avatar. |
| `app/components/mask::MaskConfig` | app/components/mask.tsx | all | component | Function component. Hooks: useState, useAppConfig. Renders: div, input, ContextPrompts, List, ListItem, Popover, AvatarPicker, MaskAvatar. |
| `app/components/mask::MaskPage` | app/components/mask.tsx | all | component | Function component. Hooks: useNavigate, useMaskStore, useChatStore, useState. Renders: div, input, option, ErrorBoundary, IconButton, DownloadIcon, UploadIcon, CloseIcon, +1 more. |
| `app/components/mcp-market::McpMarketPage` | app/components/mcp-market.tsx | all | component | Function component. Hooks: useNavigate, useAccessStore, useState, useEffect. Renders: div, input, span, a, ListItem, IconButton, DeleteIcon, AddIcon, +2 more. |
| `app/components/message-selector::MessageSelector` | app/components/message-selector.tsx | all | component | Function component. Hooks: useChatStore, useMemo, useAppConfig, useState, useShiftRange, useEffect. Renders: div, input, IconButton, Avatar, MaskAvatar. |
| `app/components/model-config::ModelConfigList` | app/components/model-config.tsx | all | component | Function component. Hooks: useAllModels. Renders: optgroup, option, input, ListItem, Select, InputRange. |
| `app/components/new-chat::MaskItem` | app/components/new-chat.tsx | all | component | Function component. Renders: div, MaskAvatar. |
| `app/components/new-chat::NewChat` | app/components/new-chat.tsx | all | component | Function component. Hooks: useChatStore, useMaskStore, useMaskGroup, useNavigate, useAppConfig, useRef, +3 more. Renders: div, IconButton, LeftIcon, EmojiAvatar, EyeIcon, LightningIcon, MaskItem. |
| `app/components/plugin::PluginPage` | app/components/plugin.tsx | all | component | Function component. Hooks: useNavigate, usePluginStore, useState, useDebouncedCallback. Renders: div, a, input, small, select, option, ErrorBoundary, IconButton, +4 more. |
| `app/components/realtime-chat/realtime-chat::RealtimeChat` | app/components/realtime-chat/realtime-chat.tsx | all | component | Function component. Props: onClose, onStartVoice, onPausedVoice. Hooks: useChatStore, useAppConfig, useState, useRef, useEffect. Renders: div, VoicePrint, IconButton, VoiceIcon, VoiceOffIcon, PowerIcon. |
| `app/components/realtime-chat/realtime-config::RealtimeConfigList` | app/components/realtime-chat/realtime-config.tsx | all | component | Function component. Renders: input, option, ListItem, Select, PasswordInput, InputRange. |
| `app/components/sd/sd-panel::ControlParam` | app/components/sd/sd-panel.tsx | all | component | Function component. Renders: textarea, option, input, div, ControlParamItem, Select. |
| `app/components/sd/sd-panel::ControlParamItem` | app/components/sd/sd-panel.tsx | all | component | Function component. Renders: div, span. |
| `app/components/sd/sd-panel::SdPanel` | app/components/sd/sd-panel.tsx | all | component | Function component. Hooks: useSdStore. Renders: div, ControlParamItem, IconButton, ControlParam. |
| `app/components/sd/sd-sidebar::SideBar` | app/components/sd/sd-sidebar.tsx | all | component | Function component. Hooks: useHotKey, useMobileScreen, useDragSideBar, useNavigate, useSdStore. Renders: div, a, SideBarContainer, IconButton, ReturnIcon, SDIcon, HistoryIcon, SideBarHeader. |
| `app/components/sd/sd::Sd` | app/components/sd/sd.tsx | all | component | Function component. Hooks: useMobileScreen, useNavigate, useLocation, useMemo, useAppConfig, useRef, +3 more. Renders: div, img, p, span, strong, SideBar, WindowContent, IconButton, +3 more. |
| `app/components/search-chat::SearchChatPage` | app/components/search-chat.tsx | all | component | Function component. Hooks: useNavigate, useChatStore, useState, useRef, useCallback, useEffect. Renders: div, input, ErrorBoundary, IconButton, CloseIcon, EyeIcon. |
| `app/components/settings::CheckButton` | app/components/settings.tsx | all | component | Function component. Hooks: useSyncStore, useMemo, useState. Renders: IconButton, ConnectionIcon, LoadingIcon, CloudSuccessIcon, CloudFailIcon. |
| `app/components/settings::DangerItems` | app/components/settings.tsx | all | component | Function component. Hooks: useChatStore, useAppConfig. Renders: List, ListItem, IconButton. |
| `app/components/settings::EditPromptModal` | app/components/settings.tsx | all | component | Function component. Hooks: usePromptStore. Renders: div, input, Modal, IconButton, Input. |
| `app/components/settings::Settings` | app/components/settings.tsx | all | component | Function component. Hooks: useNavigate, useState, useAppConfig, useUpdateStore, useAccessStore, useMemo, +2 more. Renders: input, option, div, ListItem, PasswordInput, IconButton, FireIcon, Select, +1 more. |
| `app/components/settings::SyncConfigModal` | app/components/settings.tsx | all | component | Function component. Hooks: useSyncStore. Renders: div, select, option, input, Modal, CheckButton, IconButton, ConfirmIcon, +2 more. |
| `app/components/settings::SyncItems` | app/components/settings.tsx | all | component | Function component. Hooks: useSyncStore, useChatStore, usePromptStore, useMaskStore, useMemo, useState. Renders: div, List, ListItem, IconButton, ConfigIcon, ResetIcon, UploadIcon. |
| `app/components/settings::UserPromptModal` | app/components/settings.tsx | all | component | Function component. Hooks: usePromptStore, useState, useEffect. Renders: div, input, Modal, IconButton, AddIcon, ClearIcon, EditIcon, EyeIcon. |
| `app/components/sidebar::SideBar` | app/components/sidebar.tsx | all | component | Function component. Hooks: useHotKey, useDragSideBar, useState, useNavigate, useAppConfig, useChatStore, +1 more. Renders: div, a, SideBarContainer, SideBarHeader, NextChatIcon, IconButton, MaskIcon, McpIcon. |
| `app/components/sidebar::SideBarBody` | app/components/sidebar.tsx | all | component | Function component. Renders: div. |
| `app/components/sidebar::SideBarContainer` | app/components/sidebar.tsx | all | component | Function component. Hooks: useMobileScreen, useMemo. Renders: div, DragIcon. |
| `app/components/sidebar::SideBarHeader` | app/components/sidebar.tsx | all | component | Function component. Renders: div, Fragment. |
| `app/components/sidebar::SideBarTail` | app/components/sidebar.tsx | all | component | Function component. Renders: div. |
| `app/components/tts-config::TTSConfigList` | app/components/tts-config.tsx | all | component | Function component. Renders: input, option, ListItem, Select, InputRange. |
| `app/components/ui-lib::Card` | app/components/ui-lib.tsx | all | component | Function component. Renders: div. |
| `app/components/ui-lib::FullScreen` | app/components/ui-lib.tsx | all | component | Function component. Hooks: useRef, useState, useCallback, useEffect. Renders: div, IconButton, MinIcon, MaxIcon. |
| `app/components/ui-lib::Input` | app/components/ui-lib.tsx | all | component | Function component. Props: props: InputProps. Renders: textarea. |
| `app/components/ui-lib::List` | app/components/ui-lib.tsx | all | component | Function component. Renders: div. |
| `app/components/ui-lib::ListItem` | app/components/ui-lib.tsx | all | component | Function component. Renders: div. |
| `app/components/ui-lib::Loading` | app/components/ui-lib.tsx | all | component | Function component. Renders: div, LoadingIcon. |
| `app/components/ui-lib::Modal` | app/components/ui-lib.tsx | all | component | Function component. Props: props: ModalProps. Hooks: useEffect, useState. Renders: div, MinIcon, MaxIcon, CloseIcon. |
| `app/components/ui-lib::PasswordInput` | app/components/ui-lib.tsx | all | component | Function component. Hooks: useState. Renders: div, input, IconButton, EyeIcon, EyeOffIcon. |
| `app/components/ui-lib::Popover` | app/components/ui-lib.tsx | all | component | Function component. Renders: div. |
| `app/components/ui-lib::PromptInput` | app/components/ui-lib.tsx | all | component | Function component. Hooks: useState. Renders: textarea. |
| `app/components/ui-lib::Select` | app/components/ui-lib.tsx | all | component | Function component. Props: props: object. Renders: div, select, DownIcon. |
| `app/components/ui-lib::Selector` | app/components/ui-lib.tsx | all | component | Function component. Hooks: useState. Renders: div, List, ListItem, Avatar. |
| `app/components/ui-lib::Toast` | app/components/ui-lib.tsx | all | component | Function component. Props: props: ToastProps. Renders: div, span, button. |
| `app/components/voice-print/voice-print::VoicePrint` | app/components/voice-print/voice-print.tsx | all | component | Function component. Props: frequencies, isActive. Hooks: useRef, useCallback, useEffect. Renders: div, canvas. |
| `app/layout::RootLayout` | app/layout.tsx | all | component | Function component. Props: children. Renders: html, head, meta, link, script, body, SpeedInsights, GoogleTagManager, +1 more. |
| `app/page::App` | app/page.tsx | all | component | Function component. Renders: Home, Analytics. |

## Coverage

- all: 493 identifier(s)

## Design system components

88 component(s) carry a stable `@uxid`. 1 declare variants (1 axis/axes, 2 value(s) in total), read from `cva()` calls, class maps, prop unions and conditional class branches.

| @uxid | component | file | variants | states | uses | notes |
| --- | --- | --- | --- | --- | --- | --- |
| "app/components/artifacts::HTMLPreview" | HTMLPreview | `app/components/artifacts.tsx` |  |  | 1 | Renders an HTML artifact as a live preview inside the artifacts view. |
| "app/components/artifacts::ArtifactsShareButton" | ArtifactsShareButton | `app/components/artifacts.tsx` |  |  | 1 | Button for sharing an artifact from the artifacts view. |
| "app/components/artifacts::Artifacts" | Artifacts | `app/components/artifacts.tsx` |  |  | 1 | Container page for viewing an artifact, hosting the HTML preview and its share action. |
| "app/components/auth::AuthPage" | AuthPage | `app/components/auth.tsx` |  |  | 1 | Authentication screen shown before the user can access the chat. |
| "app/components/auth::TopBanner" | TopBanner | `app/components/auth.tsx` |  |  | 0 | Banner displayed at the top of the auth page. |
| "app/components/button::IconButton" | IconButton | `app/components/button.tsx` |  |  | 113 | General-purpose button with an icon, reused across the application. |
| "app/components/chat-list::ChatItem" | ChatItem | `app/components/chat-list.tsx` |  |  | 0 | A single conversation entry within the chat list. |
| "app/components/chat-list::ChatList" | ChatList | `app/components/chat-list.tsx` |  |  | 1 | List of conversations, composed of ChatItem entries, used for switching between sessions. |
| "app/components/chat::MCPAction" | MCPAction | `app/components/chat.tsx` |  |  | 0 | Chat action related to MCP functionality within the chat view. |
| "app/components/chat::SessionConfigModel" | SessionConfigModel | `app/components/chat.tsx` |  |  | 0 | Modal for configuring the current chat session. |
| "app/components/chat::PromptToast" | PromptToast | `app/components/chat.tsx` |  |  | 0 | Toast displayed in the chat relating to prompts. |
| "app/components/chat::PromptHints" | PromptHints | `app/components/chat.tsx` |  |  | 0 | Suggestion list of prompt hints shown while composing a message. |
| "app/components/chat::ClearContextDivider" | ClearContextDivider | `app/components/chat.tsx` |  |  | 0 | Divider marking the point in a conversation where context was cleared. |
| "app/components/chat::ChatAction" | ChatAction | `app/components/chat.tsx` |  |  | 4 | A single action control in the chat input toolbar. |
| "app/components/chat::ChatActions" | ChatActions | `app/components/chat.tsx` |  |  | 0 | Toolbar grouping ChatAction controls around the message input. |
| "app/components/chat::EditMessageModal" | EditMessageModal | `app/components/chat.tsx` |  |  | 0 | Modal for editing an existing chat message. |
| "app/components/chat::DeleteImageButton" | DeleteImageButton | `app/components/chat.tsx` |  |  | 0 | Button for removing an attached image from the chat input. |
| "app/components/chat::ShortcutKeyModal" | ShortcutKeyModal | `app/components/chat.tsx` |  |  | 0 | Modal listing keyboard shortcuts available in the chat. |
| "app/components/chat::Chat" | Chat | `app/components/chat.tsx` |  |  | 2 | Main conversation view containing the message list, input area and related modals; uses t39 for timing. |
| "app/components/emoji::AvatarPicker" | AvatarPicker | `app/components/emoji.tsx` |  |  | 2 | Picker for choosing an emoji avatar. |
| "app/components/emoji::Avatar" | Avatar | `app/components/emoji.tsx` |  |  | 8 | Displays an avatar for a participant in the chat. |
| "app/components/emoji::EmojiAvatar" | EmojiAvatar | `app/components/emoji.tsx` |  |  | 3 | Avatar variant rendered from an emoji. |
| "app/components/error::ErrorBoundary" | ErrorBoundary | `app/components/error.tsx` |  |  | 0 | Catches rendering errors and shows a fallback instead of crashing the app. |
| "app/components/exporter::ExportMessageModal" | ExportMessageModal | `app/components/exporter.tsx` |  |  | 1 | Modal that wraps the message export flow. |
| "app/components/exporter::Steps" | Steps | `app/components/exporter.tsx` |  |  | 0 | Step indicator for the multi-step export flow. |
| "app/components/exporter::MessageExporter" | MessageExporter | `app/components/exporter.tsx` |  |  | 0 | Orchestrates exporting chat messages, including format selection and preview. |
| "app/components/exporter::RenderExport" | RenderExport | `app/components/exporter.tsx` |  |  | 0 | Renders the selected messages in the form used for export. |
| "app/components/exporter::PreviewActions" | PreviewActions | `app/components/exporter.tsx` |  |  | 0 | Actions available on an export preview. |
| "app/components/exporter::ImagePreviewer" | ImagePreviewer | `app/components/exporter.tsx` |  |  | 0 | Preview of the export rendered as an image. |
| "app/components/exporter::MarkdownPreviewer" | MarkdownPreviewer | `app/components/exporter.tsx` |  |  | 0 | Preview of the export rendered as Markdown. |
| "app/components/exporter::JsonPreviewer" | JsonPreviewer | `app/components/exporter.tsx` |  |  | 0 | Preview of the export rendered as JSON. |
| "app/components/home::Loading" | Loading | `app/components/home.tsx` |  |  | 1 | Loading indicator shown while the application or a screen is loading. |
| "app/components/home::WindowContent" | WindowContent | `app/components/home.tsx` |  |  | 1 | Wrapper for the main window content area, sized by t29. |
| "app/components/home::Screen" | Screen | `app/components/home.tsx` |  |  | 0 | Top-level screen layout combining the sidebar (t28) and window content. |
| "app/components/home::Home" | Home | `app/components/home.tsx` |  |  | 1 | Application root that mounts the Screen and overall app shell. |
| "app/components/input-range::InputRange" | InputRange | `app/components/input-range.tsx` |  |  | 8 | Range slider input used in settings and configuration forms. |
| "app/components/markdown::Mermaid" | Mermaid | `app/components/markdown.tsx` |  |  | 0 | Renders Mermaid diagrams found in Markdown content. |
| "app/components/markdown::PreCode" | PreCode | `app/components/markdown.tsx` |  |  | 0 | Renders a preformatted code block within Markdown, styled with the prettylights syntax tokens. |
| "app/components/markdown::CustomCode" | CustomCode | `app/components/markdown.tsx` |  |  | 0 | Custom code element rendering within Markdown content. |
| "app/components/markdown::Markdown" | Markdown | `app/components/markdown.tsx` |  |  | 4 | Renders Markdown message content, using the markdown.scss palette (t6–t9, t22, t23, t37, t38) for text, borders and surfaces. |
| "app/components/mask::MaskAvatar" | MaskAvatar | `app/components/mask.tsx` |  |  | 7 | Avatar shown for a mask (preset persona), used wherever a mask is listed or edited. |
| "app/components/mask::MaskConfig" | MaskConfig | `app/components/mask.tsx` |  |  | 1 | Editing form for a single mask: its identity and its model and context settings. |
| "app/components/mask::ContextPromptItem" | ContextPromptItem | `app/components/mask.tsx` |  |  | 0 | One editable prompt entry within a mask's context prompt list. |
| "app/components/mask::ContextPrompts" | ContextPrompts | `app/components/mask.tsx` |  |  | 1 | The ordered list of context prompts attached to a mask, composed of @app/components/mask::ContextPromptItem. |
| "app/components/mask::MaskPage" | MaskPage | `app/components/mask.tsx` |  |  | 1 | Full page for browsing, creating and managing masks. |
| "app/components/mcp-market::McpMarketPage" | McpMarketPage | `app/components/mcp-market.tsx` |  | active | 1 | Page for browsing and managing MCP (Model Context Protocol) entries offered in a market view. |
| "app/components/message-selector::MessageSelector" | MessageSelector | `app/components/message-selector.tsx` |  | selection | 1 | UI for selecting one or more messages from a conversation, e.g. for export or sharing. |
| "app/components/model-config::ModelConfigList" | ModelConfigList | `app/components/model-config.tsx` |  |  | 2 | List of controls for configuring model parameters; reused by mask and settings screens. |
| "app/components/new-chat::MaskItem" | MaskItem | `app/components/new-chat.tsx` |  |  | 0 | A single selectable mask entry displayed on the new-chat screen. |
| "app/components/new-chat::NewChat" | NewChat | `app/components/new-chat.tsx` |  |  | 1 | Screen for starting a new conversation, offering masks to pick from via @app/components/new-chat::MaskItem. |
| "app/components/plugin::PluginPage" | PluginPage | `app/components/plugin.tsx` |  |  | 1 | Page for viewing and managing plugins. |
| "app/components/realtime-chat/realtime-chat::RealtimeChat" | RealtimeChat | `app/components/realtime-chat/realtime-chat.tsx` |  |  | 1 | Realtime (voice) chat interface, a distinct mode from the standard text chat. |
| "app/components/realtime-chat/realtime-config::RealtimeConfigList" | RealtimeConfigList | `app/components/realtime-chat/realtime-config.tsx` |  |  | 1 | Settings list for the realtime chat mode. |
| "app/components/sd/sd-panel::ControlParamItem" | ControlParamItem | `app/components/sd/sd-panel.tsx` |  | placeholder, required | 0 | A single parameter control within the image-generation panel. |
| "app/components/sd/sd-panel::ControlParam" | ControlParam | `app/components/sd/sd-panel.tsx` |  | placeholder, required | 0 | Group of image-generation parameter controls built from @app/components/sd/sd-panel::ControlParamItem. |
| "app/components/sd/sd-panel::SdPanel" | SdPanel | `app/components/sd/sd-panel.tsx` |  | placeholder, required | 1 | The main parameter panel for the image-generation (sd) feature. |
| "app/components/sd/sd-sidebar::SideBar" | SideBar | `app/components/sd/sd-sidebar.tsx` |  |  | 2 | Sidebar specific to the image-generation feature, separate from the app-wide @app/components/sidebar::SideBar. |
| "app/components/sd/sd::Sd" | Sd | `app/components/sd/sd.tsx` |  |  | 2 | Top-level container for the image-generation feature, combining its sidebar and panel. |
| "app/components/search-chat::SearchChatPage" | SearchChatPage | `app/components/search-chat.tsx` |  |  | 0 | Page for searching across chat history. |
| "app/components/settings::EditPromptModal" | EditPromptModal | `app/components/settings.tsx` |  |  | 0 | Modal for editing a single user-defined prompt. |
| "app/components/settings::UserPromptModal" | UserPromptModal | `app/components/settings.tsx` |  |  | 0 | Modal listing and managing the user's custom prompts, opening @app/components/settings::EditPromptModal for edits. |
| "app/components/settings::DangerItems" | DangerItems | `app/components/settings.tsx` |  |  | 0 | Settings section grouping destructive actions such as resetting or clearing data. |
| "app/components/settings::CheckButton" | CheckButton | `app/components/settings.tsx` |  |  | 0 | Button in settings that triggers a check and reports its result inline. |
| "app/components/settings::SyncConfigModal" | SyncConfigModal | `app/components/settings.tsx` |  |  | 0 | Modal for configuring data synchronisation. |
| "app/components/settings::SyncItems" | SyncItems | `app/components/settings.tsx` |  |  | 0 | Settings section for sync status and actions, opening @app/components/settings::SyncConfigModal. |
| "app/components/settings::Settings" | Settings | `app/components/settings.tsx` |  |  | 1 | The full settings page composing the configuration lists, sync and danger sections. |
| "app/components/sidebar::SideBarContainer" | SideBarContainer | `app/components/sidebar.tsx` |  |  | 1 | Layout shell for the app-wide sidebar; sized by the sidebar width token. |
| "app/components/sidebar::SideBarHeader" | SideBarHeader | `app/components/sidebar.tsx` |  |  | 1 | Top region of the sidebar holding title and primary actions. |
| "app/components/sidebar::SideBarBody" | SideBarBody | `app/components/sidebar.tsx` |  |  | 1 | Scrollable middle region of the sidebar, used for the conversation list. |
| "app/components/sidebar::SideBarTail" | SideBarTail | `app/components/sidebar.tsx` |  |  | 1 | Bottom region of the sidebar for secondary actions and navigation. |
| "app/components/sidebar::SideBar" | SideBar | `app/components/sidebar.tsx` |  |  | 2 | The assembled app-wide sidebar, composed of the container, header, body and tail parts. |
| "app/components/tts-config::TTSConfigList" | TTSConfigList | `app/components/tts-config.tsx` |  |  | 1 | Settings list for text-to-speech options. |
| "app/components/ui-lib::Popover" | Popover | `app/components/ui-lib.tsx` | align (2) |  | 2 | Shared primitive for anchored floating content. |
| "app/components/ui-lib::Card" | Card | `app/components/ui-lib.tsx` |  |  | 0 | Shared surface container; uses the card shadow token. |
| "app/components/ui-lib::ListItem" | ListItem | `app/components/ui-lib.tsx` |  |  | 119 | Shared row with label and control, the building block of settings-style lists. |
| "app/components/ui-lib::List" | List | `app/components/ui-lib.tsx` |  |  | 19 | Shared grouped container for @app/components/ui-lib::ListItem rows. |
| "app/components/ui-lib::Loading" | Loading | `app/components/ui-lib.tsx` |  |  | 11 | Shared loading indicator. |
| "app/components/ui-lib::Modal" | Modal | `app/components/ui-lib.tsx` |  |  | 12 | Shared dialog primitive; padded by the modal padding token and used by all settings modals. |
| "app/components/ui-lib::Toast" | Toast | `app/components/ui-lib.tsx` |  |  | 0 | Shared transient notification. |
| "app/components/ui-lib::Input" | Input | `app/components/ui-lib.tsx` |  |  | 2 | Shared text input primitive. |
| "app/components/ui-lib::PasswordInput" | PasswordInput | `app/components/ui-lib.tsx` |  |  | 27 | A text input intended for entering passwords, part of the shared ui-lib. |
| "app/components/ui-lib::Select" | Select | `app/components/ui-lib.tsx` |  |  | 17 | A select control for choosing one option from a list, part of the shared ui-lib. |
| "app/components/ui-lib::PromptInput" | PromptInput | `app/components/ui-lib.tsx` |  |  | 0 | An input used for entering a prompt, part of the shared ui-lib. |
| "app/components/ui-lib::Selector" | Selector | `app/components/ui-lib.tsx` |  |  | 6 | A selector control for picking from a set of items, part of the shared ui-lib and distinct from the plain Select. |
| "app/components/ui-lib::FullScreen" | FullScreen | `app/components/ui-lib.tsx` |  |  | 1 | A wrapper that presents its content in a full-screen mode, part of the shared ui-lib. |
| "app/components/voice-print/voice-print::VoicePrint" | VoicePrint | `app/components/voice-print/voice-print.tsx` |  |  | 1 | A component for displaying a voice print, living in its own voice-print module. |
| "app/layout::RootLayout" | RootLayout | `app/layout.tsx` |  |  | 0 | The root layout that wraps every page and applies the global styles and theme variables. |
| "app/page::App" | App | `app/page.tsx` |  |  | 0 | The top-level app page that mounts the application UI inside the root layout. |

### Variants, in full

#### Popover (`app/components/ui-lib.tsx`:30)

| axis | value | classes | call sites |
| --- | --- | --- | --- |
| `align` | `left` | _declared by the prop type only_ | 0 |
| `align` | `center` | _declared by the prop type only_ | 0 |

Rendered 2 time(s) in 2 other file(s).
