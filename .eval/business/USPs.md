# Unique selling propositions

_Each USP is sourced to a business document (verbatim) and mapped to the components that deliver it._

## Zero-config AI chat assistant

No API key needed — users sign up and instantly chat with top models without any setup.

- **Sources:**
  - `About_the_organisation.md`: "✨ Zero-config AI chat assistant."
  - `About_the_organisation.md`: "No API key needed — sign up and instantly chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek & 100+ top models."
- **Delivered by:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## One chat window for 100+ top models

Chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek and 100+ other models from a single interface, with the ability to switch models.

- **Sources:**
  - `About_the_organisation.md`: "No API key needed — sign up and instantly chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek & 100+ top models."
  - `nextchat-overview.md`: "Students and hobbyists who want one chat window for many models."
  - `nextchat-overview.md`: "Conversations keep history; users can set a system prompt ("masks") and switch models."
- **Delivered by:**
  - `app/client/platforms/deepseek::DeepSeekApi`, matched on name "seek" in DeepSeekApi; name "deep" in DeepSeekApi; module "claude" in module app/client; +2 more
  - `app/client/platforms/anthropic::ClaudeApi`, matched on name "claude" in ClaudeApi; module "gemini" in module app/client; module "seek" in module app/client; +2 more
  - `app/client/platforms/google::GeminiProApi`, matched on name "gemini" in GeminiProApi; module "claude" in module app/client; module "seek" in module app/client; +2 more
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents
  - `app/components/model-config::ModelConfigList`, matched on named by the model while reading the business documents

## Open-source (MIT) web chat interface

NextChat is an MIT-licensed web chat interface for talking to large language models, built with Next.js and self-hostable as a private ChatGPT-style UI.

- **Sources:**
  - `nextchat-overview.md`: "NextChat is an open-source (MIT) web chat interface for talking to large language models."
  - `nextchat-overview.md`: "It is built with Next.js (app router) and deployed by individuals and small teams."
  - `nextchat-overview.md`: "Developers who self-host a private ChatGPT-style UI."
- **Delivered by:** _no linked components_

## Streamed answers in the browser

Users open the app in a browser, type a message and get a streamed answer from the model.

- **Sources:**
  - `nextchat-overview.md`: "Users open the app in a browser, type a message and get a streamed answer from the model."
- **Delivered by:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## System prompts via masks and conversation history

Conversations keep history; users can set a system prompt ("masks") and switch models.

- **Sources:**
  - `nextchat-overview.md`: "Conversations keep history; users can set a system prompt ("masks") and switch models."
- **Delivered by:**
  - `app/components/mask::MaskPage`, matched on named by the model while reading the business documents
  - `app/components/mask::MaskConfig`, matched on named by the model while reading the business documents
  - `app/components/mask::ContextPrompts`, matched on named by the model while reading the business documents
  - `app/components/chat::SessionConfigModel`, matched on named by the model while reading the business documents

## No database, no sign-in

Sessions live in the browser; there is no database and no sign-in required.

- **Sources:**
  - `nextchat-overview.md`: "No database and no sign-in: sessions live in the browser."
- **Delivered by:** _no linked components_

## Coverage

- **Statements linked to code:** 10 of 14 · rule: 6/8 · usp: 4/6
- **Artifacts reached from the business:** 9 of 524 linkable artifacts in the scan
- **How the links were made:** candidates from names, paths, routes and endpoints in your own code, confirmed by the model.

### Reach by area

- App: 9 of 425
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

### Linked to nothing (4)

- **usp** Open-source (MIT) web chat interface: 2 candidate(s) were offered and the model confirmed none of them.
- **usp** No database, no sign-in: The only words that matched a name, path or route are too short to mean one thing (sign), and a three- or four-letter stem matches by accident across two languages. Something longer has to match the same artifact.
- **rule** The server forwards chat requests to an OpenAI-compatible API (BASE_URL), here OpenRouter.: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** No database and no sign-in: sessions live in the browser.: The only words that matched a name, path or route are too short to mean one thing (sign), and a three- or four-letter stem matches by accident across two languages. Something longer has to match the same artifact.

## Gaps

_None. All material was sourced._
