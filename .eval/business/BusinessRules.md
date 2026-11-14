# Business rules

_Each rule is sourced verbatim, marked verifiable (yes/no), and linked to the components it governs._

### Rule 1

AI answers must be correct and relevant to the user's question.

- **Verifiable:** ✅ yes
- **Sources:**
  - `About_the_organisation.md`: "A good answer is correct, relevant to the question, concise, in the user's language, and streams without errors or cut-offs."
  - `business.md`: "Answers are correct, relevant and in the user's language."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents
  - `app/constant::DEFAULT_SYSTEM_TEMPLATE`, matched on named by the model while reading the business documents

### Rule 2

AI answers must be in the user's language.

- **Verifiable:** ✅ yes
- **Sources:**
  - `About_the_organisation.md`: "A good answer is correct, relevant to the question, concise, in the user's language, and streams without errors or cut-offs."
  - `business.md`: "Answers are correct, relevant and in the user's language."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents
  - `app/constant::DEFAULT_SYSTEM_TEMPLATE`, matched on named by the model while reading the business documents

### Rule 3

AI answers must be concise.

- **Verifiable:** ✅ yes
- **Sources:**
  - `About_the_organisation.md`: "A good answer is correct, relevant to the question, concise, in the user's language, and streams without errors or cut-offs."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents
  - `app/constant::DEFAULT_SYSTEM_TEMPLATE`, matched on named by the model while reading the business documents

### Rule 4

Streaming must never freeze or cut off; answers stream without errors.

- **Verifiable:** ✅ yes
- **Sources:**
  - `About_the_organisation.md`: "A good answer is correct, relevant to the question, concise, in the user's language, and streams without errors or cut-offs."
  - `business.md`: "Streaming never freezes or cuts off."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 5

Errors from the model provider must be explained to the user in plain words.

- **Verifiable:** ✅ yes
- **Sources:**
  - `business.md`: "Errors from the model provider are explained in plain words."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 6

Chat sessions and history are stored in the browser; there is no database and no sign-in.

- **Verifiable:** ✅ yes
- **Sources:**
  - `business.md`: "Chat sessions with history, stored in the browser."
  - `business.md`: "No database and no sign-in."
- **Components:**
  - `app/store/chat::createEmptySession`, matched on name "session" in createEmptySession; path "chat" in app/store/chat; module "history" in module app/store; +1 more

### Rule 7

The model API address is configured via BASE_URL, and OpenRouter stands in for OpenAI as the OpenAI-compatible provider.

- **Verifiable:** ✅ yes
- **Sources:**
  - `business.md`: "Streaming answers from any OpenAI-compatible API; here the address is BASE_URL and OpenRouter stands in for OpenAI."
- **Components:** _no linked components_

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
