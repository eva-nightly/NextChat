# Business rules

_Each rule is sourced verbatim, marked verifiable (yes/no), and linked to the components it governs._

### Rule 1

The server forwards chat requests to an OpenAI-compatible API configured via BASE_URL.

- **Verifiable:** ✅ yes
- **Sources:**
  - `business.md`: "The server forwards chat requests to an OpenAI-compatible API (BASE_URL)."
- **Components:** _no linked components_

### Rule 2

In this deployment BASE_URL points at OpenRouter.

- **Verifiable:** ✅ yes
- **Sources:**
  - `business.md`: "In our deployment BASE_URL points at OpenRouter."
- **Components:** _no linked components_

### Rule 3

Answers must stream back to the user token by token.

- **Verifiable:** ✅ yes
- **Sources:**
  - `business.md`: "Answers stream back token by token."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 4

Answers should be helpful, correct and in the user's language.

- **Verifiable:** ❌ no
- **Sources:**
  - `business.md`: "Answers should be helpful, correct and in the user's language."
- **Components:**
  - `app/constant::DEFAULT_SYSTEM_TEMPLATE`, matched on named by the model while reading the business documents

### Rule 5

Errors such as a bad key or rate limit must be explained clearly to the user, never shown as a blank screen.

- **Verifiable:** ✅ yes
- **Sources:**
  - `business.md`: "Errors (bad key, rate limit) should be explained clearly, never a blank screen."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 6

Conversation history stays in the browser; there is no database or sign-in.

- **Verifiable:** ✅ yes
- **Sources:**
  - `business.md`: "Conversation history stays in the browser; there is no database or sign-in."
- **Components:** _no linked components_

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
