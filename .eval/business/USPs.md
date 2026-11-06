# Unique selling propositions

_Each USP is sourced to a business document (verbatim) and mapped to the components that deliver it._

## Zero-config AI chat assistant

Marketed as a zero-config AI chat assistant: no API key needed — sign up and instantly chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek and 100+ top models.

- **Sources:**
  - `About_the_organisation.md`: "✨ Zero-config AI chat assistant."
  - `About_the_organisation.md`: "No API key needed — sign up and instantly chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek & 100+ top models."
- **Delivered by:**
  - `app/client/platforms/deepseek::DeepSeekApi`, matched on name "seek" in DeepSeekApi; name "deep" in DeepSeekApi; module "claude" in module app/client; +2 more
  - `app/client/platforms/anthropic::ClaudeApi`, matched on name "claude" in ClaudeApi; module "gemini" in module app/client; module "seek" in module app/client; +2 more
  - `app/client/platforms/google::GeminiProApi`, matched on name "gemini" in GeminiProApi; module "claude" in module app/client; module "seek" in module app/client; +2 more
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## One chat window for many models with your own API key

Users bring their own API key and get one clean web chat interface for talking to many large language models.

- **Sources:**
  - `About_the_organisation.md`: "Individuals and small teams who want one web chat interface for several AI models, using their own API key."
  - `about-nextchat.md`: "People bring their own API key and get one clean chat window for many models."
- **Delivered by:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents
  - `app/components/model-config::ModelConfigList`, matched on named by the model while reading the business documents

## Open-source (MIT) and self-hostable

NextChat is an open-source (MIT) web chat interface that individuals, developers and small teams can self-host for a fast, private chat UI.

- **Sources:**
  - `about-nextchat.md`: "NextChat is an open-source (MIT) web chat interface for talking to large language models."
  - `about-nextchat.md`: "Individuals, developers and small teams who want a fast, private chat UI they can self-host."
- **Delivered by:** _no linked components_

## Streaming answers from OpenAI-compatible models

Chat with an OpenAI-compatible model and receive streamed answers.

- **Sources:**
  - `about-nextchat.md`: "Chat with an OpenAI-compatible model, with streaming answers."
- **Delivered by:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## Conversations and prompt templates (masks) kept in the browser

Conversations and prompt templates called "masks" are stored locally in the browser; there is no sign-in or database, everything lives on the user's device.

- **Sources:**
  - `about-nextchat.md`: "Keep conversations and prompt templates ("masks") in the browser."
  - `about-nextchat.md`: "There is no sign-in and no database; everything is stored on the user's device."
- **Delivered by:**
  - `app/components/mask::MaskPage`, matched on named by the model while reading the business documents
  - `app/components/mask::MaskConfig`, matched on named by the model while reading the business documents

## Configurable model and API address

Users choose the model and the API address; in this deployment the address points to OpenRouter.

- **Sources:**
  - `about-nextchat.md`: "Choose the model and the API address; in our deployment the address points to OpenRouter."
- **Delivered by:**
  - `app/components/model-config::ModelConfigList`, matched on named by the model while reading the business documents
  - `app/components/settings::Settings`, matched on named by the model while reading the business documents

## Coverage

- **Statements linked to code:** 10 of 12 · rule: 5/6 · usp: 5/6
- **Artifacts reached from the business:** 8 of 524 linkable artifacts in the scan
- **How the links were made:** candidates from names, paths, routes and endpoints in your own code, confirmed by the model.

### Reach by area

- App: 8 of 425
- Test: 0 of 38
- Utils: 0 of 30
- Public: 0 of 8
- Scripts: 0 of 6
- Constant: 0 of 4
- Other: 0 of 4
- Command: 0 of 3
- Layout: 0 of 2
- Page: 0 of 2
- Polyfill: 0 of 1
- Typing: 0 of 1

### Linked to nothing (2)

- **usp** Open-source (MIT) and self-hostable: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** There is no sign-in and no database; everything is stored on the user's device.: The only words that matched a name, path or route are too short to mean one thing (sign, user), and a three- or four-letter stem matches by accident across two languages. Something longer has to match the same artifact.

## Gaps

_None. All material was sourced._
