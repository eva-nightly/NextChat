# Business rules

_Each rule is sourced verbatim, marked verifiable (yes/no), and linked to the components it governs._

### Rule 1

Answers must be correct, relevant, on-topic, and in the user's language.

- **Verifiable:** ✅ yes
- **Sources:**
  - `About_the_organisation.md`: "A good answer is correct, relevant, on-topic, in the user's language, and the chat never errors or hangs."
  - `about-nextchat.md`: "Answers are relevant, correct and in the language of the user."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 2

The chat must never hang or show raw errors; failures must tell the user what to do next.

- **Verifiable:** ✅ yes
- **Sources:**
  - `About_the_organisation.md`: "A good answer is correct, relevant, on-topic, in the user's language, and the chat never errors or hangs."
  - `about-nextchat.md`: "The chat never hangs or shows raw errors; failures say what to do next."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 3

Messages are relayed to an OpenAI-compatible API (OpenRouter), configured via BASE_URL.

- **Verifiable:** ✅ yes
- **Sources:**
  - `About_the_organisation.md`: "It is a chat assistant: it relays the user's messages to an OpenAI-compatible model (via OpenRouter) and streams back answers."
  - `about-nextchat.md`: "Streams answers from an OpenAI-compatible API (here OpenRouter, set via BASE_URL)."
- **Components:** _no linked components_

### Rule 4

The first message must get an answer within a few seconds.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "First message gets an answer in a few seconds."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 5

Conversation history is stored locally in the browser; there is no database or sign-in.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "Keeps conversation history locally in the browser; there is no database or sign-in."
- **Components:** _no linked components_

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
