# Business rules

_Each rule is sourced verbatim, marked verifiable (yes/no), and linked to the components it governs._

### Rule 1

Answers must be relevant, accurate and complete without errors.

- **Verifiable:** ❌ no
- **Sources:**
  - `About_the_organisation.md`: "Right means the answer is relevant, accurate, and complete without errors."
  - `about-nextchat.md`: "Answers are relevant, accurate and arrive quickly."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 2

The assistant must reply in the user's language.

- **Verifiable:** ✅ yes
- **Sources:**
  - `About_the_organisation.md`: "A chat assistant: users type questions and the AI answers helpfully and correctly, in the user's language, streaming replies."
  - `about-nextchat.md`: "The assistant follows the user's instructions and language."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents
  - `app/constant::DEFAULT_SYSTEM_TEMPLATE`, matched on named by the model while reading the business documents

### Rule 3

Replies must be streamed to the user and arrive quickly.

- **Verifiable:** ✅ yes
- **Sources:**
  - `About_the_organisation.md`: "A chat assistant: users type questions and the AI answers helpfully and correctly, in the user's language, streaming replies."
  - `about-nextchat.md`: "Lets a person chat with an AI assistant in the browser, with streaming answers."
  - `about-nextchat.md`: "Answers are relevant, accurate and arrive quickly."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 4

The assistant must follow the user's instructions.

- **Verifiable:** ❌ no
- **Sources:**
  - `about-nextchat.md`: "The assistant follows the user's instructions and language."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents
  - `app/constant::DEFAULT_SYSTEM_TEMPLATE`, matched on named by the model while reading the business documents

### Rule 5

Errors from the model provider must be shown clearly to the user, never as a blank screen.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "Errors from the model provider are shown clearly, never as a blank screen."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 6

Long conversations must stay coherent.

- **Verifiable:** ❌ no
- **Sources:**
  - `about-nextchat.md`: "Long conversations stay coherent; titles for chats are short and fitting."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 7

Generated chat titles must be short and fitting.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "Long conversations stay coherent; titles for chats are short and fitting."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 8

Conversation history is stored locally in the browser; there is no database and no sign-in.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "Keeps conversation history locally in the browser; there is no database and no sign-in."
- **Components:** _no linked components_

### Rule 9

The model provider is reached through an OpenAI-compatible API whose address is configured with BASE_URL.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "Talks to an OpenAI-compatible API; the address is set with BASE_URL (here: OpenRouter)."
- **Components:** _no linked components_

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
