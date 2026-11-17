# Business rules

_Each rule is sourced verbatim, marked verifiable (yes/no), and linked to the components it governs._

### Rule 1

Answers must be accurate, helpful, relevant/on-topic and consistent with the conversation.

- **Verifiable:** ❌ no
- **Sources:**
  - `About_the_organisation.md`: "A good answer is accurate, helpful, on-topic, follows the conversation context and the selected model/system prompt, and fails gracefully on errors."
  - `about.md`: "Answers must be accurate, relevant and consistent with the conversation."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 2

Answers must follow the conversation context and the selected model / system prompt (mask).

- **Verifiable:** ✅ yes
- **Sources:**
  - `About_the_organisation.md`: "A good answer is accurate, helpful, on-topic, follows the conversation context and the selected model/system prompt, and fails gracefully on errors."
  - `about.md`: "Users can pick a model and set a system prompt (masks)."
- **Components:**
  - `app/components/mask::ContextPrompts`, matched on name "context" in ContextPrompts; name "prompt" in ContextPrompts; path "mask" in app/components/mask
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents
  - `app/components/mask::MaskConfig`, matched on named by the model while reading the business documents
  - `app/constant::DEFAULT_SYSTEM_TEMPLATE`, matched on named by the model while reading the business documents

### Rule 3

Errors from the API must be explained clearly to the user and fail gracefully — never a blank screen.

- **Verifiable:** ✅ yes
- **Sources:**
  - `About_the_organisation.md`: "A good answer is accurate, helpful, on-topic, follows the conversation context and the selected model/system prompt, and fails gracefully on errors."
  - `about.md`: "Errors from the API must be explained clearly, never a blank screen."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 4

The app answers through an OpenAI-compatible API; the deployed endpoint is OpenRouter, set through BASE_URL.

- **Verifiable:** ✅ yes
- **Sources:**
  - `About_the_organisation.md`: "A chat assistant that answers user questions through an OpenAI-compatible API (OpenRouter)."
  - `about.md`: "In our deployment the endpoint is OpenRouter, set through BASE_URL."
- **Components:** _no linked components_

### Rule 5

No database and no sign-in: chats stay in the browser.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about.md`: "No database and no sign-in: chats stay in the browser."
- **Components:** _no linked components_

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
