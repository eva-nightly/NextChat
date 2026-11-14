# Unique selling propositions

_Each USP is sourced to a business document (verbatim) and mapped to the components that deliver it._

## Lightweight, open-source (MIT) chat interface for LLMs

NextChat is a lightweight, MIT-licensed, open-source web chat UI for talking to large language models.

- **Sources:**
  - `About_the_organisation.md`: "A web chat UI where people talk to AI models (through an OpenAI-compatible API such as OpenRouter) with sessions, prompts and settings."
  - `business.md`: "NextChat is a lightweight, open-source (MIT) chat interface for large language models."
- **Delivered by:** _no linked components_

## Chat sessions with history, stored in the browser

Conversations are kept as sessions with history, stored locally in the browser rather than on a server.

- **Sources:**
  - `About_the_organisation.md`: "A web chat UI where people talk to AI models (through an OpenAI-compatible API such as OpenRouter) with sessions, prompts and settings."
  - `business.md`: "Chat sessions with history, stored in the browser."
- **Delivered by:**
  - `app/store/chat::createEmptySession`, matched on name "session" in createEmptySession; path "chat" in app/store/chat; module "history" in module app/store; +2 more
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## Prompt templates (masks) for repeated tasks

Reusable prompt templates, called masks, let users set up repeated tasks quickly.

- **Sources:**
  - `About_the_organisation.md`: "A web chat UI where people talk to AI models (through an OpenAI-compatible API such as OpenRouter) with sessions, prompts and settings."
  - `business.md`: "Prompt templates ("masks") for repeated tasks."
- **Delivered by:**
  - `app/components/chat::SessionConfigModel`, matched on name "session" in SessionConfigModel; path "chat" in app/components/chat; description "mask" in its description
  - `app/components/mask::MaskPage`, matched on named by the model while reading the business documents
  - `app/components/mask::MaskConfig`, matched on named by the model while reading the business documents
  - `app/components/mask::ContextPrompts`, matched on named by the model while reading the business documents

## Streaming answers from any OpenAI-compatible API

Answers stream from any OpenAI-compatible provider; the endpoint is configured via BASE_URL, with OpenRouter standing in for OpenAI.

- **Sources:**
  - `About_the_organisation.md`: "A web chat UI where people talk to AI models (through an OpenAI-compatible API such as OpenRouter) with sessions, prompts and settings."
  - `business.md`: "Streaming answers from any OpenAI-compatible API; here the address is BASE_URL and OpenRouter stands in for OpenAI."
- **Delivered by:**
  - `app/utils/chat::stream`, matched on name "stream" in stream; path "chat" in app/utils/chat; module "session" in module app/utils; +2 more
  - `app/utils/chat::streamWithThink`, matched on name "stream" in streamWithThink; path "chat" in app/utils/chat; module "session" in module app/utils; +2 more
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## One place for several AI models

A single clean interface for chatting with several AI models, with sessions, prompts and settings.

- **Sources:**
  - `About_the_organisation.md`: "A web chat UI where people talk to AI models (through an OpenAI-compatible API such as OpenRouter) with sessions, prompts and settings."
  - `business.md`: "Individual developers and small teams who want one clean place to chat with several AI models."
- **Delivered by:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents
  - `app/components/model-config::ModelConfigList`, matched on named by the model while reading the business documents

## Self-hosted or one-click deploy

Runs as a Next.js web app that can be self-hosted or deployed in one click.

- **Sources:**
  - `business.md`: "It runs as a web app (Next.js) and can be self-hosted or deployed in one click."
- **Delivered by:** _no linked components_

## No database and no sign-in

The app needs no database and no user sign-in to work.

- **Sources:**
  - `business.md`: "No database and no sign-in."
- **Delivered by:** _no linked components_

## Coverage

- **Statements linked to code:** 10 of 14 · rule: 6/7 · usp: 4/7
- **Artifacts reached from the business:** 10 of 524 linkable artifacts in the scan
- **How the links were made:** candidates from names, paths, routes and endpoints in your own code, confirmed by the model.

### Reach by area

- App: 9 of 425
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

### Linked to nothing (4)

- **usp** Lightweight, open-source (MIT) chat interface for LLMs: 3 candidate(s) were offered and the model confirmed none of them.
- **usp** Self-hosted or one-click deploy: The only words that matched a name, path or route are too short to mean one thing (next, web), and a three- or four-letter stem matches by accident across two languages. Something longer has to match the same artifact.
- **usp** No database and no sign-in: The only words that matched a name, path or route are too short to mean one thing (sign, work), and a three- or four-letter stem matches by accident across two languages. Something longer has to match the same artifact.
- **rule** The model API address is configured via BASE_URL, and OpenRouter stands in for OpenAI as the OpenAI-compatible provider.: 1 candidate(s) were offered and the model confirmed none of them.

## Gaps

_None. All material was sourced._
