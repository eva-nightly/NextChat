# Identifiers in this code

Every row is a `@uxid` comment in this repository: above a declaration (`// @uxid <id>`, `# @uxid <id>` in
Python), or for an element inside its opening tag (`<button /* @uxid <id> */ ...>`). Search the code for an
id to find its place, wherever the file has moved. Ids are permanent: never edit or remove one, and copy
none: a new component gets its own on Eva's next scan.

## Components (88)

| identifier | file | description |
| --- | --- | --- |
| `app/components/artifacts::Artifacts` | app/components/artifacts.tsx | Function component. Hooks: useParams, useState, useRef, useEffect. Renders: div, a, IconButton, GithubIcon, ReloadButtonIcon, ArtifactsShareButton, Loading, HTMLPreview. |
| `app/components/artifacts::ArtifactsShareButton` | app/components/artifacts.tsx | Function component. Props: getCode, id, style, fileName. Hooks: useState, useMemo. Renders: div, a, IconButton, LoadingButtonIcon, ExportIcon, Modal, DownloadIcon, CopyIcon. |
| `app/components/artifacts::HTMLPreview` | app/components/artifacts.tsx | Wrapped component. Hooks: useRef, useState, useEffect, useImperativeHandle, useMemo. Renders: iframe. |
| `app/components/auth::AuthPage` | app/components/auth.tsx | Function component. Hooks: useNavigate, useAccessStore, useEffect. Renders: div, TopBanner, IconButton, LeftIcon, BotIcon, PasswordInput. |
| `app/components/auth::TopBanner` | app/components/auth.tsx | Function component. Hooks: useState, useMobileScreen, useEffect. Renders: div, span, a, Logo, Arrow, Delete. |
| `app/components/button::IconButton` | app/components/button.tsx | Function component. Renders: button, div. |
| `app/components/chat-list::ChatItem` | app/components/chat-list.tsx | Function component. Hooks: useRef, useEffect, useLocation. Renders: div, Draggable, MaskAvatar, DeleteIcon. |
| `app/components/chat-list::ChatList` | app/components/chat-list.tsx | Function component. Hooks: useChatStore, useNavigate, useMobileScreen. Renders: div, DragDropContext, Droppable, ChatItem. |
| `app/components/chat::Chat` | app/components/chat.tsx | Function component. Hooks: useChatStore. Renders: _Chat. |
| `app/components/chat::ChatAction` | app/components/chat.tsx | Function component. Hooks: useRef, useState. Renders: div. |
| `app/components/chat::ChatActions` | app/components/chat.tsx | Function component. Hooks: useAppConfig, useNavigate, useChatStore, usePluginStore, useAllModels, useMemo, +3 more. Renders: div, ChatAction, StopIcon, BottomIcon, SettingsIcon, LoadingButtonIcon, ImageIcon. |
| `app/components/chat::ClearContextDivider` | app/components/chat.tsx | Function component. Hooks: useChatStore. Renders: div. |
| `app/components/chat::DeleteImageButton` | app/components/chat.tsx | Function component. Renders: div, DeleteIcon. |
| `app/components/chat::EditMessageModal` | app/components/chat.tsx | Function component. Hooks: useChatStore, useState. Renders: div, input, Modal, IconButton, CancelIcon, ConfirmIcon, List, ListItem. |
| `app/components/chat::MCPAction` | app/components/chat.tsx | Arrow function component. Hooks: useNavigate, useAccessStore, useState, useEffect. Renders: ChatAction, McpToolIcon. |
| `app/components/chat::PromptHints` | app/components/chat.tsx | Function component. Hooks: useState, useRef, useEffect. Renders: div. |
| `app/components/chat::PromptToast` | app/components/chat.tsx | Function component. Hooks: useChatStore. Renders: div, span, BrainIcon, SessionConfigModel. |
| `app/components/chat::SessionConfigModel` | app/components/chat.tsx | Function component. Hooks: useChatStore, useMaskStore, useNavigate. Renders: div, Modal, IconButton, ResetIcon, CopyIcon, MaskConfig, ListItem. |
| `app/components/chat::ShortcutKeyModal` | app/components/chat.tsx | Function component. Renders: div, span, Modal, IconButton, ConfirmIcon. |
| `app/components/emoji::Avatar` | app/components/emoji.tsx | Function component. Renders: div, LlmIcon, EmojiAvatar. |
| `app/components/emoji::AvatarPicker` | app/components/emoji.tsx | Function component. Renders: EmojiPicker. |
| `app/components/emoji::EmojiAvatar` | app/components/emoji.tsx | Function component. Renders: Emoji. |
| `app/components/error::ErrorBoundary` | app/components/error.tsx | Class component. Renders: div, h2, pre, code, a, IconButton, GithubIcon, ResetIcon. |
| `app/components/exporter::ExportMessageModal` | app/components/exporter.tsx | Function component. Renders: div, Modal, MessageExporter. |
| `app/components/exporter::ImagePreviewer` | app/components/exporter.tsx | Function component. Hooks: useChatStore, useAppConfig, useRef, useMobileScreen. Renders: div, span, img, PreviewActions, NextImage, MaskAvatar, Avatar, Markdown. |
| `app/components/exporter::JsonPreviewer` | app/components/exporter.tsx | Function component. Renders: div, PreviewActions, Markdown. |
| `app/components/exporter::MarkdownPreviewer` | app/components/exporter.tsx | Function component. Renders: div, pre, PreviewActions. |
| `app/components/exporter::MessageExporter` | app/components/exporter.tsx | Function component. Hooks: useSteps, useState, useChatStore, useMessageSelector, useMemo. Renders: div, option, input, MarkdownPreviewer, JsonPreviewer, ImagePreviewer, Steps, List, +1 more. |
| `app/components/exporter::PreviewActions` | app/components/exporter.tsx | Function component. Hooks: useState, useAppConfig. Renders: input, div, IconButton, CopyIcon, DownloadIcon, LoadingIcon, ShareIcon, RenderExport. |
| `app/components/exporter::RenderExport` | app/components/exporter.tsx | Function component. Hooks: useRef, useEffect. Renders: div, Markdown. |
| `app/components/exporter::Steps` | app/components/exporter.tsx | Function component. Renders: div, span. |
| `app/components/home::Home` | app/components/home.tsx | Function component. Hooks: useSwitchTheme, useLoadData, useHtmlLang, useEffect, useHasHydrated. Renders: Loading, ErrorBoundary, Router, Screen. |
| `app/components/home::Loading` | app/components/home.tsx | Function component. Renders: div, BotIcon, LoadingIcon. |
| `app/components/home::Screen` | app/components/home.tsx | Function component. Hooks: useAppConfig, useLocation, useMobileScreen, useEffect. Renders: div, Routes, Route, Artifacts, AuthPage, Sd, SideBar. |
| `app/components/home::WindowContent` | app/components/home.tsx | Function component. Renders: div. |
| `app/components/input-range::InputRange` | app/components/input-range.tsx | Function component. Props: onChange, title, value, className, min, max, +2 more. Renders: div, input. |
| `app/components/markdown::CustomCode` | app/components/markdown.tsx | Function component. Hooks: useChatStore, useAppConfig, useRef, useState, useEffect. Renders: div, button, code. |
| `app/components/markdown::Markdown` | app/components/markdown.tsx | Function component. Hooks: useRef. Renders: div, LoadingIcon, MarkdownContent. |
| `app/components/markdown::Mermaid` | app/components/markdown.tsx | Function component. Hooks: useRef, useState, useEffect. Renders: div. |
| `app/components/markdown::PreCode` | app/components/markdown.tsx | Function component. Hooks: useRef, useState, useWindowSize, useChatStore, useDebouncedCallback, useAppConfig, +1 more. Renders: pre, span, Mermaid, FullScreen, ArtifactsShareButton, IconButton, ReloadButtonIcon, HTMLPreview. |
| `app/components/mask::ContextPromptItem` | app/components/mask.tsx | Function component. Hooks: useState. Renders: div, option, DragIcon, Select, Input, IconButton, DeleteIcon. |
| `app/components/mask::ContextPrompts` | app/components/mask.tsx | Function component. Renders: div, DragDropContext, Droppable, Draggable, ContextPromptItem, AddIcon, IconButton. |
| `app/components/mask::MaskAvatar` | app/components/mask.tsx | Function component. Renders: Avatar. |
| `app/components/mask::MaskConfig` | app/components/mask.tsx | Function component. Hooks: useState, useAppConfig. Renders: div, input, ContextPrompts, List, ListItem, Popover, AvatarPicker, MaskAvatar. |
| `app/components/mask::MaskPage` | app/components/mask.tsx | Function component. Hooks: useNavigate, useMaskStore, useChatStore, useState. Renders: div, input, option, ErrorBoundary, IconButton, DownloadIcon, UploadIcon, CloseIcon, +1 more. |
| `app/components/mcp-market::McpMarketPage` | app/components/mcp-market.tsx | Function component. Hooks: useNavigate, useAccessStore, useState, useEffect. Renders: div, input, span, a, ListItem, IconButton, DeleteIcon, AddIcon, +2 more. |
| `app/components/message-selector::MessageSelector` | app/components/message-selector.tsx | Function component. Hooks: useChatStore, useMemo, useAppConfig, useState, useShiftRange, useEffect. Renders: div, input, IconButton, Avatar, MaskAvatar. |
| `app/components/model-config::ModelConfigList` | app/components/model-config.tsx | Function component. Hooks: useAllModels. Renders: optgroup, option, input, ListItem, Select, InputRange. |
| `app/components/new-chat::MaskItem` | app/components/new-chat.tsx | Function component. Renders: div, MaskAvatar. |
| `app/components/new-chat::NewChat` | app/components/new-chat.tsx | Function component. Hooks: useChatStore, useMaskStore, useMaskGroup, useNavigate, useAppConfig, useRef, +3 more. Renders: div, IconButton, LeftIcon, EmojiAvatar, EyeIcon, LightningIcon, MaskItem. |
| `app/components/plugin::PluginPage` | app/components/plugin.tsx | Function component. Hooks: useNavigate, usePluginStore, useState, useDebouncedCallback. Renders: div, a, input, small, select, option, ErrorBoundary, IconButton, +4 more. |
| `app/components/realtime-chat/realtime-chat::RealtimeChat` | app/components/realtime-chat/realtime-chat.tsx | Function component. Props: onClose, onStartVoice, onPausedVoice. Hooks: useChatStore, useAppConfig, useState, useRef, useEffect. Renders: div, VoicePrint, IconButton, VoiceIcon, VoiceOffIcon, PowerIcon. |
| `app/components/realtime-chat/realtime-config::RealtimeConfigList` | app/components/realtime-chat/realtime-config.tsx | Function component. Renders: input, option, ListItem, Select, PasswordInput, InputRange. |
| `app/components/sd/sd-panel::ControlParam` | app/components/sd/sd-panel.tsx | Function component. Renders: textarea, option, input, div, ControlParamItem, Select. |
| `app/components/sd/sd-panel::ControlParamItem` | app/components/sd/sd-panel.tsx | Function component. Renders: div, span. |
| `app/components/sd/sd-panel::SdPanel` | app/components/sd/sd-panel.tsx | Function component. Hooks: useSdStore. Renders: div, ControlParamItem, IconButton, ControlParam. |
| `app/components/sd/sd-sidebar::SideBar` | app/components/sd/sd-sidebar.tsx | Function component. Hooks: useHotKey, useMobileScreen, useDragSideBar, useNavigate, useSdStore. Renders: div, a, SideBarContainer, IconButton, ReturnIcon, SDIcon, HistoryIcon, SideBarHeader. |
| `app/components/sd/sd::Sd` | app/components/sd/sd.tsx | Function component. Hooks: useMobileScreen, useNavigate, useLocation, useMemo, useAppConfig, useRef, +3 more. Renders: div, img, p, span, strong, SideBar, WindowContent, IconButton, +3 more. |
| `app/components/search-chat::SearchChatPage` | app/components/search-chat.tsx | Function component. Hooks: useNavigate, useChatStore, useState, useRef, useCallback, useEffect. Renders: div, input, ErrorBoundary, IconButton, CloseIcon, EyeIcon. |
| `app/components/settings::CheckButton` | app/components/settings.tsx | Function component. Hooks: useSyncStore, useMemo, useState. Renders: IconButton, ConnectionIcon, LoadingIcon, CloudSuccessIcon, CloudFailIcon. |
| `app/components/settings::DangerItems` | app/components/settings.tsx | Function component. Hooks: useChatStore, useAppConfig. Renders: List, ListItem, IconButton. |
| `app/components/settings::EditPromptModal` | app/components/settings.tsx | Function component. Hooks: usePromptStore. Renders: div, input, Modal, IconButton, Input. |
| `app/components/settings::Settings` | app/components/settings.tsx | Function component. Hooks: useNavigate, useState, useAppConfig, useUpdateStore, useAccessStore, useMemo, +2 more. Renders: input, option, div, ListItem, PasswordInput, IconButton, FireIcon, Select, +1 more. |
| `app/components/settings::SyncConfigModal` | app/components/settings.tsx | Function component. Hooks: useSyncStore. Renders: div, select, option, input, Modal, CheckButton, IconButton, ConfirmIcon, +2 more. |
| `app/components/settings::SyncItems` | app/components/settings.tsx | Function component. Hooks: useSyncStore, useChatStore, usePromptStore, useMaskStore, useMemo, useState. Renders: div, List, ListItem, IconButton, ConfigIcon, ResetIcon, UploadIcon. |
| `app/components/settings::UserPromptModal` | app/components/settings.tsx | Function component. Hooks: usePromptStore, useState, useEffect. Renders: div, input, Modal, IconButton, AddIcon, ClearIcon, EditIcon, EyeIcon. |
| `app/components/sidebar::SideBar` | app/components/sidebar.tsx | Function component. Hooks: useHotKey, useDragSideBar, useState, useNavigate, useAppConfig, useChatStore, +1 more. Renders: div, a, SideBarContainer, SideBarHeader, NextChatIcon, IconButton, MaskIcon, McpIcon. |
| `app/components/sidebar::SideBarBody` | app/components/sidebar.tsx | Function component. Renders: div. |
| `app/components/sidebar::SideBarContainer` | app/components/sidebar.tsx | Function component. Hooks: useMobileScreen, useMemo. Renders: div, DragIcon. |
| `app/components/sidebar::SideBarHeader` | app/components/sidebar.tsx | Function component. Renders: div, Fragment. |
| `app/components/sidebar::SideBarTail` | app/components/sidebar.tsx | Function component. Renders: div. |
| `app/components/tts-config::TTSConfigList` | app/components/tts-config.tsx | Function component. Renders: input, option, ListItem, Select, InputRange. |
| `app/components/ui-lib::Card` | app/components/ui-lib.tsx | Function component. Renders: div. |
| `app/components/ui-lib::FullScreen` | app/components/ui-lib.tsx | Function component. Hooks: useRef, useState, useCallback, useEffect. Renders: div, IconButton, MinIcon, MaxIcon. |
| `app/components/ui-lib::Input` | app/components/ui-lib.tsx | Function component. Props: props: InputProps. Renders: textarea. |
| `app/components/ui-lib::List` | app/components/ui-lib.tsx | Function component. Renders: div. |
| `app/components/ui-lib::ListItem` | app/components/ui-lib.tsx | Function component. Renders: div. |
| `app/components/ui-lib::Loading` | app/components/ui-lib.tsx | Function component. Renders: div, LoadingIcon. |
| `app/components/ui-lib::Modal` | app/components/ui-lib.tsx | Function component. Props: props: ModalProps. Hooks: useEffect, useState. Renders: div, MinIcon, MaxIcon, CloseIcon. |
| `app/components/ui-lib::PasswordInput` | app/components/ui-lib.tsx | Function component. Hooks: useState. Renders: div, input, IconButton, EyeIcon, EyeOffIcon. |
| `app/components/ui-lib::Popover` | app/components/ui-lib.tsx | Function component. Renders: div. |
| `app/components/ui-lib::PromptInput` | app/components/ui-lib.tsx | Function component. Hooks: useState. Renders: textarea. |
| `app/components/ui-lib::Select` | app/components/ui-lib.tsx | Function component. Props: props: object. Renders: div, select, DownIcon. |
| `app/components/ui-lib::Selector` | app/components/ui-lib.tsx | Function component. Hooks: useState. Renders: div, List, ListItem, Avatar. |
| `app/components/ui-lib::Toast` | app/components/ui-lib.tsx | Function component. Props: props: ToastProps. Renders: div, span, button. |
| `app/components/voice-print/voice-print::VoicePrint` | app/components/voice-print/voice-print.tsx | Function component. Props: frequencies, isActive. Hooks: useRef, useCallback, useEffect. Renders: div, canvas. |
| `app/layout::RootLayout` | app/layout.tsx | Function component. Props: children. Renders: html, head, meta, link, script, body, SpeedInsights, GoogleTagManager, +1 more. |
| `app/page::App` | app/page.tsx | Function component. Renders: Home, Analytics. |

## Interactive elements (buttons, inputs, links), each inside a component (387)

| identifier | file | in | description |
| --- | --- | --- | --- |
| `app/components/artifacts::Artifacts.htmlpreview` | app/components/artifacts.tsx | `app/components/artifacts::Artifacts` | <HTMLPreview> component. Handlers: onLoad. |
| `app/components/artifacts::Artifacts.iconbutton` | app/components/artifacts.tsx | `app/components/artifacts::Artifacts` | <IconButton> component. Handlers: onClick. |
| `app/components/artifacts::Artifacts.link` | app/components/artifacts.tsx | `app/components/artifacts::Artifacts` | Link. |
| `app/components/artifacts::ArtifactsShareButton.iconbutton` | app/components/artifacts.tsx | `app/components/artifacts::ArtifactsShareButton` | <IconButton> component. Handlers: onClick. |
| `app/components/artifacts::ArtifactsShareButton.iconbutton-2` | app/components/artifacts.tsx | `app/components/artifacts::ArtifactsShareButton` | <IconButton> component. Handlers: onClick. |
| `app/components/artifacts::ArtifactsShareButton.iconbutton-3` | app/components/artifacts.tsx | `app/components/artifacts::ArtifactsShareButton` | <IconButton> component. Handlers: onClick. |
| `app/components/artifacts::ArtifactsShareButton.link` | app/components/artifacts.tsx | `app/components/artifacts::ArtifactsShareButton` | Link. |
| `app/components/artifacts::ArtifactsShareButton.modal` | app/components/artifacts.tsx | `app/components/artifacts::ArtifactsShareButton` | <Modal> component. Handlers: onClose. |
| `app/components/artifacts::HTMLPreview.iframe` | app/components/artifacts.tsx | `app/components/artifacts::HTMLPreview` | <iframe> element. Handlers: onLoad. |
| `app/components/auth::AuthPage.iconbutton` | app/components/auth.tsx | `app/components/auth::AuthPage` | <IconButton> component. Handlers: onClick. |
| `app/components/auth::AuthPage.iconbutton-2` | app/components/auth.tsx | `app/components/auth::AuthPage` | <IconButton> component. type=primary. Handlers: onClick. |
| `app/components/auth::AuthPage.iconbutton-3` | app/components/auth.tsx | `app/components/auth::AuthPage` | <IconButton> component. Handlers: onClick. |
| `app/components/auth::AuthPage.passwordinput` | app/components/auth.tsx | `app/components/auth::AuthPage` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/auth::AuthPage.passwordinput-2` | app/components/auth.tsx | `app/components/auth::AuthPage` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/auth::AuthPage.passwordinput-3` | app/components/auth.tsx | `app/components/auth::AuthPage` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/auth::TopBanner.delete` | app/components/auth.tsx | `app/components/auth::TopBanner` | <Delete> component. Handlers: onClick. |
| `app/components/auth::TopBanner.div` | app/components/auth.tsx | `app/components/auth::TopBanner` | <div> element. Handlers: onMouseEnter, onMouseLeave. |
| `app/components/auth::TopBanner.link` | app/components/auth.tsx | `app/components/auth::TopBanner` | Link. Handlers: onClick. |
| `app/components/button::IconButton.button` | app/components/button.tsx | `app/components/button::IconButton` | Button. can be disabled. Handlers: onClick. |
| `app/components/chat-list::ChatItem.div` | app/components/chat-list.tsx | `app/components/chat-list::ChatItem` | <div> element. Handlers: onClick. |
| `app/components/chat-list::ChatItem.div-2` | app/components/chat-list.tsx | `app/components/chat-list::ChatItem` | <div> element. Handlers: onClickCapture. |
| `app/components/chat-list::ChatList.chatitem` | app/components/chat-list.tsx | `app/components/chat-list::ChatList` | <ChatItem> component. Handlers: onClick, onDelete. |
| `app/components/chat-list::ChatList.dragdropcontext` | app/components/chat-list.tsx | `app/components/chat-list::ChatList` | <DragDropContext> component. Handlers: onDragEnd. |
| `app/components/chat::_Chat.chataction` | app/components/chat.tsx |  | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::_Chat.chataction-2` | app/components/chat.tsx |  | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::_Chat.chataction-3` | app/components/chat.tsx |  | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::_Chat.chataction-4` | app/components/chat.tsx |  | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::_Chat.chataction-5` | app/components/chat.tsx |  | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::_Chat.chataction-6` | app/components/chat.tsx |  | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::_Chat.div` | app/components/chat.tsx |  | <div> element. Handlers: onClickCapture. |
| `app/components/chat::_Chat.div-2` | app/components/chat.tsx |  | <div> element. Handlers: onScroll, onMouseDown, onTouchStart. |
| `app/components/chat::_Chat.editmessagemodal` | app/components/chat.tsx |  | <EditMessageModal> component. Handlers: onClose. |
| `app/components/chat::_Chat.exportmessagemodal` | app/components/chat.tsx |  | <ExportMessageModal> component. Handlers: onClose. |
| `app/components/chat::_Chat.iconbutton` | app/components/chat.tsx |  | <IconButton> component. Handlers: onClick. |
| `app/components/chat::_Chat.iconbutton-2` | app/components/chat.tsx |  | <IconButton> component. Handlers: onClick. |
| `app/components/chat::_Chat.iconbutton-3` | app/components/chat.tsx |  | <IconButton> component. Handlers: onClick. |
| `app/components/chat::_Chat.iconbutton-4` | app/components/chat.tsx |  | <IconButton> component. Handlers: onClick. |
| `app/components/chat::_Chat.iconbutton-5` | app/components/chat.tsx |  | <IconButton> component. Handlers: onClick. |
| `app/components/chat::_Chat.iconbutton-6` | app/components/chat.tsx |  | <IconButton> component. Handlers: onClick. |
| `app/components/chat::_Chat.iconbutton-7` | app/components/chat.tsx |  | <IconButton> component. type=primary. Handlers: onClick. |
| `app/components/chat::_Chat.label` | app/components/chat.tsx |  | Field label. |
| `app/components/chat::_Chat.markdown` | app/components/chat.tsx |  | <Markdown> component. Handlers: onDoubleClickCapture. |
| `app/components/chat::_Chat.prompthints` | app/components/chat.tsx |  | <PromptHints> component. Handlers: onPromptSelect. |
| `app/components/chat::_Chat.realtimechat` | app/components/chat.tsx |  | <RealtimeChat> component. Handlers: onClose, onStartVoice. |
| `app/components/chat::_Chat.shortcutkeymodal` | app/components/chat.tsx |  | <ShortcutKeyModal> component. Handlers: onClose. |
| `app/components/chat::_Chat.textarea` | app/components/chat.tsx |  | Multi-line text field. Handlers: onInput, onKeyDown, onFocus, onClick, onPaste. |
| `app/components/chat::ChatAction.div` | app/components/chat.tsx | `app/components/chat::ChatAction` | <div> element. Handlers: onClick, onMouseEnter, onTouchStart. |
| `app/components/chat::ChatActions.chataction` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.chataction-10` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.chataction-11` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.chataction-12` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.chataction-13` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.chataction-14` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.chataction-15` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.chataction-2` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.chataction-3` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.chataction-4` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.chataction-5` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.chataction-6` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.chataction-7` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.chataction-8` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.chataction-9` | app/components/chat.tsx | `app/components/chat::ChatActions` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::ChatActions.selector` | app/components/chat.tsx | `app/components/chat::ChatActions` | <Selector> component. Handlers: onClose, onSelection. |
| `app/components/chat::ChatActions.selector-2` | app/components/chat.tsx | `app/components/chat::ChatActions` | <Selector> component. Handlers: onClose, onSelection. |
| `app/components/chat::ChatActions.selector-3` | app/components/chat.tsx | `app/components/chat::ChatActions` | <Selector> component. Handlers: onClose, onSelection. |
| `app/components/chat::ChatActions.selector-4` | app/components/chat.tsx | `app/components/chat::ChatActions` | <Selector> component. Handlers: onClose, onSelection. |
| `app/components/chat::ChatActions.selector-5` | app/components/chat.tsx | `app/components/chat::ChatActions` | <Selector> component. Handlers: onClose, onSelection. |
| `app/components/chat::ClearContextDivider.div` | app/components/chat.tsx | `app/components/chat::ClearContextDivider` | <div> element. Handlers: onClick. |
| `app/components/chat::DeleteImageButton.div` | app/components/chat.tsx | `app/components/chat::DeleteImageButton` | <div> element. Handlers: onClick. |
| `app/components/chat::EditMessageModal.iconbutton` | app/components/chat.tsx | `app/components/chat::EditMessageModal` | <IconButton> component. Handlers: onClick. |
| `app/components/chat::EditMessageModal.iconbutton-2` | app/components/chat.tsx | `app/components/chat::EditMessageModal` | <IconButton> component. type=primary. Handlers: onClick. |
| `app/components/chat::EditMessageModal.input` | app/components/chat.tsx | `app/components/chat::EditMessageModal` | Text input. Handlers: onInput. |
| `app/components/chat::EditMessageModal.modal` | app/components/chat.tsx | `app/components/chat::EditMessageModal` | <Modal> component. Handlers: onClose. |
| `app/components/chat::MCPAction.chataction` | app/components/chat.tsx | `app/components/chat::MCPAction` | <ChatAction> component. Handlers: onClick. |
| `app/components/chat::PromptHints.div` | app/components/chat.tsx | `app/components/chat::PromptHints` | <div> element. Handlers: onClick, onMouseEnter. |
| `app/components/chat::PromptToast.div` | app/components/chat.tsx | `app/components/chat::PromptToast` | <div> element. Handlers: onClick. |
| `app/components/chat::PromptToast.sessionconfigmodel` | app/components/chat.tsx | `app/components/chat::PromptToast` | <SessionConfigModel> component. Handlers: onClose. |
| `app/components/chat::SessionConfigModel.iconbutton` | app/components/chat.tsx | `app/components/chat::SessionConfigModel` | <IconButton> component. Handlers: onClick. |
| `app/components/chat::SessionConfigModel.iconbutton-2` | app/components/chat.tsx | `app/components/chat::SessionConfigModel` | <IconButton> component. Handlers: onClick. |
| `app/components/chat::SessionConfigModel.modal` | app/components/chat.tsx | `app/components/chat::SessionConfigModel` | <Modal> component. Handlers: onClose. |
| `app/components/chat::ShortcutKeyModal.iconbutton` | app/components/chat.tsx | `app/components/chat::ShortcutKeyModal` | <IconButton> component. type=primary. Handlers: onClick. |
| `app/components/chat::ShortcutKeyModal.modal` | app/components/chat.tsx | `app/components/chat::ShortcutKeyModal` | <Modal> component. Handlers: onClose. |
| `app/components/emoji::AvatarPicker.emojipicker` | app/components/emoji.tsx | `app/components/emoji::AvatarPicker` | <EmojiPicker> component. Handlers: onEmojiClick. |
| `app/components/error::ErrorBoundary.iconbutton` | app/components/error.tsx | `app/components/error::ErrorBoundary` | <IconButton> component. Handlers: onClick. |
| `app/components/error::ErrorBoundary.link` | app/components/error.tsx | `app/components/error::ErrorBoundary` | Link. |
| `app/components/exporter::ExportMessageModal.modal` | app/components/exporter.tsx | `app/components/exporter::ExportMessageModal` | <Modal> component. Handlers: onClose. |
| `app/components/exporter::JsonPreviewer.div` | app/components/exporter.tsx | `app/components/exporter::JsonPreviewer` | <div> element. Handlers: onClick. |
| `app/components/exporter::MessageExporter.checkbox` | app/components/exporter.tsx | `app/components/exporter::MessageExporter` | Checkbox. Handlers: onChange. |
| `app/components/exporter::MessageExporter.option` | app/components/exporter.tsx | `app/components/exporter::MessageExporter` | Select option. |
| `app/components/exporter::MessageExporter.select` | app/components/exporter.tsx | `app/components/exporter::MessageExporter` | <Select> component. Handlers: onChange. |
| `app/components/exporter::MessageExporter.steps` | app/components/exporter.tsx | `app/components/exporter::MessageExporter` | <Steps> component. Handlers: onStepChange. |
| `app/components/exporter::PreviewActions.iconbutton` | app/components/exporter.tsx | `app/components/exporter::PreviewActions` | <IconButton> component. Handlers: onClick. |
| `app/components/exporter::PreviewActions.iconbutton-2` | app/components/exporter.tsx | `app/components/exporter::PreviewActions` | <IconButton> component. Handlers: onClick. |
| `app/components/exporter::PreviewActions.iconbutton-3` | app/components/exporter.tsx | `app/components/exporter::PreviewActions` | <IconButton> component. Handlers: onClick. |
| `app/components/exporter::PreviewActions.iconbutton-4` | app/components/exporter.tsx | `app/components/exporter::PreviewActions` | <IconButton> component. Handlers: onClick. |
| `app/components/exporter::PreviewActions.input` | app/components/exporter.tsx | `app/components/exporter::PreviewActions` | Text input. Handlers: onClick. |
| `app/components/exporter::PreviewActions.renderexport` | app/components/exporter.tsx | `app/components/exporter::PreviewActions` | <RenderExport> component. Handlers: onRender. |
| `app/components/exporter::Steps.div` | app/components/exporter.tsx | `app/components/exporter::Steps` | <div> element. Handlers: onClick. |
| `app/components/input-range::InputRange.range` | app/components/input-range.tsx | `app/components/input-range::InputRange` | Slider. Handlers: onChange. |
| `app/components/markdown::_MarkDownContent.link` | app/components/markdown.tsx |  | Link. |
| `app/components/markdown::CustomCode.button` | app/components/markdown.tsx | `app/components/markdown::CustomCode` | Button. Handlers: onClick. |
| `app/components/markdown::Markdown.div` | app/components/markdown.tsx | `app/components/markdown::Markdown` | <div> element. Handlers: onContextMenu, onDoubleClickCapture. |
| `app/components/markdown::Mermaid.div` | app/components/markdown.tsx | `app/components/markdown::Mermaid` | <div> element. Handlers: onClick. |
| `app/components/markdown::PreCode.iconbutton` | app/components/markdown.tsx | `app/components/markdown::PreCode` | <IconButton> component. Handlers: onClick. |
| `app/components/markdown::PreCode.span` | app/components/markdown.tsx | `app/components/markdown::PreCode` | <span> element. Handlers: onClick. |
| `app/components/mask::ContextPromptItem.iconbutton` | app/components/mask.tsx | `app/components/mask::ContextPromptItem` | <IconButton> component. Handlers: onClick. |
| `app/components/mask::ContextPromptItem.input` | app/components/mask.tsx | `app/components/mask::ContextPromptItem` | <Input> component. type=text. Handlers: onFocus, onBlur, onInput. |
| `app/components/mask::ContextPromptItem.option` | app/components/mask.tsx | `app/components/mask::ContextPromptItem` | Select option. |
| `app/components/mask::ContextPromptItem.select` | app/components/mask.tsx | `app/components/mask::ContextPromptItem` | <Select> component. Handlers: onChange. |
| `app/components/mask::ContextPrompts.div` | app/components/mask.tsx | `app/components/mask::ContextPrompts` | <div> element. Handlers: onClick. |
| `app/components/mask::ContextPrompts.dragdropcontext` | app/components/mask.tsx | `app/components/mask::ContextPrompts` | <DragDropContext> component. Handlers: onDragEnd. |
| `app/components/mask::ContextPrompts.iconbutton` | app/components/mask.tsx | `app/components/mask::ContextPrompts` | <IconButton> component. Handlers: onClick. |
| `app/components/mask::MaskConfig.avatarpicker` | app/components/mask.tsx | `app/components/mask::MaskConfig` | <AvatarPicker> component. Handlers: onEmojiClick. |
| `app/components/mask::MaskConfig.checkbox` | app/components/mask.tsx | `app/components/mask::MaskConfig` | Checkbox. Handlers: onChange. |
| `app/components/mask::MaskConfig.checkbox-2` | app/components/mask.tsx | `app/components/mask::MaskConfig` | Checkbox. Handlers: onChange. |
| `app/components/mask::MaskConfig.checkbox-3` | app/components/mask.tsx | `app/components/mask::MaskConfig` | Checkbox. Handlers: onChange. |
| `app/components/mask::MaskConfig.checkbox-4` | app/components/mask.tsx | `app/components/mask::MaskConfig` | Checkbox. Handlers: onChange. |
| `app/components/mask::MaskConfig.div` | app/components/mask.tsx | `app/components/mask::MaskConfig` | <div> element. Handlers: onClick. |
| `app/components/mask::MaskConfig.iconbutton` | app/components/mask.tsx | `app/components/mask::MaskConfig` | <IconButton> component. Handlers: onClick. |
| `app/components/mask::MaskConfig.input` | app/components/mask.tsx | `app/components/mask::MaskConfig` | Text input. Handlers: onInput. |
| `app/components/mask::MaskConfig.popover` | app/components/mask.tsx | `app/components/mask::MaskConfig` | <Popover> component. Handlers: onClose. |
| `app/components/mask::MaskPage.iconbutton` | app/components/mask.tsx | `app/components/mask::MaskPage` | <IconButton> component. Handlers: onClick. |
| `app/components/mask::MaskPage.iconbutton-10` | app/components/mask.tsx | `app/components/mask::MaskPage` | <IconButton> component. Handlers: onClick. |
| `app/components/mask::MaskPage.iconbutton-2` | app/components/mask.tsx | `app/components/mask::MaskPage` | <IconButton> component. Handlers: onClick. |
| `app/components/mask::MaskPage.iconbutton-3` | app/components/mask.tsx | `app/components/mask::MaskPage` | <IconButton> component. Handlers: onClick. |
| `app/components/mask::MaskPage.iconbutton-4` | app/components/mask.tsx | `app/components/mask::MaskPage` | <IconButton> component. Handlers: onClick. |
| `app/components/mask::MaskPage.iconbutton-5` | app/components/mask.tsx | `app/components/mask::MaskPage` | <IconButton> component. Handlers: onClick. |
| `app/components/mask::MaskPage.iconbutton-6` | app/components/mask.tsx | `app/components/mask::MaskPage` | <IconButton> component. Handlers: onClick. |
| `app/components/mask::MaskPage.iconbutton-7` | app/components/mask.tsx | `app/components/mask::MaskPage` | <IconButton> component. Handlers: onClick. |
| `app/components/mask::MaskPage.iconbutton-8` | app/components/mask.tsx | `app/components/mask::MaskPage` | <IconButton> component. Handlers: onClick. |
| `app/components/mask::MaskPage.iconbutton-9` | app/components/mask.tsx | `app/components/mask::MaskPage` | <IconButton> component. Handlers: onClick. |
| `app/components/mask::MaskPage.input` | app/components/mask.tsx | `app/components/mask::MaskPage` | Text input. Handlers: onInput. |
| `app/components/mask::MaskPage.modal` | app/components/mask.tsx | `app/components/mask::MaskPage` | <Modal> component. Handlers: onClose. |
| `app/components/mask::MaskPage.option` | app/components/mask.tsx | `app/components/mask::MaskPage` | Select option. |
| `app/components/mask::MaskPage.option-2` | app/components/mask.tsx | `app/components/mask::MaskPage` | Select option. |
| `app/components/mask::MaskPage.select` | app/components/mask.tsx | `app/components/mask::MaskPage` | <Select> component. Handlers: onChange. |
| `app/components/mcp-market::McpMarketPage.iconbutton` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | <IconButton> component. Handlers: onClick. |
| `app/components/mcp-market::McpMarketPage.iconbutton-10` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | <IconButton> component. can be disabled. Handlers: onClick. |
| `app/components/mcp-market::McpMarketPage.iconbutton-11` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | <IconButton> component. type=primary, can be disabled. Handlers: onClick. |
| `app/components/mcp-market::McpMarketPage.iconbutton-12` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | <IconButton> component. Handlers: onClick. |
| `app/components/mcp-market::McpMarketPage.iconbutton-2` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | <IconButton> component. Handlers: onClick. |
| `app/components/mcp-market::McpMarketPage.iconbutton-3` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | <IconButton> component. can be disabled. Handlers: onClick. |
| `app/components/mcp-market::McpMarketPage.iconbutton-4` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | <IconButton> component. can be disabled. Handlers: onClick. |
| `app/components/mcp-market::McpMarketPage.iconbutton-5` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | <IconButton> component. can be disabled. Handlers: onClick. |
| `app/components/mcp-market::McpMarketPage.iconbutton-6` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | <IconButton> component. can be disabled. Handlers: onClick. |
| `app/components/mcp-market::McpMarketPage.iconbutton-7` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | <IconButton> component. can be disabled. Handlers: onClick. |
| `app/components/mcp-market::McpMarketPage.iconbutton-8` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | <IconButton> component. can be disabled. Handlers: onClick. |
| `app/components/mcp-market::McpMarketPage.iconbutton-9` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | <IconButton> component. can be disabled. Handlers: onClick. |
| `app/components/mcp-market::McpMarketPage.input` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | Text input. Handlers: onChange. |
| `app/components/mcp-market::McpMarketPage.input-2` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | Text input. Handlers: onChange. |
| `app/components/mcp-market::McpMarketPage.input-3` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | Text input. placeholder "Search MCP Server". Handlers: onInput. |
| `app/components/mcp-market::McpMarketPage.link` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | Link. labelled "Open repository". |
| `app/components/mcp-market::McpMarketPage.modal` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | <Modal> component. Handlers: onClose. |
| `app/components/mcp-market::McpMarketPage.modal-2` | app/components/mcp-market.tsx | `app/components/mcp-market::McpMarketPage` | <Modal> component. Handlers: onClose. |
| `app/components/message-selector::MessageSelector.checkbox` | app/components/message-selector.tsx | `app/components/message-selector::MessageSelector` | Checkbox. |
| `app/components/message-selector::MessageSelector.div` | app/components/message-selector.tsx | `app/components/message-selector::MessageSelector` | <div> element. Handlers: onClick. |
| `app/components/message-selector::MessageSelector.iconbutton` | app/components/message-selector.tsx | `app/components/message-selector::MessageSelector` | <IconButton> component. Handlers: onClick. |
| `app/components/message-selector::MessageSelector.iconbutton-2` | app/components/message-selector.tsx | `app/components/message-selector::MessageSelector` | <IconButton> component. Handlers: onClick. |
| `app/components/message-selector::MessageSelector.iconbutton-3` | app/components/message-selector.tsx | `app/components/message-selector::MessageSelector` | <IconButton> component. Handlers: onClick. |
| `app/components/message-selector::MessageSelector.input` | app/components/message-selector.tsx | `app/components/message-selector::MessageSelector` | Text input. Handlers: onInput. |
| `app/components/model-config::ModelConfigList.checkbox` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | Checkbox. Handlers: onChange. |
| `app/components/model-config::ModelConfigList.checkbox-2` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | Checkbox. Handlers: onChange. |
| `app/components/model-config::ModelConfigList.input` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | Text input. Handlers: onChange. |
| `app/components/model-config::ModelConfigList.inputrange` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | <InputRange> component. Handlers: onChange. |
| `app/components/model-config::ModelConfigList.inputrange-2` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | <InputRange> component. Handlers: onChange. |
| `app/components/model-config::ModelConfigList.inputrange-3` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | <InputRange> component. Handlers: onChange. |
| `app/components/model-config::ModelConfigList.inputrange-4` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | <InputRange> component. Handlers: onChange. |
| `app/components/model-config::ModelConfigList.inputrange-5` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | <InputRange> component. Handlers: onChange. |
| `app/components/model-config::ModelConfigList.number` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | Number input. Handlers: onChange. |
| `app/components/model-config::ModelConfigList.number-2` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | Number input. Handlers: onChange. |
| `app/components/model-config::ModelConfigList.optgroup` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | Option group. |
| `app/components/model-config::ModelConfigList.option` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | Select option. |
| `app/components/model-config::ModelConfigList.option-2` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | Select option. |
| `app/components/model-config::ModelConfigList.select` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | <Select> component. Handlers: onChange. |
| `app/components/model-config::ModelConfigList.select-2` | app/components/model-config.tsx | `app/components/model-config::ModelConfigList` | <Select> component. Handlers: onChange. |
| `app/components/new-chat::MaskItem.div` | app/components/new-chat.tsx | `app/components/new-chat::MaskItem` | <div> element. Handlers: onClick. |
| `app/components/new-chat::NewChat.iconbutton` | app/components/new-chat.tsx | `app/components/new-chat::NewChat` | <IconButton> component. Handlers: onClick. |
| `app/components/new-chat::NewChat.iconbutton-2` | app/components/new-chat.tsx | `app/components/new-chat::NewChat` | <IconButton> component. Handlers: onClick. |
| `app/components/new-chat::NewChat.iconbutton-3` | app/components/new-chat.tsx | `app/components/new-chat::NewChat` | <IconButton> component. Handlers: onClick. |
| `app/components/new-chat::NewChat.iconbutton-4` | app/components/new-chat.tsx | `app/components/new-chat::NewChat` | <IconButton> component. type=primary. Handlers: onClick. |
| `app/components/new-chat::NewChat.maskitem` | app/components/new-chat.tsx | `app/components/new-chat::NewChat` | <MaskItem> component. Handlers: onClick. |
| `app/components/plugin::PluginPage.code` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | <code> element. Handlers: onBlur. |
| `app/components/plugin::PluginPage.iconbutton` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | <IconButton> component. Handlers: onClick. |
| `app/components/plugin::PluginPage.iconbutton-2` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | <IconButton> component. Handlers: onClick. |
| `app/components/plugin::PluginPage.iconbutton-3` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | <IconButton> component. Handlers: onClick. |
| `app/components/plugin::PluginPage.iconbutton-4` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | <IconButton> component. Handlers: onClick. |
| `app/components/plugin::PluginPage.iconbutton-5` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | <IconButton> component. Handlers: onClick. |
| `app/components/plugin::PluginPage.iconbutton-6` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | <IconButton> component. Handlers: onClick. |
| `app/components/plugin::PluginPage.input` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | Text input. Handlers: onInput. |
| `app/components/plugin::PluginPage.input-2` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | Text input. Handlers: onChange. |
| `app/components/plugin::PluginPage.input-3` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | Text input. Handlers: onInput. |
| `app/components/plugin::PluginPage.link` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | Link. |
| `app/components/plugin::PluginPage.link-2` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | Link. |
| `app/components/plugin::PluginPage.modal` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | <Modal> component. Handlers: onClose. |
| `app/components/plugin::PluginPage.option` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | Select option. |
| `app/components/plugin::PluginPage.option-2` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | Select option. |
| `app/components/plugin::PluginPage.option-3` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | Select option. |
| `app/components/plugin::PluginPage.option-4` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | Select option. |
| `app/components/plugin::PluginPage.option-5` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | Select option. |
| `app/components/plugin::PluginPage.option-6` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | Select option. |
| `app/components/plugin::PluginPage.option-7` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | Select option. |
| `app/components/plugin::PluginPage.passwordinput` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/plugin::PluginPage.select` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | Dropdown select. Handlers: onChange. |
| `app/components/plugin::PluginPage.select-2` | app/components/plugin.tsx | `app/components/plugin::PluginPage` | Dropdown select. Handlers: onChange. |
| `app/components/realtime-chat/realtime-chat::RealtimeChat.iconbutton` | app/components/realtime-chat/realtime-chat.tsx | `app/components/realtime-chat/realtime-chat::RealtimeChat` | <IconButton> component. can be disabled. Handlers: onClick. |
| `app/components/realtime-chat/realtime-chat::RealtimeChat.iconbutton-2` | app/components/realtime-chat/realtime-chat.tsx | `app/components/realtime-chat/realtime-chat::RealtimeChat` | <IconButton> component. Handlers: onClick. |
| `app/components/realtime-chat/realtime-config::RealtimeConfigList.checkbox` | app/components/realtime-chat/realtime-config.tsx | `app/components/realtime-chat/realtime-config::RealtimeConfigList` | Checkbox. Handlers: onChange. |
| `app/components/realtime-chat/realtime-config::RealtimeConfigList.input` | app/components/realtime-chat/realtime-config.tsx | `app/components/realtime-chat/realtime-config::RealtimeConfigList` | Text input. Handlers: onChange. |
| `app/components/realtime-chat/realtime-config::RealtimeConfigList.input-2` | app/components/realtime-chat/realtime-config.tsx | `app/components/realtime-chat/realtime-config::RealtimeConfigList` | Text input. Handlers: onChange. |
| `app/components/realtime-chat/realtime-config::RealtimeConfigList.inputrange` | app/components/realtime-chat/realtime-config.tsx | `app/components/realtime-chat/realtime-config::RealtimeConfigList` | <InputRange> component. Handlers: onChange. |
| `app/components/realtime-chat/realtime-config::RealtimeConfigList.option` | app/components/realtime-chat/realtime-config.tsx | `app/components/realtime-chat/realtime-config::RealtimeConfigList` | Select option. |
| `app/components/realtime-chat/realtime-config::RealtimeConfigList.option-2` | app/components/realtime-chat/realtime-config.tsx | `app/components/realtime-chat/realtime-config::RealtimeConfigList` | Select option. |
| `app/components/realtime-chat/realtime-config::RealtimeConfigList.option-3` | app/components/realtime-chat/realtime-config.tsx | `app/components/realtime-chat/realtime-config::RealtimeConfigList` | Select option. |
| `app/components/realtime-chat/realtime-config::RealtimeConfigList.passwordinput` | app/components/realtime-chat/realtime-config.tsx | `app/components/realtime-chat/realtime-config::RealtimeConfigList` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/realtime-chat/realtime-config::RealtimeConfigList.select` | app/components/realtime-chat/realtime-config.tsx | `app/components/realtime-chat/realtime-config::RealtimeConfigList` | <Select> component. Handlers: onChange. |
| `app/components/realtime-chat/realtime-config::RealtimeConfigList.select-2` | app/components/realtime-chat/realtime-config.tsx | `app/components/realtime-chat/realtime-config::RealtimeConfigList` | <Select> component. Handlers: onChange. |
| `app/components/realtime-chat/realtime-config::RealtimeConfigList.select-3` | app/components/realtime-chat/realtime-config.tsx | `app/components/realtime-chat/realtime-config::RealtimeConfigList` | <Select> component. Handlers: onChange. |
| `app/components/sd/sd-panel::ControlParam.input` | app/components/sd/sd-panel.tsx | `app/components/sd/sd-panel::ControlParam` | Text input. Handlers: onChange. |
| `app/components/sd/sd-panel::ControlParam.number` | app/components/sd/sd-panel.tsx | `app/components/sd/sd-panel::ControlParam` | Number input. Handlers: onChange. |
| `app/components/sd/sd-panel::ControlParam.option` | app/components/sd/sd-panel.tsx | `app/components/sd/sd-panel::ControlParam` | Select option. |
| `app/components/sd/sd-panel::ControlParam.select` | app/components/sd/sd-panel.tsx | `app/components/sd/sd-panel::ControlParam` | <Select> component. Handlers: onChange. |
| `app/components/sd/sd-panel::ControlParam.textarea` | app/components/sd/sd-panel.tsx | `app/components/sd/sd-panel::ControlParam` | Multi-line text field. Handlers: onChange. |
| `app/components/sd/sd-panel::SdPanel.controlparam` | app/components/sd/sd-panel.tsx | `app/components/sd/sd-panel::SdPanel` | <ControlParam> component. Handlers: onChange. |
| `app/components/sd/sd-panel::SdPanel.iconbutton` | app/components/sd/sd-panel.tsx | `app/components/sd/sd-panel::SdPanel` | <IconButton> component. Handlers: onClick. |
| `app/components/sd/sd-sidebar::SideBar.iconbutton` | app/components/sd/sd-sidebar.tsx | `app/components/sd/sd-sidebar::SideBar` | <IconButton> component. Handlers: onClick. |
| `app/components/sd/sd-sidebar::SideBar.iconbutton-2` | app/components/sd/sd-sidebar.tsx | `app/components/sd/sd-sidebar::SideBar` | <IconButton> component. Handlers: onClick. |
| `app/components/sd/sd-sidebar::SideBar.iconbutton-3` | app/components/sd/sd-sidebar.tsx | `app/components/sd/sd-sidebar::SideBar` | <IconButton> component. Handlers: onClick. |
| `app/components/sd/sd-sidebar::SideBar.iconbutton-4` | app/components/sd/sd-sidebar.tsx | `app/components/sd/sd-sidebar::SideBar` | <IconButton> component. type=primary. Handlers: onClick. |
| `app/components/sd/sd-sidebar::SideBar.link` | app/components/sd/sd-sidebar.tsx | `app/components/sd/sd-sidebar::SideBar` | Link. |
| `app/components/sd/sd-sidebar::SideBar.sidebarcontainer` | app/components/sd/sd-sidebar.tsx | `app/components/sd/sd-sidebar::SideBar` | <SideBarContainer> component. Handlers: onDragStart. |
| `app/components/sd/sd::getSdTaskStatus.span` | app/components/sd/sd.tsx |  | <span> element. Handlers: onClick. |
| `app/components/sd/sd::Sd.chataction` | app/components/sd/sd.tsx | `app/components/sd/sd::Sd` | <ChatAction> component. Handlers: onClick. |
| `app/components/sd/sd::Sd.chataction-2` | app/components/sd/sd.tsx | `app/components/sd/sd::Sd` | <ChatAction> component. Handlers: onClick. |
| `app/components/sd/sd::Sd.chataction-3` | app/components/sd/sd.tsx | `app/components/sd/sd::Sd` | <ChatAction> component. Handlers: onClick. |
| `app/components/sd/sd::Sd.chataction-4` | app/components/sd/sd.tsx | `app/components/sd/sd::Sd` | <ChatAction> component. Handlers: onClick. |
| `app/components/sd/sd::Sd.iconbutton` | app/components/sd/sd.tsx | `app/components/sd/sd::Sd` | <IconButton> component. Handlers: onClick. |
| `app/components/sd/sd::Sd.iconbutton-2` | app/components/sd/sd.tsx | `app/components/sd/sd::Sd` | <IconButton> component. Handlers: onClick. |
| `app/components/sd/sd::Sd.img` | app/components/sd/sd.tsx | `app/components/sd/sd::Sd` | <img> element. Handlers: onClick. |
| `app/components/sd/sd::Sd.span` | app/components/sd/sd.tsx | `app/components/sd/sd::Sd` | <span> element. Handlers: onClick. |
| `app/components/search-chat::SearchChatPage.div` | app/components/search-chat.tsx | `app/components/search-chat::SearchChatPage` | <div> element. Handlers: onClick. |
| `app/components/search-chat::SearchChatPage.iconbutton` | app/components/search-chat.tsx | `app/components/search-chat::SearchChatPage` | <IconButton> component. Handlers: onClick. |
| `app/components/search-chat::SearchChatPage.input` | app/components/search-chat.tsx | `app/components/search-chat::SearchChatPage` | Text input. Handlers: onKeyDown. |
| `app/components/settings::CheckButton.iconbutton` | app/components/settings.tsx | `app/components/settings::CheckButton` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::DangerItems.iconbutton` | app/components/settings.tsx | `app/components/settings::DangerItems` | <IconButton> component. type=danger. Handlers: onClick. |
| `app/components/settings::DangerItems.iconbutton-2` | app/components/settings.tsx | `app/components/settings::DangerItems` | <IconButton> component. type=danger. Handlers: onClick. |
| `app/components/settings::EditPromptModal.iconbutton` | app/components/settings.tsx | `app/components/settings::EditPromptModal` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::EditPromptModal.input` | app/components/settings.tsx | `app/components/settings::EditPromptModal` | Text input. Handlers: onInput. |
| `app/components/settings::EditPromptModal.input-2` | app/components/settings.tsx | `app/components/settings::EditPromptModal` | <Input> component. Handlers: onInput. |
| `app/components/settings::EditPromptModal.modal` | app/components/settings.tsx | `app/components/settings::EditPromptModal` | <Modal> component. Handlers: onClose. |
| `app/components/settings::Settings.avatarpicker` | app/components/settings.tsx | `app/components/settings::Settings` | <AvatarPicker> component. Handlers: onEmojiClick. |
| `app/components/settings::Settings.checkbox` | app/components/settings.tsx | `app/components/settings::Settings` | Checkbox. Handlers: onChange. |
| `app/components/settings::Settings.checkbox-2` | app/components/settings.tsx | `app/components/settings::Settings` | Checkbox. Handlers: onChange. |
| `app/components/settings::Settings.checkbox-3` | app/components/settings.tsx | `app/components/settings::Settings` | Checkbox. Handlers: onChange. |
| `app/components/settings::Settings.checkbox-4` | app/components/settings.tsx | `app/components/settings::Settings` | Checkbox. Handlers: onChange. |
| `app/components/settings::Settings.checkbox-5` | app/components/settings.tsx | `app/components/settings::Settings` | Checkbox. Handlers: onChange. |
| `app/components/settings::Settings.checkbox-6` | app/components/settings.tsx | `app/components/settings::Settings` | Checkbox. Handlers: onChange. |
| `app/components/settings::Settings.checkbox-7` | app/components/settings.tsx | `app/components/settings::Settings` | Checkbox. Handlers: onChange. |
| `app/components/settings::Settings.checkbox-8` | app/components/settings.tsx | `app/components/settings::Settings` | Checkbox. Handlers: onChange. |
| `app/components/settings::Settings.div` | app/components/settings.tsx | `app/components/settings::Settings` | <div> element. Handlers: onClick. |
| `app/components/settings::Settings.iconbutton` | app/components/settings.tsx | `app/components/settings::Settings` | <IconButton> component. type=primary. Handlers: onClick. |
| `app/components/settings::Settings.iconbutton-2` | app/components/settings.tsx | `app/components/settings::Settings` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::Settings.iconbutton-3` | app/components/settings.tsx | `app/components/settings::Settings` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::Settings.iconbutton-4` | app/components/settings.tsx | `app/components/settings::Settings` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::Settings.iconbutton-5` | app/components/settings.tsx | `app/components/settings::Settings` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::Settings.iconbutton-6` | app/components/settings.tsx | `app/components/settings::Settings` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::Settings.input` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-10` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-11` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-12` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-13` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-14` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-15` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-16` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-17` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-18` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-19` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-2` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-20` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-21` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. placeholder "model1,model2,model3". Handlers: onChange. |
| `app/components/settings::Settings.input-3` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. placeholder "2023-08-01-preview". Handlers: onChange. |
| `app/components/settings::Settings.input-4` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-5` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. placeholder "2023-08-01-preview". Handlers: onChange. |
| `app/components/settings::Settings.input-6` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-7` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-8` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.input-9` | app/components/settings.tsx | `app/components/settings::Settings` | Text input. Handlers: onChange. |
| `app/components/settings::Settings.inputrange` | app/components/settings.tsx | `app/components/settings::Settings` | <InputRange> component. Handlers: onChange. |
| `app/components/settings::Settings.link` | app/components/settings.tsx | `app/components/settings::Settings` | <Link> component. |
| `app/components/settings::Settings.option` | app/components/settings.tsx | `app/components/settings::Settings` | Select option. |
| `app/components/settings::Settings.option-2` | app/components/settings.tsx | `app/components/settings::Settings` | Select option. |
| `app/components/settings::Settings.option-3` | app/components/settings.tsx | `app/components/settings::Settings` | Select option. |
| `app/components/settings::Settings.option-4` | app/components/settings.tsx | `app/components/settings::Settings` | Select option. |
| `app/components/settings::Settings.option-5` | app/components/settings.tsx | `app/components/settings::Settings` | Select option. |
| `app/components/settings::Settings.passwordinput` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-10` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-11` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-12` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-13` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-14` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-15` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-16` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-17` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-18` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-19` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-2` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-20` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-3` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-4` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-5` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-6` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-7` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-8` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.passwordinput-9` | app/components/settings.tsx | `app/components/settings::Settings` | <PasswordInput> component. type=text. Handlers: onChange. |
| `app/components/settings::Settings.popover` | app/components/settings.tsx | `app/components/settings::Settings` | <Popover> component. Handlers: onClose. |
| `app/components/settings::Settings.select` | app/components/settings.tsx | `app/components/settings::Settings` | <Select> component. Handlers: onChange. |
| `app/components/settings::Settings.select-2` | app/components/settings.tsx | `app/components/settings::Settings` | <Select> component. Handlers: onChange. |
| `app/components/settings::Settings.select-3` | app/components/settings.tsx | `app/components/settings::Settings` | <Select> component. Handlers: onChange. |
| `app/components/settings::Settings.select-4` | app/components/settings.tsx | `app/components/settings::Settings` | <Select> component. Handlers: onChange. |
| `app/components/settings::Settings.select-5` | app/components/settings.tsx | `app/components/settings::Settings` | <Select> component. Handlers: onChange. |
| `app/components/settings::Settings.userpromptmodal` | app/components/settings.tsx | `app/components/settings::Settings` | <UserPromptModal> component. Handlers: onClose. |
| `app/components/settings::SyncConfigModal.checkbox` | app/components/settings.tsx | `app/components/settings::SyncConfigModal` | Checkbox. Handlers: onChange. |
| `app/components/settings::SyncConfigModal.iconbutton` | app/components/settings.tsx | `app/components/settings::SyncConfigModal` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::SyncConfigModal.input` | app/components/settings.tsx | `app/components/settings::SyncConfigModal` | Text input. Handlers: onChange. |
| `app/components/settings::SyncConfigModal.input-2` | app/components/settings.tsx | `app/components/settings::SyncConfigModal` | Text input. Handlers: onChange. |
| `app/components/settings::SyncConfigModal.input-3` | app/components/settings.tsx | `app/components/settings::SyncConfigModal` | Text input. Handlers: onChange. |
| `app/components/settings::SyncConfigModal.input-4` | app/components/settings.tsx | `app/components/settings::SyncConfigModal` | Text input. Handlers: onChange. |
| `app/components/settings::SyncConfigModal.input-5` | app/components/settings.tsx | `app/components/settings::SyncConfigModal` | Text input. Handlers: onChange. |
| `app/components/settings::SyncConfigModal.modal` | app/components/settings.tsx | `app/components/settings::SyncConfigModal` | <Modal> component. Handlers: onClose. |
| `app/components/settings::SyncConfigModal.option` | app/components/settings.tsx | `app/components/settings::SyncConfigModal` | Select option. |
| `app/components/settings::SyncConfigModal.passwordinput` | app/components/settings.tsx | `app/components/settings::SyncConfigModal` | <PasswordInput> component. Handlers: onChange. |
| `app/components/settings::SyncConfigModal.passwordinput-2` | app/components/settings.tsx | `app/components/settings::SyncConfigModal` | <PasswordInput> component. Handlers: onChange. |
| `app/components/settings::SyncConfigModal.select` | app/components/settings.tsx | `app/components/settings::SyncConfigModal` | Dropdown select. Handlers: onChange. |
| `app/components/settings::SyncItems.iconbutton` | app/components/settings.tsx | `app/components/settings::SyncItems` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::SyncItems.iconbutton-2` | app/components/settings.tsx | `app/components/settings::SyncItems` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::SyncItems.iconbutton-3` | app/components/settings.tsx | `app/components/settings::SyncItems` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::SyncItems.iconbutton-4` | app/components/settings.tsx | `app/components/settings::SyncItems` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::SyncItems.syncconfigmodal` | app/components/settings.tsx | `app/components/settings::SyncItems` | <SyncConfigModal> component. Handlers: onClose. |
| `app/components/settings::UserPromptModal.editpromptmodal` | app/components/settings.tsx | `app/components/settings::UserPromptModal` | <EditPromptModal> component. Handlers: onClose. |
| `app/components/settings::UserPromptModal.iconbutton` | app/components/settings.tsx | `app/components/settings::UserPromptModal` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::UserPromptModal.iconbutton-2` | app/components/settings.tsx | `app/components/settings::UserPromptModal` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::UserPromptModal.iconbutton-3` | app/components/settings.tsx | `app/components/settings::UserPromptModal` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::UserPromptModal.iconbutton-4` | app/components/settings.tsx | `app/components/settings::UserPromptModal` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::UserPromptModal.iconbutton-5` | app/components/settings.tsx | `app/components/settings::UserPromptModal` | <IconButton> component. Handlers: onClick. |
| `app/components/settings::UserPromptModal.input` | app/components/settings.tsx | `app/components/settings::UserPromptModal` | Text input. Handlers: onInput. |
| `app/components/settings::UserPromptModal.modal` | app/components/settings.tsx | `app/components/settings::UserPromptModal` | <Modal> component. Handlers: onClose. |
| `app/components/sidebar::SideBar-2.iconbutton` | app/components/sidebar.tsx | `app/components/sidebar::SideBar` | <IconButton> component. Handlers: onClick. |
| `app/components/sidebar::SideBar-2.iconbutton-2` | app/components/sidebar.tsx | `app/components/sidebar::SideBar` | <IconButton> component. Handlers: onClick. |
| `app/components/sidebar::SideBar-2.iconbutton-3` | app/components/sidebar.tsx | `app/components/sidebar::SideBar` | <IconButton> component. Handlers: onClick. |
| `app/components/sidebar::SideBar-2.iconbutton-4` | app/components/sidebar.tsx | `app/components/sidebar::SideBar` | <IconButton> component. Handlers: onClick. |
| `app/components/sidebar::SideBar-2.iconbutton-5` | app/components/sidebar.tsx | `app/components/sidebar::SideBar` | <IconButton> component. Handlers: onClick. |
| `app/components/sidebar::SideBar-2.link` | app/components/sidebar.tsx | `app/components/sidebar::SideBar` | Link. |
| `app/components/sidebar::SideBar-2.selector` | app/components/sidebar.tsx | `app/components/sidebar::SideBar` | <Selector> component. Handlers: onClose, onSelection. |
| `app/components/sidebar::SideBar-2.sidebarbody` | app/components/sidebar.tsx | `app/components/sidebar::SideBar` | <SideBarBody> component. Handlers: onClick. |
| `app/components/sidebar::SideBar-2.sidebarcontainer` | app/components/sidebar.tsx | `app/components/sidebar::SideBar` | <SideBarContainer> component. Handlers: onDragStart. |
| `app/components/sidebar::SideBarBody.div` | app/components/sidebar.tsx | `app/components/sidebar::SideBarBody` | <div> element. Handlers: onClick. |
| `app/components/sidebar::SideBarContainer.div` | app/components/sidebar.tsx | `app/components/sidebar::SideBarContainer` | <div> element. Handlers: onPointerDown. |
| `app/components/tts-config::TTSConfigList.checkbox` | app/components/tts-config.tsx | `app/components/tts-config::TTSConfigList` | Checkbox. Handlers: onChange. |
| `app/components/tts-config::TTSConfigList.inputrange` | app/components/tts-config.tsx | `app/components/tts-config::TTSConfigList` | <InputRange> component. Handlers: onChange. |
| `app/components/tts-config::TTSConfigList.option` | app/components/tts-config.tsx | `app/components/tts-config::TTSConfigList` | Select option. |
| `app/components/tts-config::TTSConfigList.option-2` | app/components/tts-config.tsx | `app/components/tts-config::TTSConfigList` | Select option. |
| `app/components/tts-config::TTSConfigList.option-3` | app/components/tts-config.tsx | `app/components/tts-config::TTSConfigList` | Select option. |
| `app/components/tts-config::TTSConfigList.select` | app/components/tts-config.tsx | `app/components/tts-config::TTSConfigList` | <Select> component. Handlers: onChange. |
| `app/components/tts-config::TTSConfigList.select-2` | app/components/tts-config.tsx | `app/components/tts-config::TTSConfigList` | <Select> component. Handlers: onChange. |
| `app/components/tts-config::TTSConfigList.select-3` | app/components/tts-config.tsx | `app/components/tts-config::TTSConfigList` | <Select> component. Handlers: onChange. |
| `app/components/ui-lib::FullScreen.iconbutton` | app/components/ui-lib.tsx | `app/components/ui-lib::FullScreen` | <IconButton> component. Handlers: onClick. |
| `app/components/ui-lib::Input.textarea` | app/components/ui-lib.tsx | `app/components/ui-lib::Input` | Multi-line text field. |
| `app/components/ui-lib::ListItem.div` | app/components/ui-lib.tsx | `app/components/ui-lib::ListItem` | <div> element. Handlers: onClick. |
| `app/components/ui-lib::Modal.div` | app/components/ui-lib.tsx | `app/components/ui-lib::Modal` | <div> element. Handlers: onClick. |
| `app/components/ui-lib::Modal.div-2` | app/components/ui-lib.tsx | `app/components/ui-lib::Modal` | <div> element. Handlers: onClick. |
| `app/components/ui-lib::PasswordInput.iconbutton` | app/components/ui-lib.tsx | `app/components/ui-lib::PasswordInput` | <IconButton> component. Handlers: onClick. |
| `app/components/ui-lib::PasswordInput.input` | app/components/ui-lib.tsx | `app/components/ui-lib::PasswordInput` | Text input field. |
| `app/components/ui-lib::Popover.div` | app/components/ui-lib.tsx | `app/components/ui-lib::Popover` | <div> element. Handlers: onClick. |
| `app/components/ui-lib::PromptInput.textarea` | app/components/ui-lib.tsx | `app/components/ui-lib::PromptInput` | Multi-line text field. Handlers: onInput. |
| `app/components/ui-lib::Select.select` | app/components/ui-lib.tsx | `app/components/ui-lib::Select` | Dropdown select. |
| `app/components/ui-lib::Selector.div` | app/components/ui-lib.tsx | `app/components/ui-lib::Selector` | <div> element. Handlers: onClick. |
| `app/components/ui-lib::Selector.listitem` | app/components/ui-lib.tsx | `app/components/ui-lib::Selector` | <ListItem> component. Handlers: onClick. |
| `app/components/ui-lib::showConfirm.iconbutton` | app/components/ui-lib.tsx |  | <IconButton> component. Handlers: onClick. |
| `app/components/ui-lib::showConfirm.iconbutton-2` | app/components/ui-lib.tsx |  | <IconButton> component. type=primary. Handlers: onClick. |
| `app/components/ui-lib::showConfirm.modal` | app/components/ui-lib.tsx |  | <Modal> component. Handlers: onClose. |
| `app/components/ui-lib::showModal.modal` | app/components/ui-lib.tsx |  | <Modal> component. Handlers: onClose. |
| `app/components/ui-lib::showPrompt.iconbutton` | app/components/ui-lib.tsx |  | <IconButton> component. Handlers: onClick. |
| `app/components/ui-lib::showPrompt.iconbutton-2` | app/components/ui-lib.tsx |  | <IconButton> component. type=primary. Handlers: onClick. |
| `app/components/ui-lib::showPrompt.modal` | app/components/ui-lib.tsx |  | <Modal> component. Handlers: onClose. |
| `app/components/ui-lib::showPrompt.promptinput` | app/components/ui-lib.tsx |  | <PromptInput> component. Handlers: onChange. |
| `app/components/ui-lib::showToast.toast` | app/components/ui-lib.tsx |  | <Toast> component. Handlers: onClose. |
| `app/components/ui-lib::Toast.button` | app/components/ui-lib.tsx | `app/components/ui-lib::Toast` | Button. Handlers: onClick. |
| `app/layout::RootLayout.link` | app/layout.tsx | `app/layout::RootLayout` | <link> element. href "/site.webmanifest". |

## The code on the way to the AI: endpoint handlers and functions that call a model (16)

| identifier | file | description |
| --- | --- | --- |
| `app/api/artifacts/route::handle` | app/api/artifacts/route.ts | Function 'handle'. Params: req, res. |
| `app/api/config/route::handle` | app/api/config/route.ts | Function 'handle'. |
| `app/api/tencent/route::handle` | app/api/tencent/route.ts | Function 'handle'. Params: req, {…}. |
| `app/api/tencent/route::request` | app/api/tencent/route.ts | Function 'request'. Params: req. |
| `app/client/platforms/ai302::Ai302Api` | app/client/platforms/ai302.ts | Exported Class 'Ai302Api'. |
| `app/client/platforms/anthropic::ClaudeApi` | app/client/platforms/anthropic.ts | Exported Class 'ClaudeApi'. |
| `app/client/platforms/baidu::ErnieApi` | app/client/platforms/baidu.ts | Exported Class 'ErnieApi'. |
| `app/client/platforms/bytedance::DoubaoApi` | app/client/platforms/bytedance.ts | Exported Class 'DoubaoApi'. |
| `app/client/platforms/deepseek::DeepSeekApi` | app/client/platforms/deepseek.ts | Exported Class 'DeepSeekApi'. |
| `app/client/platforms/google::GeminiProApi` | app/client/platforms/google.ts | Exported Class 'GeminiProApi'. |
| `app/client/platforms/iflytek::SparkApi` | app/client/platforms/iflytek.ts | Exported Class 'SparkApi'. |
| `app/client/platforms/moonshot::MoonshotApi` | app/client/platforms/moonshot.ts | Exported Class 'MoonshotApi'. |
| `app/client/platforms/openai::ChatGPTApi` | app/client/platforms/openai.ts | Exported Class 'ChatGPTApi'. |
| `app/client/platforms/siliconflow::SiliconflowApi` | app/client/platforms/siliconflow.ts | Exported Class 'SiliconflowApi'. |
| `app/client/platforms/tencent::HunyuanApi` | app/client/platforms/tencent.ts | Exported Class 'HunyuanApi'. |
| `app/client/platforms/xai::XAIApi` | app/client/platforms/xai.ts | Exported Class 'XAIApi'. |

## Instructions sent to a model (2)

| identifier | file | description |
| --- | --- | --- |
| `app/constant::DEFAULT_SYSTEM_TEMPLATE` | app/constant.ts | Prompt / instruction constant 'DEFAULT_SYSTEM_TEMPLATE' (216 chars). |
| `app/constant::MCP_SYSTEM_TEMPLATE` | app/constant.ts | Prompt / instruction constant 'MCP_SYSTEM_TEMPLATE' (3018 chars). |
