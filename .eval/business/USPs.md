# Unique selling propositions

_Each USP is sourced to a business document (verbatim) and mapped to the components that deliver it._

## Zero-config AI chat assistant

Sign up and instantly chat with an AI assistant — no API key needed and no setup.

- **Sources:**
  - `About_the_organisation.md`: "✨ Zero-config AI chat assistant."
  - `About_the_organisation.md`: "No API key needed — sign up and instantly chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek & 100+ top models."
- **Delivered by:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## Access to 100+ top models

Chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek and over 100 other leading models from one interface.

- **Sources:**
  - `About_the_organisation.md`: "No API key needed — sign up and instantly chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek & 100+ top models."
- **Delivered by:**
  - `app/client/platforms/deepseek::DeepSeekApi`, matched on name "seek" in DeepSeekApi; name "deep" in DeepSeekApi; module "claude" in module app/client; +2 more
  - `app/client/platforms/google::GeminiProApi`, matched on name "gemini" in GeminiProApi; module "claude" in module app/client; module "gpt" in module app/client; +2 more
  - `app/client/platforms/anthropic::ClaudeApi`, matched on name "claude" in ClaudeApi; module "gemini" in module app/client; module "gpt" in module app/client; +2 more
  - `app/components/model-config::ModelConfigList`, matched on named by the model while reading the business documents

## Streaming answers in the browser

Users type questions and the AI answers helpfully and correctly with streamed replies, directly in the browser.

- **Sources:**
  - `About_the_organisation.md`: "A chat assistant: users type questions and the AI answers helpfully and correctly, in the user's language, streaming replies."
  - `about-nextchat.md`: "Lets a person chat with an AI assistant in the browser, with streaming answers."
- **Delivered by:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## Private, local conversation history

Conversation history is kept locally in the browser; there is no database and no sign-in.

- **Sources:**
  - `about-nextchat.md`: "Keeps conversation history locally in the browser; there is no database and no sign-in."
- **Delivered by:** _no linked components_

## Prompt templates (masks)

Preset-role prompt templates called masks let users start conversations with a predefined persona.

- **Sources:**
  - `about-nextchat.md`: "Offers prompt templates ("masks") to start conversations with a preset role."
- **Delivered by:**
  - `app/components/mask::MaskPage`, matched on named by the model while reading the business documents
  - `app/components/mask::MaskConfig`, matched on named by the model while reading the business documents
  - `app/components/mask::ContextPrompts`, matched on named by the model while reading the business documents

## Open-source (MIT)

NextChat is an MIT-licensed open-source web chat interface for large language models.

- **Sources:**
  - `about-nextchat.md`: "NextChat is an open-source (MIT) web chat interface for large language models."
- **Delivered by:** _no linked components_

## Works with any OpenAI-compatible API

Talks to an OpenAI-compatible API whose address is set via BASE_URL (here OpenRouter), so users can bring their own model keys.

- **Sources:**
  - `about-nextchat.md`: "Talks to an OpenAI-compatible API; the address is set with BASE_URL (here: OpenRouter)."
  - `about-nextchat.md`: "Individuals and small teams who want a fast, private chat UI for their own model keys."
- **Delivered by:** _no linked components_

## Coverage

- **Statements linked to code:** 11 of 16 · rule: 7/9 · usp: 4/7
- **Artifacts reached from the business:** 9 of 524 linkable artifacts in the scan
- **How the links were made:** candidates from names, paths, routes and endpoints in your own code, confirmed by the model.

### Reach by area

- App: 8 of 425
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

### Linked to nothing (5)

- **usp** Private, local conversation history: 1 candidate(s) were offered and the model confirmed none of them.
- **usp** Open-source (MIT): 1 candidate(s) were offered and the model confirmed none of them.
- **usp** Works with any OpenAI-compatible API: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** Conversation history is stored locally in the browser; there is no database and no sign-in.: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** The model provider is reached through an OpenAI-compatible API whose address is configured with BASE_URL.: 3 candidate(s) were offered and the model confirmed none of them.

## Gaps

_None. All material was sourced._
