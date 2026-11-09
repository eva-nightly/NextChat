# Module: app/locales [AI]

(part 1 of 3) Provides internationalization (i18n) translation dictionaries for the NextChat user interface across multiple languages, defining localized text for authentication, chat sessions, prompt templates (masks), system prompt injection, history compression, export options, and settings. (part 2 of 3) Provides internationalization (i18n) dictionary definitions, language detection, locale persistence, and speech-to-text language mapping across 20+ supported languages. (part 3 of 3) Provides localized UI strings, command descriptions, system prompt settings text, and translation dictionaries for Russian (ru), Slovak (sk), Turkish (tr), Traditional Chinese (tw), and Vietnamese (vi).

_This module does not fit in one model call, so it was read in 3 parts and their summaries were combined without a further model call._

## Key files
- `app/locales/en.ts`: Defines the base English translation dictionary adhering to LocaleType.
- `app/locales/cn.ts`: Defines Simplified Chinese translation dictionary strings.
- `app/locales/ar.ts`: Defines Arabic translation dictionary strings implementing PartialLocaleType.
- `app/locales/bn.ts`: Defines Bengali translation dictionary strings implementing PartialLocaleType.
- `app/locales/cs.ts`: Defines Czech translation dictionary strings implementing PartialLocaleType.
- `app/locales/da.ts`: Defines Danish translation dictionary strings implementing PartialLocaleType.
- `app/locales/de.ts`: Defines German translation dictionary strings implementing PartialLocaleType.
- `app/locales/index.ts`: Central i18n coordinator; manages locale loading, fallback merging against English, localStorage persistence, ISO and STT language mapping, and active language switching.
- `app/locales/es.ts`: Spanish UI locale definitions and formatting functions.
- `app/locales/fr.ts`: French UI locale definitions and formatting functions.
- `app/locales/id.ts`: Indonesian UI locale definitions and formatting functions.
- `app/locales/it.ts`: Italian UI locale definitions and formatting functions.
- `app/locales/jp.ts`: Japanese UI locale definitions and formatting functions.
- `app/locales/ko.ts`: Korean UI locale definitions and formatting functions.
- `app/locales/no.ts`: Norwegian UI locale definitions and formatting functions.
- `app/locales/pt.ts`: Portuguese UI locale definitions and formatting functions.
- `app/locales/ru.ts`: Russian localization dictionary covering chat UI, settings, masks, error prompts, and configuration hints.
- `app/locales/sk.ts`: Slovak localization dictionary covering chat UI, settings, masks, error prompts, and configuration hints.
- `app/locales/tr.ts`: Turkish localization dictionary covering chat UI, settings, masks, error prompts, and configuration hints.
- `app/locales/tw.ts`: Traditional Chinese localization dictionary covering chat UI, settings, masks, keyboard shortcuts, and model provider configurations.
- `app/locales/vi.ts`: Vietnamese localization dictionary covering chat UI, settings, masks, error prompts, and configuration hints.

## Public interface
- ar
- bn
- cn
- cs
- da
- de
- en
- default (LocaleType dictionary for the active language merged over English fallback)
- AllLangs: Lang[]
- ALL_LANG_OPTIONS: Record<Lang, string>
- STT_LANG_MAP: Record<Lang, string>
- getLang(): Lang
- changeLang(lang: Lang): void
- getISOLang(): string
- getSTTLang(): string
- type Lang
- type LocaleType
- type PartialLocaleType
- ru: PartialLocaleType
- sk: PartialLocaleType
- tr: PartialLocaleType
- tw: object
- vi: PartialLocaleType

## Dependencies
- ../config/client
- ../store/config
- ./index
- @/app/constant
- @/app/utils
- ../utils/merge
- ./cn
- ../locales/index

## AI touchpoints [AI]
- `app/locales/ar.ts`
- `app/locales/bn.ts`
- `app/locales/cn.ts`
- `app/locales/cs.ts`
- `app/locales/da.ts`
- `app/locales/de.ts`
- `app/locales/en.ts`
- `app/locales/es.ts`
- `app/locales/fr.ts`
- `app/locales/id.ts`
- `app/locales/it.ts`
- `app/locales/jp.ts`
- `app/locales/ko.ts`
- `app/locales/no.ts`
- `app/locales/pt.ts`
- `app/locales/ru.ts`
- `app/locales/sk.ts`
- `app/locales/tr.ts`
- `app/locales/tw.ts`
- `app/locales/vi.ts`

## Open questions
- Locale merging in app/locales/index.ts mutates the static imported 'fallbackLang' (en) object in-place via merge(fallbackLang, targetLang) on module load; dynamic runtime language switches rely on full page reloads via location.reload() rather than reactive React context state.
