# Module: app/locales [AI]

(part 1 of 3) Provides internationalization (i18n) localization strings and translation dictionaries across multiple languages for UI elements, error messages, settings, masks, prompt management, and chat interactions. (part 2 of 3) Provides internationalization (i18n) and localization dictionary bundles across multiple languages for the NextChat UI, managing language detection, persistent user language preferences, and speech-to-text (STT) language code mappings. (part 3 of 3) Provides localized UI strings, command descriptions, system prompt settings labels, and error messages for Russian (ru), Slovak (sk), Turkish (tr), Traditional Chinese (tw), and Vietnamese (vi) languages in NextChat.

_This module does not fit in one model call, so it was read in 3 parts and their summaries were combined without a further model call._

## Key files
- `app/locales/en.ts`: Canonical English localization dictionary defining all UI strings, action labels, and settings descriptions.
- `app/locales/cn.ts`: Simplified Chinese localization dictionary.
- `app/locales/ar.ts`: Arabic localization dictionary.
- `app/locales/bn.ts`: Bengali localization dictionary.
- `app/locales/cs.ts`: Czech localization dictionary.
- `app/locales/da.ts`: Danish localization dictionary.
- `app/locales/de.ts`: German localization dictionary.
- `app/locales/index.ts`: Central i18n hub that resolves active locale via localStorage or browser navigator, merges selected translations with English fallbacks, and exports STT language mappings and language switching functions.
- `app/locales/es.ts`: Spanish language locale definitions and UI text dictionary.
- `app/locales/fr.ts`: French language locale definitions and UI text dictionary.
- `app/locales/id.ts`: Indonesian language locale definitions and UI text dictionary.
- `app/locales/it.ts`: Italian language locale definitions and UI text dictionary.
- `app/locales/jp.ts`: Japanese language locale definitions and UI text dictionary.
- `app/locales/ko.ts`: Korean language locale definitions and UI text dictionary.
- `app/locales/no.ts`: Norwegian language locale definitions and UI text dictionary.
- `app/locales/pt.ts`: Portuguese language locale definitions and UI text dictionary.
- `app/locales/ru.ts`: Russian localization dictionary covering chat UI, mask/prompt settings, cloud sync, authentication, and error messages.
- `app/locales/sk.ts`: Slovak localization dictionary covering chat UI, mask/prompt settings, cloud sync, authentication, and error messages.
- `app/locales/tr.ts`: Turkish localization dictionary covering chat UI, mask/prompt settings, cloud sync, authentication, and error messages.
- `app/locales/tw.ts`: Traditional Chinese localization dictionary covering chat UI, mask/prompt settings, cloud sync, provider settings, and keyboard shortcuts.
- `app/locales/vi.ts`: Vietnamese localization dictionary covering chat UI, mask/prompt settings, cloud sync, authentication, and error messages.

## Public interface
- export default ar
- export default bn
- export default cn
- export default cs
- export default da
- export default de
- export default en
- export type { LocaleType, PartialLocaleType } from './cn'
- export type Lang
- export const AllLangs: Lang[]
- export const ALL_LANG_OPTIONS: Record<Lang, string>
- export default fallbackLang: LocaleType
- export function getLang(): Lang
- export function changeLang(lang: Lang): void
- export function getISOLang(): string
- export const STT_LANG_MAP: Record<Lang, string>
- export function getSTTLang(): string
- ru: PartialLocaleType
- sk: PartialLocaleType
- tr: PartialLocaleType
- tw: object
- vi: PartialLocaleType

## Dependencies
- app/store/config
- app/config/client
- @/app/constant
- app/locales/index
- ../store/config
- ../config/client
- ../utils/merge
- @/app/utils
- ./cn
- ./en
- ./tw
- ./pt
- ./da
- ./jp
- ./ko
- ./id
- ./fr
- ./es
- ./it
- ./tr
- ./de
- ./vi
- ./ru
- ./cs
- ./no
- ./ar
- ./bn
- ./sk
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
- _none_
