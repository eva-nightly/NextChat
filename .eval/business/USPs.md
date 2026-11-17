# Unique selling propositions

_Each USP is sourced to a business document (verbatim) and mapped to the components that deliver it._

## Zero-config AI chat assistant

Sign up and instantly chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek and 100+ top models without needing an API key.

- **Sources:**
  - `About_the_organisation.md`: "✨ Zero-config AI chat assistant."
  - `About_the_organisation.md`: "No API key needed — sign up and instantly chat with GPT-5, Claude 4, Gemini 2.5, DeepSeek & 100+ top models."
- **Delivered by:**
  - `app/client/platforms/deepseek::DeepSeekApi`, matched on name "seek" in DeepSeekApi; name "deep" in DeepSeekApi; module "claude" in module app/client; +2 more
  - `app/client/platforms/anthropic::ClaudeApi`, matched on name "claude" in ClaudeApi; module "gemini" in module app/client; module "gpt" in module app/client; +2 more
  - `app/client/platforms/google::GeminiProApi`, matched on name "gemini" in GeminiProApi; module "claude" in module app/client; module "gpt" in module app/client; +2 more
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

## Works with any OpenAI-compatible endpoint

Users bring their own API access; the app talks to any OpenAI-compatible endpoint. In this deployment the endpoint is OpenRouter, configured via BASE_URL.

- **Sources:**
  - `About_the_organisation.md`: "A chat assistant that answers user questions through an OpenAI-compatible API (OpenRouter)."
  - `about.md`: "Users bring their own API access; the app talks to any OpenAI-compatible endpoint."
  - `about.md`: "In our deployment the endpoint is OpenRouter, set through BASE_URL."
- **Delivered by:** _no linked components_

## Private and self-hosted, no database and no sign-in

A private, self-hosted chat UI where chats stay in the browser — there is no database and no sign-in.

- **Sources:**
  - `About_the_organisation.md`: "Developers and hobbyists who want a private, self-hosted chat UI for LLMs."
  - `about.md`: "Developers, hobbyists and small teams who want a fast, private chat UI."
  - `about.md`: "No database and no sign-in: chats stay in the browser."
- **Delivered by:** _no linked components_

## Open-source (MIT) web chat interface for LLMs

NextChat is an open-source, MIT-licensed web chat interface for large language models.

- **Sources:**
  - `about.md`: "NextChat is an open-source (MIT) web chat interface for large language models."
- **Delivered by:** _no linked components_

## Model selection and system prompts (masks)

Users can pick a model and set a system prompt, called a mask.

- **Sources:**
  - `about.md`: "Users can pick a model and set a system prompt (masks)."
- **Delivered by:**
  - `app/components/mask::MaskPage`, matched on named by the model while reading the business documents
  - `app/components/mask::MaskConfig`, matched on named by the model while reading the business documents
  - `app/components/model-config::ModelConfigList`, matched on named by the model while reading the business documents
  - `app/components/chat::SessionConfigModel`, matched on named by the model while reading the business documents

## Coverage

- **Statements linked to code:** 5 of 10 · rule: 3/5 · usp: 2/5
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

### Linked to nothing (5)

- **usp** Works with any OpenAI-compatible endpoint: 1 candidate(s) were offered and the model confirmed none of them.
- **usp** Private and self-hosted, no database and no sign-in: The only words that matched a name, path or route are too short to mean one thing (chat, sign), and a three- or four-letter stem matches by accident across two languages. Something longer has to match the same artifact.
- **usp** Open-source (MIT) web chat interface for LLMs: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** The app answers through an OpenAI-compatible API; the deployed endpoint is OpenRouter, set through BASE_URL.: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** No database and no sign-in: chats stay in the browser.: The only words that matched a name, path or route are too short to mean one thing (chat, sign), and a three- or four-letter stem matches by accident across two languages. Something longer has to match the same artifact.

## Gaps

_None. All material was sourced._
