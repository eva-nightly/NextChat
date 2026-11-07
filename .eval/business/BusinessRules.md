# Business rules

_Each rule is sourced verbatim, marked verifiable (yes/no), and linked to the components it governs._

### Rule 1

Answers must be relevant, accurate and honest about uncertainty.

- **Verifiable:** ❌ no
- **Sources:**
  - `about-nextchat.md`: "Answers are relevant, accurate and honest about uncertainty."
- **Components:**
  - `app/constant::DEFAULT_SYSTEM_TEMPLATE`, matched on named by the model while reading the business documents

### Rule 2

Streaming must be quick and errors must be explained plainly to the user.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "Streaming is quick and errors are explained plainly."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 3

No database and no sign-in: conversations must stay in the browser.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "No database and no sign-in: conversations stay in the browser."
- **Components:** _no linked components_

### Rule 4

Users bring their own API key, or the app is pointed at an OpenAI-compatible endpoint through BASE_URL.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "Users bring their own API key, or point the app at an OpenAI-compatible endpoint through BASE_URL."
- **Components:**
  - `app/components/auth::AuthPage`, matched on named by the model while reading the business documents

### Rule 5

In this deployment the endpoint is OpenRouter, standing in for OpenAI.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "In our deployment the endpoint is OpenRouter, which stands in for OpenAI."
- **Components:** _no linked components_

### Rule 6

Long chats are summarised so the conversation stays within the context window.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "Conversation summaries that keep long chats within the context window."
- **Components:** _no linked components_

## Coverage

- **Statements linked to code:** 9 of 15 · rule: 3/6 · usp: 6/9
- **Artifacts reached from the business:** 11 of 524 linkable artifacts in the scan
- **How the links were made:** candidates from names, paths, routes and endpoints in your own code, confirmed by the model.

### Reach by area

- App: 10 of 425
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

### Linked to nothing (6)

- **usp** Private by design: no database, no sign-in: 3 candidate(s) were offered and the model confirmed none of them.
- **usp** Open-source (MIT) web chat interface: 1 candidate(s) were offered and the model confirmed none of them.
- **usp** Conversation summaries keep long chats within the context window: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** No database and no sign-in: conversations must stay in the browser.: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** In this deployment the endpoint is OpenRouter, standing in for OpenAI.: No artifact NAME, path, route or endpoint in the codebase matches any word in it. It may be a rule about how people work rather than about what the product does.
- **rule** Long chats are summarised so the conversation stays within the context window.: 1 candidate(s) were offered and the model confirmed none of them.

## Gaps

_None. All material was sourced._
