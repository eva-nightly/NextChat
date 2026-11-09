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

- all: 88 identifier(s)

## Design system components

88 component(s) carry a stable `@uxid`. 1 declare variants (1 axis/axes, 2 value(s) in total), read from `cva()` calls, class maps, prop unions and conditional class branches.

| @uxid | component | file | variants | states | uses | notes |
| --- | --- | --- | --- | --- | --- | --- |
| "app/components/artifacts::HTMLPreview" | HTMLPreview | `app/components/artifacts.tsx` |  |  | 1 | Renders HTML content as a live preview inside the artifacts view. |
| "app/components/artifacts::ArtifactsShareButton" | ArtifactsShareButton | `app/components/artifacts.tsx` |  |  | 1 | Button for sharing an artifact from the artifacts view. |
| "app/components/artifacts::Artifacts" | Artifacts | `app/components/artifacts.tsx` |  |  | 1 | Top-level artifacts page that hosts the HTML preview and its share action. |
| "app/components/auth::AuthPage" | AuthPage | `app/components/auth.tsx` |  |  | 1 | Authentication / access entry page shown before the user reaches the chat. |
| "app/components/auth::TopBanner" | TopBanner | `app/components/auth.tsx` |  |  | 0 | Banner displayed at the top of the auth page. |
| "app/components/button::IconButton" | IconButton | `app/components/button.tsx` |  |  | 113 | Generic icon-bearing button used throughout the UI. |
| "app/components/chat-list::ChatItem" | ChatItem | `app/components/chat-list.tsx` |  |  | 0 | A single session entry within the chat list. |
| "app/components/chat-list::ChatList" | ChatList | `app/components/chat-list.tsx` |  |  | 1 | Sidebar list of chat sessions composed of ChatItem entries. |
| "app/components/chat::MCPAction" | MCPAction | `app/components/chat.tsx` |  |  | 0 | Action control within the chat for MCP-related functionality. |
| "app/components/chat::SessionConfigModel" | SessionConfigModel | `app/components/chat.tsx` |  |  | 0 | Modal for configuring the current chat session's settings. |
| "app/components/chat::PromptToast" | PromptToast | `app/components/chat.tsx` |  |  | 0 | Toast shown in the chat area related to the session's prompt/context. |
| "app/components/chat::PromptHints" | PromptHints | `app/components/chat.tsx` |  |  | 0 | List of prompt suggestions surfaced while the user types. |
| "app/components/chat::ClearContextDivider" | ClearContextDivider | `app/components/chat.tsx` |  |  | 0 | Divider marking the point where chat context was cleared. |
| "app/components/chat::ChatAction" | ChatAction | `app/components/chat.tsx` |  |  | 4 | A single action control in the chat input toolbar. |
| "app/components/chat::ChatActions" | ChatActions | `app/components/chat.tsx` |  |  | 0 | Toolbar grouping the ChatAction controls above the chat input. |
| "app/components/chat::EditMessageModal" | EditMessageModal | `app/components/chat.tsx` |  |  | 0 | Modal for editing messages in the current session. |
| "app/components/chat::DeleteImageButton" | DeleteImageButton | `app/components/chat.tsx` |  |  | 0 | Button for removing an attached image from the chat input. |
| "app/components/chat::ShortcutKeyModal" | ShortcutKeyModal | `app/components/chat.tsx` |  |  | 0 | Modal listing available keyboard shortcuts. |
| "app/components/chat::Chat" | Chat | `app/components/chat.tsx` |  |  | 2 | Main conversation view containing the message list, input and chat actions. |
| "app/components/emoji::AvatarPicker" | AvatarPicker | `app/components/emoji.tsx` |  |  | 2 | Picker for choosing an emoji avatar. |
| "app/components/emoji::Avatar" | Avatar | `app/components/emoji.tsx` |  |  | 8 | Displays an avatar for a user or model. |
| "app/components/emoji::EmojiAvatar" | EmojiAvatar | `app/components/emoji.tsx` |  |  | 3 | Avatar rendered from an emoji. |
| "app/components/error::ErrorBoundary" | ErrorBoundary | `app/components/error.tsx` |  |  | 0 | Catches rendering errors and displays a fallback. |
| "app/components/exporter::ExportMessageModal" | ExportMessageModal | `app/components/exporter.tsx` |  |  | 1 | Modal that wraps the message export flow. |
| "app/components/exporter::Steps" | Steps | `app/components/exporter.tsx` |  |  | 0 | Step indicator for the export process. |
| "app/components/exporter::MessageExporter" | MessageExporter | `app/components/exporter.tsx` |  |  | 0 | Export flow for selecting messages and choosing an output format. |
| "app/components/exporter::RenderExport" | RenderExport | `app/components/exporter.tsx` |  |  | 0 | Renders selected messages for export output. |
| "app/components/exporter::PreviewActions" | PreviewActions | `app/components/exporter.tsx` |  |  | 0 | Action controls shown alongside an export preview. |
| "app/components/exporter::ImagePreviewer" | ImagePreviewer | `app/components/exporter.tsx` |  |  | 0 | Preview of the conversation exported as an image. |
| "app/components/exporter::MarkdownPreviewer" | MarkdownPreviewer | `app/components/exporter.tsx` |  |  | 0 | Preview of the conversation exported as markdown. |
| "app/components/exporter::JsonPreviewer" | JsonPreviewer | `app/components/exporter.tsx` |  |  | 0 | Preview of the conversation exported as JSON. |
| "app/components/home::Loading" | Loading | `app/components/home.tsx` |  |  | 1 | Loading indicator shown while the app or a view initializes. |
| "app/components/home::WindowContent" | WindowContent | `app/components/home.tsx` |  |  | 1 | Container for the main window content area. |
| "app/components/home::Screen" | Screen | `app/components/home.tsx` |  |  | 0 | Overall screen layout combining sidebar and window content. |
| "app/components/home::Home" | Home | `app/components/home.tsx` |  |  | 1 | Application root that mounts the screen and routes. |
| "app/components/input-range::InputRange" | InputRange | `app/components/input-range.tsx` |  |  | 8 | Range slider input control. |
| "app/components/markdown::Mermaid" | Mermaid | `app/components/markdown.tsx` |  |  | 0 | Renders Mermaid diagram code blocks. |
| "app/components/markdown::PreCode" | PreCode | `app/components/markdown.tsx` |  |  | 0 | Preformatted code block wrapper inside rendered markdown. |
| "app/components/markdown::CustomCode" | CustomCode | `app/components/markdown.tsx` |  |  | 0 | Custom inline/code element rendering within markdown. |
| "app/components/markdown::Markdown" | Markdown | `app/components/markdown.tsx` |  |  | 4 | Markdown renderer used for message content, styled by the markdown.scss tokens. |
| "app/components/mask::MaskAvatar" | MaskAvatar | `app/components/mask.tsx` |  |  | 7 | Renders the avatar image or emoji that identifies a mask (assistant persona). |
| "app/components/mask::MaskConfig" | MaskConfig | `app/components/mask.tsx` |  |  | 1 | Editing form for a single mask: its identity and associated model settings. |
| "app/components/mask::ContextPromptItem" | ContextPromptItem | `app/components/mask.tsx` |  |  | 0 | One editable row in a mask's list of context (system/few-shot) prompts. |
| "app/components/mask::ContextPrompts" | ContextPrompts | `app/components/mask.tsx` |  |  | 1 | The ordered list of context prompts attached to a mask, composed of ContextPromptItem rows. |
| "app/components/mask::MaskPage" | MaskPage | `app/components/mask.tsx` |  |  | 1 | Full page for browsing, creating and managing masks. |
| "app/components/mcp-market::McpMarketPage" | McpMarketPage | `app/components/mcp-market.tsx` |  | active | 1 | Page for browsing and managing MCP (Model Context Protocol) entries. |
| "app/components/message-selector::MessageSelector" | MessageSelector | `app/components/message-selector.tsx` |  | selection | 1 | Lets the user pick a subset of messages from a conversation, e.g. for export or sharing. |
| "app/components/model-config::ModelConfigList" | ModelConfigList | `app/components/model-config.tsx` |  |  | 2 | List of settings rows for choosing a model and its parameters. |
| "app/components/new-chat::MaskItem" | MaskItem | `app/components/new-chat.tsx` |  |  | 0 | A selectable mask tile shown on the new-chat screen. |
| "app/components/new-chat::NewChat" | NewChat | `app/components/new-chat.tsx` |  |  | 1 | Entry screen for starting a conversation, offering masks to begin from. |
| "app/components/plugin::PluginPage" | PluginPage | `app/components/plugin.tsx` |  |  | 1 | Page for viewing and managing plugins. |
| "app/components/realtime-chat/realtime-chat::RealtimeChat" | RealtimeChat | `app/components/realtime-chat/realtime-chat.tsx` |  |  | 1 | The realtime (voice/streaming) chat interface. |
| "app/components/realtime-chat/realtime-config::RealtimeConfigList" | RealtimeConfigList | `app/components/realtime-chat/realtime-config.tsx` |  |  | 1 | Settings rows that configure the realtime chat feature. |
| "app/components/sd/sd-panel::ControlParamItem" | ControlParamItem | `app/components/sd/sd-panel.tsx` |  | placeholder, required | 0 | A single control for one image-generation parameter in the SD panel. |
| "app/components/sd/sd-panel::ControlParam" | ControlParam | `app/components/sd/sd-panel.tsx` |  | placeholder, required | 0 | Groups the ControlParamItem controls for the current set of image-generation parameters. |
| "app/components/sd/sd-panel::SdPanel" | SdPanel | `app/components/sd/sd-panel.tsx` |  | placeholder, required | 1 | The main Stable-Diffusion panel where generation parameters are set and submitted. |
| "app/components/sd/sd-sidebar::SideBar" | SideBar | `app/components/sd/sd-sidebar.tsx` |  |  | 2 | Sidebar specific to the Stable-Diffusion area. |
| "app/components/sd/sd::Sd" | Sd | `app/components/sd/sd.tsx` |  |  | 2 | Top-level container for the Stable-Diffusion image feature. |
| "app/components/search-chat::SearchChatPage" | SearchChatPage | `app/components/search-chat.tsx` |  |  | 0 | Page for searching across chat history. |
| "app/components/settings::EditPromptModal" | EditPromptModal | `app/components/settings.tsx` |  |  | 0 | Modal for editing a single user-defined prompt. |
| "app/components/settings::UserPromptModal" | UserPromptModal | `app/components/settings.tsx` |  |  | 0 | Modal listing the user's saved prompts for management. |
| "app/components/settings::DangerItems" | DangerItems | `app/components/settings.tsx` |  |  | 0 | Settings group holding destructive actions such as reset or clear. |
| "app/components/settings::CheckButton" | CheckButton | `app/components/settings.tsx` |  |  | 0 | Button used in settings to trigger a check (e.g. of a connection or configuration) and show its result. |
| "app/components/settings::SyncConfigModal" | SyncConfigModal | `app/components/settings.tsx` |  |  | 0 | Modal for configuring data synchronisation. |
| "app/components/settings::SyncItems" | SyncItems | `app/components/settings.tsx` |  |  | 0 | Settings group for sync-related options and actions. |
| "app/components/settings::Settings" | Settings | `app/components/settings.tsx` |  |  | 1 | The full settings page that assembles the various settings groups and modals. |
| "app/components/sidebar::SideBarContainer" | SideBarContainer | `app/components/sidebar.tsx` |  |  | 1 | Outer shell of the main app sidebar, handling its layout and sizing. |
| "app/components/sidebar::SideBarHeader" | SideBarHeader | `app/components/sidebar.tsx` |  |  | 1 | Top section of the main sidebar with title and header actions. |
| "app/components/sidebar::SideBarBody" | SideBarBody | `app/components/sidebar.tsx` |  |  | 1 | Scrollable middle section of the main sidebar, holding the conversation list. |
| "app/components/sidebar::SideBarTail" | SideBarTail | `app/components/sidebar.tsx` |  |  | 1 | Bottom section of the main sidebar with footer actions. |
| "app/components/sidebar::SideBar" | SideBar | `app/components/sidebar.tsx` |  |  | 2 | The composed main navigation sidebar built from the container, header, body and tail parts. |
| "app/components/tts-config::TTSConfigList" | TTSConfigList | `app/components/tts-config.tsx` |  |  | 1 | Settings rows that configure text-to-speech. |
| "app/components/ui-lib::Popover" | Popover | `app/components/ui-lib.tsx` | align (2) |  | 2 | Generic anchored popover used to show contextual content next to a trigger. |
| "app/components/ui-lib::Card" | Card | `app/components/ui-lib.tsx` |  |  | 0 | Generic surface container for grouping related content. |
| "app/components/ui-lib::ListItem" | ListItem | `app/components/ui-lib.tsx` |  |  | 119 | Generic row with title, optional subtitle and trailing control, used across settings and config lists. |
| "app/components/ui-lib::List" | List | `app/components/ui-lib.tsx` |  |  | 19 | Generic container that stacks ListItem rows. |
| "app/components/ui-lib::Loading" | Loading | `app/components/ui-lib.tsx` |  |  | 11 | Generic loading indicator. |
| "app/components/ui-lib::Modal" | Modal | `app/components/ui-lib.tsx` |  |  | 12 | Generic dialog shell with title, body and action buttons used by the feature modals. |
| "app/components/ui-lib::Toast" | Toast | `app/components/ui-lib.tsx` |  |  | 0 | Transient notification message. |
| "app/components/ui-lib::Input" | Input | `app/components/ui-lib.tsx` |  |  | 2 | Generic text input used throughout forms. |
| "app/components/ui-lib::PasswordInput" | PasswordInput | `app/components/ui-lib.tsx` |  |  | 27 | Text field from the shared UI library for entering a password or other secret value. |
| "app/components/ui-lib::Select" | Select | `app/components/ui-lib.tsx` |  |  | 17 | Shared UI-library dropdown control for choosing a single option from a list. |
| "app/components/ui-lib::PromptInput" | PromptInput | `app/components/ui-lib.tsx` |  |  | 0 | Shared UI-library input intended for composing a prompt; the chat tokens (t26, t39) are the related layout context. |
| "app/components/ui-lib::Selector" | Selector | `app/components/ui-lib.tsx` |  |  | 6 | Shared UI-library picker for selecting among several items; distinct from the native-style Select. |
| "app/components/ui-lib::FullScreen" | FullScreen | `app/components/ui-lib.tsx` |  |  | 1 | Shared UI-library wrapper for presenting its content in a full-screen state, in contrast to the default window sizing (t31, t30). |
| "app/components/voice-print/voice-print::VoicePrint" | VoicePrint | `app/components/voice-print/voice-print.tsx` |  |  | 1 | Visualisation component for voice/audio input, living in its own voice-print module. |
| "app/layout::RootLayout" | RootLayout | `app/layout.tsx` |  |  | 0 | Top-level Next.js layout that wraps every page and is where the global stylesheets (globals.scss, markdown.scss) and theme tokens (t61, t60) apply. |
| "app/page::App" | App | `app/page.tsx` |  |  | 0 | Root page component that mounts the application shell inside the window frame defined by t31, t30, t28 and t29. |

### Variants, in full

#### Popover (`app/components/ui-lib.tsx`:30)

| axis | value | classes | call sites |
| --- | --- | --- | --- |
| `align` | `left` | _declared by the prop type only_ | 0 |
| `align` | `center` | _declared by the prop type only_ | 0 |

Rendered 2 time(s) in 2 other file(s).
