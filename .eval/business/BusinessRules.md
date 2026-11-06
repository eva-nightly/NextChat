# Business rules

_Each rule is sourced verbatim, marked verifiable (yes/no), and linked to the components it governs._

### Rule 1

Answers must be relevant, correct and in the user's language.

- **Verifiable:** ❌ no
- **Sources:**
  - `about-nextchat.md`: "Answers must be relevant, correct and in the user's language."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 2

The chat must stay responsive and never lose a conversation.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "The chat must stay responsive and never lose a conversation."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 3

Errors from the model provider must be shown in plain words, not as raw JSON.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "Errors from the model provider must be shown in plain words, not as raw JSON."
- **Components:**
  - `app/components/chat::Chat`, matched on named by the model while reading the business documents

### Rule 4

There is no sign-in and no database; everything is stored on the user's device.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "There is no sign-in and no database; everything is stored on the user's device."
- **Components:** _no linked components_

### Rule 5

Conversations and prompt templates (masks) are kept in the browser.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "Keep conversations and prompt templates ("masks") in the browser."
- **Components:**
  - `app/components/mask::MaskPage`, matched on named by the model while reading the business documents

### Rule 6

The model and API address are user-selectable; in this deployment the API address points to OpenRouter.

- **Verifiable:** ✅ yes
- **Sources:**
  - `about-nextchat.md`: "Choose the model and the API address; in our deployment the address points to OpenRouter."
- **Components:**
  - `app/components/model-config::ModelConfigList`, matched on named by the model while reading the business documents
  - `app/components/settings::Settings`, matched on named by the model while reading the business documents

## Coverage

- **Statements linked to code:** 10 of 12 · rule: 5/6 · usp: 5/6
- **Artifacts reached from the business:** 8 of 524 linkable artifacts in the scan
- **How the links were made:** candidates from names, paths, routes and endpoints in your own code, confirmed by the model.

### Reach by area

- App: 8 of 425
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

### Linked to nothing (2)

- **usp** Open-source (MIT) and self-hostable: 1 candidate(s) were offered and the model confirmed none of them.
- **rule** There is no sign-in and no database; everything is stored on the user's device.: The only words that matched a name, path or route are too short to mean one thing (sign, user), and a three- or four-letter stem matches by accident across two languages. Something longer has to match the same artifact.

## Gaps

_None. All material was sourced._
