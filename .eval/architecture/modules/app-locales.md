# Module: app/locales [AI]

(part 1 of 3) Provides multilingual localization dictionaries and UI string translations across various languages (Arabic, Bengali, Chinese, Czech, Danish, German, English, etc.) for NextChat's interface, settings, sync options, error messages, and prompt/mask features. (part 2 of 3) Provides internationalization (i18n) definitions, translation dictionaries, language detection, locale switching, and Speech-to-Text (STT) language mapping for the chat interface. (part 3 of 3) Provides localization (i18n) translation dictionaries for Russian, Slovak, Turkish, Traditional Chinese, and Vietnamese across UI components, settings, masks, and error handling.

_This module does not fit in one model call, so it was read in 3 parts and their summaries were combined without a further model call._

## Key files
- `app/locales/en.ts`: Defines the base English localization dictionary implementing LocaleType for all UI components, actions, settings, and error messages.
- `app/locales/cn.ts`: Defines Simplified Chinese localization dictionary entries for UI components, settings, and commands.
- `app/locales/ar.ts`: Defines Arabic partial localization dictionary entries.
- `app/locales/bn.ts`: Defines Bengali partial localization dictionary entries.
- `app/locales/cs.ts`: Defines Czech partial localization dictionary entries.
- `app/locales/da.ts`: Defines Danish partial localization dictionary entries.
- `app/locales/de.ts`: Defines German partial localization dictionary entries.
- `app/locales/index.ts`: Core i18n manager that detects browser locale, persists language preferences to localStorage, merges active language dictionaries onto the English fallback, and exports language switcher utilities and STT language mappings.
- `app/locales/es.ts`: Spanish language translations for UI elements, prompts, error states, and settings.
- `app/locales/fr.ts`: French language translations for UI elements, prompts, error states, and settings.
- `app/locales/id.ts`: Indonesian language translations for UI elements, prompts, error states, and settings.
- `app/locales/it.ts`: Italian language translations for UI elements, prompts, error states, and settings.
- `app/locales/jp.ts`: Japanese language translations for UI elements, prompts, error states, and settings.
- `app/locales/ko.ts`: Korean language translations for UI elements, prompts, error states, and settings.
- `app/locales/no.ts`: Norwegian language translations for UI elements, prompts, error states, and settings.
- `app/locales/pt.ts`: Portuguese language translations for UI elements, prompts, error states, and settings.
- `app/locales/ru.ts`: Russian localization dictionary mapping UI labels, prompt/mask strings, and configuration texts
- `app/locales/sk.ts`: Slovak localization dictionary mapping UI labels, prompt/mask strings, and configuration texts
- `app/locales/tr.ts`: Turkish localization dictionary mapping UI labels, prompt/mask strings, and configuration texts
- `app/locales/tw.ts`: Traditional Chinese localization dictionary mapping UI labels, prompt/mask strings, and configuration texts
- `app/locales/vi.ts`: Vietnamese localization dictionary mapping UI labels, prompt/mask strings, and configuration texts

## Public interface
- en
- cn
- ar
- bn
- cs
- da
- de
- default (LocaleType dictionary merged with fallback)
- type Lang
- type LocaleType
- type PartialLocaleType
- AllLangs: Lang[]
- ALL_LANG_OPTIONS: Record<Lang, string>
- STT_LANG_MAP: Record<Lang, string>
- getLang(): Lang
- changeLang(lang: Lang): void
- getISOLang(): string
- getSTTLang(): string
- ru
- sk
- tr
- tw
- vi

## Dependencies
- ../store/config
- ../config/client
- @/app/constant
- ./index
- @/app/utils
- ../utils/merge
- app/store/config
- app/config/client
- app/locales/index

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
- `app/locales/index.ts`

## Open questions
- How does the unprovided index file (app/locales/index.ts) merge and fall back between PartialLocaleType entries and the default LocaleType dictionary?
- Locale merging executes eagerly at module load time (merge(fallbackLang, targetLang)); how is dynamic switching handled on SSR or edge runtimes prior to client reload?
