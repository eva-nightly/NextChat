# Module: app/locales [AI]

(part 1 of 3) Provides internationalization (i18n) translation dictionaries and UI strings for multiple languages across all NextChat interface features, including chat controls, settings, authentication, prompt templates (masks), memory summaries, and model configuration. (part 2 of 3) Provides internationalization (i18n) translation dictionaries and locale management utilities for NextChat UI strings, error notices, chat action prompts, settings, speech-to-text (STT) language mappings, and client language detection. (part 3 of 3) Provides internationalization dictionary objects for Russian (ru), Slovak (sk), Turkish (tr), Traditional Chinese (tw), and Vietnamese (vi), defining UI labels, commands, settings, error messages, and system prompt UI strings.

_This module does not fit in one model call, so it was read in 3 parts and their summaries were combined without a further model call._

## Key files
- `app/locales/en.ts`: Base English translation dictionary defining full LocaleType mappings for UI text and error messages
- `app/locales/cn.ts`: Simplified Chinese translation dictionary containing localized strings for chat features, masks, and configuration
- `app/locales/ar.ts`: Arabic translation dictionary implementing PartialLocaleType
- `app/locales/bn.ts`: Bengali translation dictionary implementing PartialLocaleType
- `app/locales/cs.ts`: Czech translation dictionary implementing PartialLocaleType
- `app/locales/da.ts`: Danish translation dictionary implementing PartialLocaleType
- `app/locales/de.ts`: German translation dictionary implementing PartialLocaleType
- `app/locales/index.ts`: Central i18n module that registers all supported languages, manages active language state in local storage, handles fallback merging against English, and provides utilities for language selection and STT code mapping.
- `app/locales/es.ts`: Spanish localization dictionary implementing PartialLocaleType.
- `app/locales/fr.ts`: French localization dictionary implementing PartialLocaleType.
- `app/locales/id.ts`: Indonesian localization dictionary implementing PartialLocaleType.
- `app/locales/it.ts`: Italian localization dictionary implementing PartialLocaleType.
- `app/locales/jp.ts`: Japanese localization dictionary implementing PartialLocaleType.
- `app/locales/ko.ts`: Korean localization dictionary implementing PartialLocaleType.
- `app/locales/no.ts`: Norwegian localization dictionary implementing PartialLocaleType.
- `app/locales/pt.ts`: Portuguese localization dictionary implementing PartialLocaleType.
- `app/locales/ru.ts`: Russian locale dictionary implementing PartialLocaleType
- `app/locales/sk.ts`: Slovak locale dictionary implementing PartialLocaleType
- `app/locales/tr.ts`: Turkish locale dictionary implementing PartialLocaleType
- `app/locales/tw.ts`: Traditional Chinese locale dictionary
- `app/locales/vi.ts`: Vietnamese locale dictionary implementing PartialLocaleType

## Public interface
- LocaleType / PartialLocaleType dictionary objects (exported as default or named locale mappings in ar, bn, cn, cs, da, de, en)
- export default fallbackLang: LocaleType
- export type Lang
- export type LocaleType
- export type PartialLocaleType
- export const AllLangs: Lang[]
- export const ALL_LANG_OPTIONS: Record<Lang, string>
- export const STT_LANG_MAP: Record<Lang, string>
- export function getLang(): Lang
- export function changeLang(lang: Lang): void
- export function getISOLang(): string
- export function getSTTLang(): string
- ru: PartialLocaleType
- sk: PartialLocaleType
- tr: PartialLocaleType
- tw
- vi: PartialLocaleType

## Dependencies
- @/app/constant
- ../config/client
- ../store/config
- ../utils/merge
- @/app/utils
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
- How does the index/loader module dynamically select and merge fallback dictionaries from PartialLocaleType into LocaleType?
