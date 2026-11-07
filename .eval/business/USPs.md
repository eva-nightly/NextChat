# Unique selling propositions

_Each USP is sourced to a business document (verbatim) and mapped to the components that deliver it._

## Zero-config AI chat assistant

Positioned as a zero-config chat assistant: pick it up and start chatting with AI models with minimal setup.

- **Sources:**
  - `About_the_organisation.md`: "✨ Zero-config AI chat assistant."
- **Delivered by:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## Access to 100+ top models through one interface

Chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek and 100+ other models; in this deployment the app is pointed at OpenRouter as an OpenAI-compatible endpoint via BASE_URL. Note: the organisation tagline says 'no API key needed — sign up', which conflicts with other sources stating users bring their own key and there is no sign-in.

- **Sources:**
  - `About_the_organisation.md`: "No API key needed — sign up and instantly chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek & 100+ top models."
  - `about-nextchat.md`: "Users bring their own API key, or point the app at an OpenAI-compatible endpoint through BASE_URL."
  - `about-nextchat.md`: "In our deployment the endpoint is OpenRouter, which stands in for OpenAI."
- **Delivered by:**
  - `app/client/platforms/deepseek::DeepSeekApi`, matched on name "seek" in DeepSeekApi; name "deep" in DeepSeekApi; module "claude" in module app/client; +3 more
  - `app/client/platforms/google::GeminiProApi`, matched on name "gemini" in GeminiProApi; module "claude" in module app/client; module "rout" in module app/client; +3 more
  - `app/client/platforms/anthropic::ClaudeApi`, matched on name "claude" in ClaudeApi; module "gemini" in module app/client; module "rout" in module app/client; +3 more
  - `app/components/model-config::ModelConfigList`, matched on named by the model while reading the business documents

## Bring your own API key — no vendor account

Users supply their own API key (or an OpenAI-compatible endpoint) rather than creating an account with a vendor.

- **Sources:**
  - `About_the_organisation.md`: "People who want a fast, private chat UI for talking to AI models such as GPT, Claude and Gemini, using their own API key."
  - `about-nextchat.md`: "Users bring their own API key, or point the app at an OpenAI-compatible endpoint through BASE_URL."
  - `about-nextchat.md`: "Individuals and small teams who want a fast, private chat UI without a vendor account."
- **Delivered by:**
  - `app/components/auth::AuthPage`, matched on named by the model while reading the business documents

## Private by design: no database, no sign-in

There is no database and no sign-in; conversations stay in the user's browser, giving a fast, private chat UI.

- **Sources:**
  - `About_the_organisation.md`: "People who want a fast, private chat UI for talking to AI models such as GPT, Claude and Gemini, using their own API key."
  - `about-nextchat.md`: "No database and no sign-in: conversations stay in the browser."
  - `about-nextchat.md`: "Individuals and small teams who want a fast, private chat UI without a vendor account."
- **Delivered by:** _no linked components_

## Open-source (MIT) web chat interface

NextChat is an open-source, MIT-licensed web chat interface for talking to large language models.

- **Sources:**
  - `about-nextchat.md`: "NextChat is an open-source (MIT) web chat interface for talking to large language models."
- **Delivered by:** _no linked components_

## Multi-turn streaming chat with markdown and code rendering

Conversations are multi-turn, answers stream in, and responses render markdown and code.

- **Sources:**
  - `about-nextchat.md`: "Multi-turn chat with streaming answers and markdown/code rendering."
- **Delivered by:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## Saved conversations and masks

Conversations are saved and users can apply 'masks' — prompt presets for a role or task.

- **Sources:**
  - `about-nextchat.md`: "Saved conversations and "masks" (prompt presets for a role or task)."
- **Delivered by:**
  - `app/components/mask::MaskPage`, matched on named by the model while reading the business documents
  - `app/components/mask::MaskConfig`, matched on named by the model while reading the business documents
  - `app/components/mask::ContextPrompts`, matched on named by the model while reading the business documents

## Model picker, temperature and system prompt settings

Users can choose the model and tune temperature and the system prompt.

- **Sources:**
  - `about-nextchat.md`: "Model picker, temperature and system prompt settings."
- **Delivered by:**
  - `app/components/model-config::ModelConfigList`, matched on named by the model while reading the business documents
  - `app/components/chat::SessionConfigModel`, matched on named by the model while reading the business documents

## Conversation summaries keep long chats within the context window

Long conversations are summarised so they continue to fit within the model's context window.

- **Sources:**
  - `about-nextchat.md`: "Conversation summaries that keep long chats within the context window."
- **Delivered by:** _no linked components_

## Coverage

- **Statements linked to code:** 9 of 15 · rule: 3/6 · usp: 6/9
- **Artifacts reached from the business:** 11 of 524 linkable artifacts in the scan
- **How the links were made:** candidates from names, paths, routes and endpoints in your own code, confirmed by the model.

### Reach by area

- App: 10 of 425
- Test: 0 of 38
- Utils: 0 of 30
- Public: 0 of 8
- Scripts: 0 of 6
- Constant: 1 of 4
- Other: 0 of 4
- Command: 0 of 3
- Layout: 0 of 2
- Page: 0 of 2
- Polyfill: 0 of 1
- Typing: 0 of 1

### Linked to nothing (6)

- **usp** Private by design: no database, no sign-in: 3 candidate(s) were offered and the model confirmed none of them.
- **usp** Open-source (MIT) web chat interface: 1 candidate(s) were offered and the model confirmed none of them.
- **usp** Conversation summaries keep long chats within the context window: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** No database and no sign-in: conversations must stay in the browser.: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** In this deployment the endpoint is OpenRouter, standing in for OpenAI.: No artifact NAME, path, route or endpoint in the codebase matches any word in it. It may be a rule about how people work rather than about what the product does.
- **rule** Long chats are summarised so the conversation stays within the context window.: 1 candidate(s) were offered and the model confirmed none of them.

## Gaps

_None. All material was sourced._
