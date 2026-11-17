# Module: app/locales [AI]

(part 1 of 3) Provides localized UI strings, command labels, settings definitions, and error messages for multiple languages (including Arabic, Bengali, Chinese, Czech, Danish, German, and English). (part 2 of 3) Provides internationalization (i18n) dictionaries, browser language detection, language selection persistence, fallback merging, and speech-to-text (STT) language code mappings for the NextChat UI. (part 3 of 3) Provides localized UI strings and dictionary translations for Russian (ru), Slovak (sk), Turkish (tr), Traditional Chinese (tw), and Vietnamese (vi), covering chat actions, auth, mask/system prompt management, export, sync, and settings.

_This module does not fit in one model call, so it was read in 3 parts and their summaries were combined without a further model call._

## Key files
- `app/locales/en.ts`: Defines the base English translation schema (LocaleType) for UI components, settings, masks, and prompts.
- `app/locales/cn.ts`: Defines Simplified Chinese translations.
- `app/locales/ar.ts`: Defines Arabic translations.
- `app/locales/bn.ts`: Defines Bengali translations.
- `app/locales/cs.ts`: Defines Czech translations.
- `app/locales/da.ts`: Defines Danish translations.
- `app/locales/de.ts`: Defines German translations.
- `app/locales/index.ts`: Central i18n controller that aggregates all language packs, detects user language from browser settings or localStorage, merges missing keys with English fallbacks, and exports locale switching helpers and STT language mappings.
- `app/locales/es.ts`: Spanish localization dictionary covering authentication, chat interface, prompt actions, export, memory compression, and settings.
- `app/locales/fr.ts`: French localization dictionary covering interface actions, settings, and modal prompts.
- `app/locales/id.ts`: Indonesian localization dictionary covering UI labels, configuration options, and action prompts.
- `app/locales/it.ts`: Italian localization dictionary covering UI labels, settings, sync options, and error messages.
- `app/locales/jp.ts`: Japanese localization dictionary covering chat operations, masks, prompts, and settings.
- `app/locales/ko.ts`: Korean localization dictionary covering chat UI, shortcuts, masks, settings, and sync configuration.
- `app/locales/no.ts`: Norwegian localization dictionary for user interactions, messages, and configurations.
- `app/locales/pt.ts`: Portuguese localization dictionary for chat interactions, system settings, and memory prompts.
- `app/locales/ru.ts`: Russian localization dictionary mapping UI labels, command shortcuts, settings, and error messages
- `app/locales/sk.ts`: Slovak localization dictionary mapping UI labels, command shortcuts, settings, and error messages
- `app/locales/tr.ts`: Turkish localization dictionary mapping UI labels, command shortcuts, settings, and error messages
- `app/locales/tw.ts`: Traditional Chinese localization dictionary mapping UI labels, command shortcuts, settings, and error messages
- `app/locales/vi.ts`: Vietnamese localization dictionary mapping UI labels, command shortcuts, settings, and error messages

## Public interface
- ar
- bn
- cn
- cs
- da
- de
- en
- default (LocaleType dictionary merged with fallback)
- type LocaleType
- type PartialLocaleType
- type Lang
- AllLangs: Lang[]
- ALL_LANG_OPTIONS: Record<Lang, string>
- STT_LANG_MAP: Record<Lang, string>
- getLang(): Lang
- changeLang(lang: Lang): void
- getISOLang(): string
- getSTTLang(): string
- ru: PartialLocaleType
- sk: PartialLocaleType
- tr: PartialLocaleType
- tw: PartialLocaleType
- vi: PartialLocaleType

## Dependencies
- @/app/constant
- ../config/client
- ../store/config
- ./index
- ../utils/merge
- @/app/utils
- app/store/config
- app/locales/index
- app/config/client

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
- _none_
