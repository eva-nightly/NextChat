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
| "app/components/artifacts::HTMLPreview" | HTMLPreview | `app/components/artifacts.tsx` |  |  | 1 | Renders a live preview of HTML content produced in a conversation. |
| "app/components/artifacts::ArtifactsShareButton" | ArtifactsShareButton | `app/components/artifacts.tsx` |  |  | 1 | Button that shares an artifact so it can be opened outside the current session. |
| "app/components/artifacts::Artifacts" | Artifacts | `app/components/artifacts.tsx` |  |  | 1 | Container view for displaying a shared or generated artifact. |
| "app/components/auth::AuthPage" | AuthPage | `app/components/auth.tsx` |  |  | 1 | Full-page screen where users enter credentials or access keys before using the app. |
| "app/components/auth::TopBanner" | TopBanner | `app/components/auth.tsx` |  |  | 0 | Dismissible banner shown at the top of the auth page for notices. |
| "app/components/button::IconButton" | IconButton | `app/components/button.tsx` |  |  | 113 | General-purpose button combining an icon with optional text, used across toolbars and modals. |
| "app/components/chat-list::ChatItem" | ChatItem | `app/components/chat-list.tsx` |  |  | 0 | Single row in the conversation list representing one chat session. |
| "app/components/chat-list::ChatList" | ChatList | `app/components/chat-list.tsx` |  |  | 1 | Sidebar list of chat sessions that supports selecting and reordering items. |
| "app/components/chat::MCPAction" | MCPAction | `app/components/chat.tsx` |  |  | 0 | Chat toolbar action related to MCP integration within a session. |
| "app/components/chat::SessionConfigModel" | SessionConfigModel | `app/components/chat.tsx` |  |  | 0 | Modal for editing the settings of the current chat session. |
| "app/components/chat::PromptToast" | PromptToast | `app/components/chat.tsx` |  |  | 0 | Small toast above the chat showing the session's context prompt status. |
| "app/components/chat::PromptHints" | PromptHints | `app/components/chat.tsx` |  |  | 0 | Dropdown of prompt suggestions shown while typing in the chat input. |
| "app/components/chat::ClearContextDivider" | ClearContextDivider | `app/components/chat.tsx` |  |  | 0 | Divider in the message stream marking where prior context was cleared. |
| "app/components/chat::ChatAction" | ChatAction | `app/components/chat.tsx` |  |  | 4 | Single expandable icon action in the chat input toolbar. |
| "app/components/chat::ChatActions" | ChatActions | `app/components/chat.tsx` |  |  | 0 | Toolbar of actions displayed above the chat input. |
| "app/components/chat::EditMessageModal" | EditMessageModal | `app/components/chat.tsx` |  |  | 0 | Modal for editing the messages and title of the current session. |
| "app/components/chat::DeleteImageButton" | DeleteImageButton | `app/components/chat.tsx` |  |  | 0 | Small button to remove an attached image from the chat input. |
| "app/components/chat::ShortcutKeyModal" | ShortcutKeyModal | `app/components/chat.tsx` |  |  | 0 | Modal listing available keyboard shortcuts. |
| "app/components/chat::Chat" | Chat | `app/components/chat.tsx` |  |  | 2 | Main conversation view with message history, input area and header. |
| "app/components/emoji::AvatarPicker" | AvatarPicker | `app/components/emoji.tsx` |  |  | 2 | Picker for choosing an emoji to use as an avatar. |
| "app/components/emoji::Avatar" | Avatar | `app/components/emoji.tsx` |  |  | 8 | Displays a user or model avatar. |
| "app/components/emoji::EmojiAvatar" | EmojiAvatar | `app/components/emoji.tsx` |  |  | 3 | Renders an emoji as an avatar image. |
| "app/components/error::ErrorBoundary" | ErrorBoundary | `app/components/error.tsx` |  |  | 0 | Catches rendering errors and shows a fallback with recovery options. |
| "app/components/exporter::ExportMessageModal" | ExportMessageModal | `app/components/exporter.tsx` |  |  | 1 | Modal wrapper that hosts the message export flow. |
| "app/components/exporter::Steps" | Steps | `app/components/exporter.tsx` |  |  | 0 | Step indicator for navigating the export flow. |
| "app/components/exporter::MessageExporter" | MessageExporter | `app/components/exporter.tsx` |  |  | 0 | Export flow for selecting messages and choosing an output format. |
| "app/components/exporter::RenderExport" | RenderExport | `app/components/exporter.tsx` |  |  | 0 | Renders selected messages into a form suitable for export. |
| "app/components/exporter::PreviewActions" | PreviewActions | `app/components/exporter.tsx` |  |  | 0 | Action bar for copying, downloading or sharing an export preview. |
| "app/components/exporter::ImagePreviewer" | ImagePreviewer | `app/components/exporter.tsx` |  |  | 0 | Previews the selected messages as an image for export. |
| "app/components/exporter::MarkdownPreviewer" | MarkdownPreviewer | `app/components/exporter.tsx` |  |  | 0 | Previews the selected messages as Markdown for export. |
| "app/components/exporter::JsonPreviewer" | JsonPreviewer | `app/components/exporter.tsx` |  |  | 0 | Previews the selected messages as JSON for export. |
| "app/components/home::Loading" | Loading | `app/components/home.tsx` |  |  | 1 | Loading indicator shown while screens or data are being prepared. |
| "app/components/home::WindowContent" | WindowContent | `app/components/home.tsx` |  |  | 1 | Wrapper for the main content area of the app window. |
| "app/components/home::Screen" | Screen | `app/components/home.tsx` |  |  | 0 | Top-level layout combining the sidebar with the routed main content. |
| "app/components/home::Home" | Home | `app/components/home.tsx` |  |  | 1 | Root application component that sets up routing and the overall shell. |
| "app/components/input-range::InputRange" | InputRange | `app/components/input-range.tsx` |  |  | 8 | Slider input for selecting a numeric value within a range. |
| "app/components/markdown::Mermaid" | Mermaid | `app/components/markdown.tsx` |  |  | 0 | Renders Mermaid diagram code blocks inside Markdown content. |
| "app/components/markdown::PreCode" | PreCode | `app/components/markdown.tsx` |  |  | 0 | Code block wrapper with copy support and related actions. |
| "app/components/markdown::CustomCode" | CustomCode | `app/components/markdown.tsx` |  |  | 0 | Code element with collapsible display for long content. |
| "app/components/markdown::Markdown" | Markdown | `app/components/markdown.tsx` |  |  | 4 | Renders message text as Markdown with code and math support. |
| "app/components/mask::MaskAvatar" | MaskAvatar | `app/components/mask.tsx` |  |  | 7 | Avatar display for a mask, as named in the mask feature file. |
| "app/components/mask::MaskConfig" | MaskConfig | `app/components/mask.tsx` |  |  | 1 | Configuration UI for a mask. |
| "app/components/mask::ContextPromptItem" | ContextPromptItem | `app/components/mask.tsx` |  |  | 0 | A single item within a mask's context prompts. |
| "app/components/mask::ContextPrompts" | ContextPrompts | `app/components/mask.tsx` |  |  | 1 | The collection of context prompts attached to a mask; contains @app/components/mask::ContextPromptItem. |
| "app/components/mask::MaskPage" | MaskPage | `app/components/mask.tsx` |  |  | 1 | Page-level view for browsing and managing masks. |
| "app/components/mcp-market::McpMarketPage" | McpMarketPage | `app/components/mcp-market.tsx` |  | active | 1 | Page-level view for an MCP market. |
| "app/components/message-selector::MessageSelector" | MessageSelector | `app/components/message-selector.tsx` |  | selection | 1 | UI for selecting messages. |
| "app/components/model-config::ModelConfigList" | ModelConfigList | `app/components/model-config.tsx` |  |  | 2 | List of model configuration settings. |
| "app/components/new-chat::MaskItem" | MaskItem | `app/components/new-chat.tsx` |  |  | 0 | A mask entry shown in the new-chat flow. |
| "app/components/new-chat::NewChat" | NewChat | `app/components/new-chat.tsx` |  |  | 1 | View for starting a new chat; presents @app/components/new-chat::MaskItem entries. |
| "app/components/plugin::PluginPage" | PluginPage | `app/components/plugin.tsx` |  |  | 1 | Page-level view for plugins. |
| "app/components/realtime-chat/realtime-chat::RealtimeChat" | RealtimeChat | `app/components/realtime-chat/realtime-chat.tsx` |  |  | 1 | Realtime chat interface. |
| "app/components/realtime-chat/realtime-config::RealtimeConfigList" | RealtimeConfigList | `app/components/realtime-chat/realtime-config.tsx` |  |  | 1 | List of configuration settings for realtime chat. |
| "app/components/sd/sd-panel::ControlParamItem" | ControlParamItem | `app/components/sd/sd-panel.tsx` |  | placeholder, required | 0 | A single control parameter within the sd panel. |
| "app/components/sd/sd-panel::ControlParam" | ControlParam | `app/components/sd/sd-panel.tsx` |  | placeholder, required | 0 | Group of control parameters for the sd panel; contains @app/components/sd/sd-panel::ControlParamItem. |
| "app/components/sd/sd-panel::SdPanel" | SdPanel | `app/components/sd/sd-panel.tsx` |  | placeholder, required | 1 | Control panel for the sd feature area. |
| "app/components/sd/sd-sidebar::SideBar" | SideBar | `app/components/sd/sd-sidebar.tsx` |  |  | 2 | Sidebar specific to the sd feature area; distinct from @app/components/sidebar::SideBar. |
| "app/components/sd/sd::Sd" | Sd | `app/components/sd/sd.tsx` |  |  | 2 | Top-level view for the sd feature area. |
| "app/components/search-chat::SearchChatPage" | SearchChatPage | `app/components/search-chat.tsx` |  |  | 0 | Page-level view for searching chats. |
| "app/components/settings::EditPromptModal" | EditPromptModal | `app/components/settings.tsx` |  |  | 0 | Modal for editing a prompt within settings. |
| "app/components/settings::UserPromptModal" | UserPromptModal | `app/components/settings.tsx` |  |  | 0 | Modal for managing user prompts within settings. |
| "app/components/settings::DangerItems" | DangerItems | `app/components/settings.tsx` |  |  | 0 | Settings section grouping destructive actions. |
| "app/components/settings::CheckButton" | CheckButton | `app/components/settings.tsx` |  |  | 0 | Button used in settings to run a check. |
| "app/components/settings::SyncConfigModal" | SyncConfigModal | `app/components/settings.tsx` |  |  | 0 | Modal for configuring sync in settings. |
| "app/components/settings::SyncItems" | SyncItems | `app/components/settings.tsx` |  |  | 0 | Settings section grouping sync-related items; opens @app/components/settings::SyncConfigModal. |
| "app/components/settings::Settings" | Settings | `app/components/settings.tsx` |  |  | 1 | Main settings page composing the settings sections and modals. |
| "app/components/sidebar::SideBarContainer" | SideBarContainer | `app/components/sidebar.tsx` |  |  | 1 | Outer container for the main sidebar. |
| "app/components/sidebar::SideBarHeader" | SideBarHeader | `app/components/sidebar.tsx` |  |  | 1 | Header region of the main sidebar. |
| "app/components/sidebar::SideBarBody" | SideBarBody | `app/components/sidebar.tsx` |  |  | 1 | Scrollable body region of the main sidebar. |
| "app/components/sidebar::SideBarTail" | SideBarTail | `app/components/sidebar.tsx` |  |  | 1 | Footer region of the main sidebar. |
| "app/components/sidebar::SideBar" | SideBar | `app/components/sidebar.tsx` |  |  | 2 | Main application sidebar assembled from @app/components/sidebar::SideBarContainer, @app/components/sidebar::SideBarHeader, @app/components/sidebar::SideBarBody and @app/components/sidebar::SideBarTail. |
| "app/components/tts-config::TTSConfigList" | TTSConfigList | `app/components/tts-config.tsx` |  |  | 1 | List of text-to-speech configuration settings. |
| "app/components/ui-lib::Popover" | Popover | `app/components/ui-lib.tsx` | align (2) |  | 2 | Shared popover primitive from the ui-lib. |
| "app/components/ui-lib::Card" | Card | `app/components/ui-lib.tsx` |  |  | 0 | Shared card surface primitive from the ui-lib. |
| "app/components/ui-lib::ListItem" | ListItem | `app/components/ui-lib.tsx` |  |  | 119 | Shared list row primitive, used inside @app/components/ui-lib::List. |
| "app/components/ui-lib::List" | List | `app/components/ui-lib.tsx` |  |  | 19 | Shared list container primitive from the ui-lib. |
| "app/components/ui-lib::Loading" | Loading | `app/components/ui-lib.tsx` |  |  | 11 | Shared loading indicator from the ui-lib. |
| "app/components/ui-lib::Modal" | Modal | `app/components/ui-lib.tsx` |  |  | 12 | Shared modal dialog primitive from the ui-lib; its padding is governed by t27. |
| "app/components/ui-lib::Toast" | Toast | `app/components/ui-lib.tsx` |  |  | 0 | Shared transient notification primitive from the ui-lib. |
| "app/components/ui-lib::Input" | Input | `app/components/ui-lib.tsx` |  |  | 2 | Shared text input primitive from the ui-lib. |
| "app/components/ui-lib::PasswordInput" | PasswordInput | `app/components/ui-lib.tsx` |  |  | 27 | Text input intended for entering secret or password-type values, part of the shared ui-lib. |
| "app/components/ui-lib::Select" | Select | `app/components/ui-lib.tsx` |  |  | 17 | Dropdown control for choosing one option from a list, part of the shared ui-lib. |
| "app/components/ui-lib::PromptInput" | PromptInput | `app/components/ui-lib.tsx` |  |  | 0 | Input for composing a prompt, i.e. the text the user submits in the chat-style interface. |
| "app/components/ui-lib::Selector" | Selector | `app/components/ui-lib.tsx` |  |  | 6 | Selection control in the shared ui-lib for picking from a set of items; distinct from the native-style Select. |
| "app/components/ui-lib::FullScreen" | FullScreen | `app/components/ui-lib.tsx` |  |  | 1 | Wrapper that presents its content in a full-screen mode. |
| "app/components/voice-print/voice-print::VoicePrint" | VoicePrint | `app/components/voice-print/voice-print.tsx` |  |  | 1 | Visual representation of a voice or audio signal, living in its own voice-print module. |
| "app/layout::RootLayout" | RootLayout | `app/layout.tsx` |  |  | 0 | Top-level layout that wraps every page of the application. |
| "app/page::App" | App | `app/page.tsx` |  |  | 0 | The main application page component rendered at the root route. |

### Variants, in full

#### Popover (`app/components/ui-lib.tsx`:30)

| axis | value | classes | call sites |
| --- | --- | --- | --- |
| `align` | `left` | _declared by the prop type only_ | 0 |
| `align` | `center` | _declared by the prop type only_ | 0 |

Rendered 2 time(s) in 2 other file(s).
