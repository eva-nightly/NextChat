# Unique selling propositions

_Each USP is sourced to a business document (verbatim) and mapped to the components that deliver it._

## Zero-config AI chat assistant

Sign up and instantly chat — no API key needed to get started.

- **Sources:**
  - `About_the_organisation.md`: "✨ Zero-config AI chat assistant."
  - `About_the_organisation.md`: "No API key needed — sign up and instantly chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek & 100+ top models."
- **Delivered by:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## One UI for 100+ top models

Chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek and 100+ other models through a single OpenAI-compatible API (OpenRouter).

- **Sources:**
  - `About_the_organisation.md`: "No API key needed — sign up and instantly chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek & 100+ top models."
  - `About_the_organisation.md`: "It is a chat assistant: it relays the user's messages to an OpenAI-compatible model (via OpenRouter) and streams back answers."
  - `about-nextchat.md`: "It is used by developers and hobbyists who want one clean UI for many models."
  - `about-nextchat.md`: "Streams answers from an OpenAI-compatible API (here OpenRouter, set via BASE_URL)."
- **Delivered by:**
  - `app/components/model-config::ModelConfigList`, matched on named by the model while reading the business documents

## Streaming answers

Relays the user's messages to an OpenAI-compatible model and streams back answers.

- **Sources:**
  - `About_the_organisation.md`: "It is a chat assistant: it relays the user's messages to an OpenAI-compatible model (via OpenRouter) and streams back answers."
  - `about-nextchat.md`: "Streams answers from an OpenAI-compatible API (here OpenRouter, set via BASE_URL)."
- **Delivered by:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## Lightweight and self-hostable

A lightweight chat interface for LLMs that developers and hobbyists can self-host.

- **Sources:**
  - `About_the_organisation.md`: "Developers and hobbyists who want a self-hosted chat UI for LLMs."
  - `about-nextchat.md`: "NextChat is a lightweight, self-hostable chat interface for large language models."
- **Delivered by:** _no linked components_

## Local history, no database or sign-in

Conversation history is kept locally in the browser; there is no database or sign-in.

- **Sources:**
  - `about-nextchat.md`: "Keeps conversation history locally in the browser; there is no database or sign-in."
- **Delivered by:** _no linked components_

## Prompt templates (masks)

Offers prompt templates called masks to start chats with a role or task.

- **Sources:**
  - `about-nextchat.md`: "Offers prompt templates ("masks") to start chats with a role or task."
- **Delivered by:**
  - `app/components/mask::MaskPage`, matched on named by the model while reading the business documents
  - `app/components/mask::MaskConfig`, matched on named by the model while reading the business documents
  - `app/components/mask::ContextPrompts`, matched on named by the model while reading the business documents

## Coverage

- **Statements linked to code:** 7 of 11 · rule: 3/5 · usp: 4/6
- **Artifacts reached from the business:** 5 of 524 linkable artifacts in the scan
- **How the links were made:** candidates from names, paths, routes and endpoints in your own code, confirmed by the model.

### Reach by area

- App: 5 of 425
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

- **usp** Lightweight and self-hostable: 1 candidate(s) were offered and the model confirmed none of them.
- **usp** Local history, no database or sign-in: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** Messages are relayed to an OpenAI-compatible API (OpenRouter), configured via BASE_URL.: 2 candidate(s) were offered and the model confirmed none of them.
- **rule** Conversation history is stored locally in the browser; there is no database or sign-in.: 1 candidate(s) were offered and the model confirmed none of them.

## Gaps

_None. All material was sourced._
