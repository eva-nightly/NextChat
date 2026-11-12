# Business rules

_Each rule is sourced verbatim, marked verifiable (yes/no), and linked to the components it governs._

### Rule 1

The assistant answers the user's questions clearly and correctly in the chat, stays on topic, and follows the conversation history.

- **Verifiable:** ✅ yes
- **Sources:**
  - `About_the_organisation.md`: "Answers the user's questions clearly and correctly in the chat, stays on topic, follows the conversation history."
  - `nextchat-overview.md`: "Answers are correct, on topic and arrive quickly (first token in a few seconds)."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 2

The user gets a useful answer without having to rephrase.

- **Verifiable:** ❌ no
- **Sources:**
  - `About_the_organisation.md`: "Right means the user gets a useful answer without having to rephrase."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 3

Follow-up questions use the earlier conversation.

- **Verifiable:** ✅ yes
- **Sources:**
  - `nextchat-overview.md`: "Follow-up questions use the earlier conversation."
  - `nextchat-overview.md`: "Conversations keep history; users can set a system prompt ("masks") and switch models."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 4

Answers arrive quickly: first token within a few seconds.

- **Verifiable:** ✅ yes
- **Sources:**
  - `nextchat-overview.md`: "Answers are correct, on topic and arrive quickly (first token in a few seconds)."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 5

Errors from the model provider are shown clearly, not as a blank screen.

- **Verifiable:** ✅ yes
- **Sources:**
  - `nextchat-overview.md`: "Errors from the model provider are shown clearly, not as a blank screen."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 6

The server forwards chat requests to an OpenAI-compatible API (BASE_URL), here OpenRouter.

- **Verifiable:** ✅ yes
- **Sources:**
  - `nextchat-overview.md`: "The server forwards chat requests to an OpenAI-compatible API (BASE_URL), here OpenRouter."
- **Components:** _no linked components_

### Rule 7

No database and no sign-in: sessions live in the browser.

- **Verifiable:** ✅ yes
- **Sources:**
  - `nextchat-overview.md`: "No database and no sign-in: sessions live in the browser."
- **Components:** _no linked components_

### Rule 8

Users can set a system prompt ("masks") and switch models within a conversation.

- **Verifiable:** ✅ yes
- **Sources:**
  - `nextchat-overview.md`: "Conversations keep history; users can set a system prompt ("masks") and switch models."
- **Components:**
  - `app/components/mask::MaskPage`, matched on named by the model while reading the business documents
  - `app/components/model-config::ModelConfigList`, matched on named by the model while reading the business documents
  - `app/components/chat::SessionConfigModel`, matched on named by the model while reading the business documents

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
