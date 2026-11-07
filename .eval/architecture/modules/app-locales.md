# Module: app/locales [AI]

(part 1 of 3) Provides internationalization (i18n) translation dictionaries for the NextChat user interface across multiple languages, including localized strings for authentication, chat sessions, message actions, masks, prompts, system prompts, error states, and sync settings. (part 2 of 3) Provides internationalization (i18n) dictionaries and language management utilities (language detection, persistence, fallback merging, and speech-to-text language mapping) across multiple supported locales. (part 3 of 3) Provides localized UI strings and internationalization dictionaries for Russian (ru), Slovak (sk), Turkish (tr), Traditional Chinese (tw), and Vietnamese (vi) languages across the NextChat application.

_This module does not fit in one model call, so it was read in 3 parts and their summaries were combined without a further model call._

## Key files
- `app/locales/en.ts`: Defines the base English localization dictionary (LocaleType) covering all UI components, actions, settings, and error messages.
- `app/locales/cn.ts`: Defines the Simplified Chinese localization dictionary covering UI elements, shortcuts, prompts, and provider configurations.
- `app/locales/ar.ts`: Defines the Arabic partial localization dictionary.
- `app/locales/bn.ts`: Defines the Bengali partial localization dictionary.
- `app/locales/cs.ts`: Defines the Czech partial localization dictionary.
- `app/locales/da.ts`: Defines the Danish partial localization dictionary.
- `app/locales/de.ts`: Defines the German partial localization dictionary.
- `app/locales/index.ts`: Central i18n coordinator exporting the active merged locale dictionary, language options, detection logic, switch helpers, and STT mappings.
- `app/locales/es.ts`: Spanish localization dictionary definitions.
- `app/locales/fr.ts`: French localization dictionary definitions.
- `app/locales/id.ts`: Indonesian localization dictionary definitions.
- `app/locales/it.ts`: Italian localization dictionary definitions.
- `app/locales/jp.ts`: Japanese localization dictionary definitions.
- `app/locales/ko.ts`: Korean localization dictionary definitions.
- `app/locales/no.ts`: Norwegian localization dictionary definitions.
- `app/locales/pt.ts`: Portuguese localization dictionary definitions.
- `app/locales/ru.ts`: Russian localization dictionary providing UI strings, commands, settings descriptions, and error messages
- `app/locales/sk.ts`: Slovak localization dictionary providing UI strings, commands, settings descriptions, and error messages
- `app/locales/tr.ts`: Turkish localization dictionary providing UI strings, commands, settings descriptions, and error messages
- `app/locales/tw.ts`: Traditional Chinese localization dictionary providing UI strings, commands, settings descriptions, and error messages
- `app/locales/vi.ts`: Vietnamese localization dictionary providing UI strings, commands, settings descriptions, and error messages

## Public interface
- en: LocaleType
- cn: object
- ar: PartialLocaleType
- bn: PartialLocaleType
- cs: PartialLocaleType
- da: PartialLocaleType
- de: PartialLocaleType
- default (LocaleType) - Merged active translation dictionary with English fallback
- export type Lang
- export type LocaleType
- export type PartialLocaleType
- export const AllLangs: Lang[]
- export const ALL_LANG_OPTIONS: Record<Lang, string>
- export function getLang(): Lang
- export function changeLang(lang: Lang): void
- export function getISOLang(): string
- export const STT_LANG_MAP: Record<Lang, string>
- export function getSTTLang(): string
- ru: PartialLocaleType
- sk: PartialLocaleType
- tr: PartialLocaleType
- tw
- vi: PartialLocaleType

## Dependencies
- ../store/config
- ../config/client
- @/app/constant
- ./index
- @/app/utils
- ../utils/merge
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
- `app/locales/index.ts`

## Open questions
- How are these locale objects aggregated and exported by app/locales/index.ts (e.g., dynamically loaded per user preference or statically bundled)?
