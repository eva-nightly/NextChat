# Unique selling propositions

_Each USP is sourced to a business document (verbatim) and mapped to the components that deliver it._

## Zero-config AI chat assistant

Sign up and instantly chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek and 100+ top models; the team's own description says no API key is needed, while other material says users bring their own API key or use a hosted endpoint.

- **Sources:**
  - `About_the_organisation.md`: "✨ Zero-config AI chat assistant."
  - `About_the_organisation.md`: "No API key needed — sign up and instantly chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek & 100+ top models."
  - `business.md`: "Users bring an API key or use a hosted endpoint, and chat with many models in one place."
- **Delivered by:**
  - `app/client/platforms/deepseek::DeepSeekApi`, matched on name "seek" in DeepSeekApi; name "deep" in DeepSeekApi; module "claude" in module app/client; +2 more
  - `app/client/platforms/anthropic::ClaudeApi`, matched on name "claude" in ClaudeApi; module "gemini" in module app/client; module "seek" in module app/client; +2 more
  - `app/client/platforms/google::GeminiProApi`, matched on name "gemini" in GeminiProApi; module "claude" in module app/client; module "seek" in module app/client; +2 more
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## One chat interface for many AI models

Users chat with many models in one place instead of juggling separate tools, bringing an API key or using a hosted endpoint.

- **Sources:**
  - `About_the_organisation.md`: "Individuals and small teams who want one chat interface for many AI models, using their own API keys."
  - `business.md`: "Users bring an API key or use a hosted endpoint, and chat with many models in one place."
- **Delivered by:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents
  - `app/components/model-config::ModelConfigList`, matched on named by the model while reading the business documents

## Open-source (MIT) web chat UI for LLMs

NextChat is an MIT-licensed open-source web chat interface for large language models that small teams can self-host for colleagues.

- **Sources:**
  - `business.md`: "NextChat is an open-source (MIT) web chat interface for large language models."
  - `business.md`: "Small teams who self-host it for colleagues."
- **Delivered by:** _no linked components_

## Fast, private chat UI with no account or database

Conversation history stays in the browser; there is no database or sign-in.

- **Sources:**
  - `business.md`: "Individuals who want a fast, private chat UI."
  - `business.md`: "Conversation history stays in the browser; there is no database or sign-in."
- **Delivered by:** _no linked components_

## Streaming answers

Answers stream back token by token.

- **Sources:**
  - `business.md`: "Answers stream back token by token."
- **Delivered by:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## Coverage

- **Statements linked to code:** 6 of 11 · rule: 3/6 · usp: 3/5
- **Artifacts reached from the business:** 6 of 524 linkable artifacts in the scan
- **How the links were made:** candidates from names, paths, routes and endpoints in your own code, confirmed by the model.

### Reach by area

- App: 5 of 425
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

- **usp** Open-source (MIT) web chat UI for LLMs: 1 candidate(s) were offered and the model confirmed none of them.
- **usp** Fast, private chat UI with no account or database: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** The server forwards chat requests to an OpenAI-compatible API configured via BASE_URL.: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** In this deployment BASE_URL points at OpenRouter.: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** Conversation history stays in the browser; there is no database or sign-in.: 1 candidate(s) were offered and the model confirmed none of them.

## Gaps

_None. All material was sourced._
