# Module: app/locales [AI]

(part 1 of 3) Provides localization dictionary definitions and multilingual UI strings (such as chat actions, authentication prompts, settings, masks, conversation summaries, and synchronization configuration) for multiple languages across the NextChat application. (part 2 of 3) Manages internationalization (i18n) dictionaries and locale resolution for the NextChat application, providing multilingual UI translations, browser language detection, localStorage persistence, fallback dictionary merging, and speech-to-text (STT) locale mappings. (part 3 of 3) Provides localization dictionary definitions and UI translation strings for Russian (ru), Slovak (sk), Turkish (tr), Traditional Chinese (tw), and Vietnamese (vi), covering chat interfaces, model configurations, memory compression, system prompts, authentication, and cloud sync settings.

_This module does not fit in one model call, so it was read in 3 parts and their summaries were combined without a further model call._

## Key files
- `app/locales/en.ts`: Defines the base English translation dictionary adhering to LocaleType.
- `app/locales/cn.ts`: Defines the Simplified Chinese translation dictionary for the application UI.
- `app/locales/ar.ts`: Defines the Arabic translation dictionary (PartialLocaleType).
- `app/locales/bn.ts`: Defines the Bengali translation dictionary (PartialLocaleType).
- `app/locales/cs.ts`: Defines the Czech translation dictionary (PartialLocaleType).
- `app/locales/da.ts`: Defines the Danish translation dictionary (PartialLocaleType).
- `app/locales/de.ts`: Defines the German translation dictionary (PartialLocaleType).
- `app/locales/index.ts`: Entrypoint for localization system: aggregates all language packs, provides fallback merging into English, exports language utilities (getLang, changeLang, getISOLang, getSTTLang), and defines STT locale mappings.
- `app/locales/es.ts`: Spanish language dictionary containing translated UI strings for auth, chat, export, settings, prompts, and error dialogs.
- `app/locales/fr.ts`: French language dictionary containing translated UI strings.
- `app/locales/id.ts`: Indonesian language dictionary containing translated UI strings.
- `app/locales/it.ts`: Italian language dictionary containing translated UI strings.
- `app/locales/jp.ts`: Japanese language dictionary containing translated UI strings.
- `app/locales/ko.ts`: Korean language dictionary containing translated UI strings.
- `app/locales/no.ts`: Norwegian (Nynorsk) language dictionary containing translated UI strings.
- `app/locales/pt.ts`: Portuguese language dictionary containing translated UI strings.
- `app/locales/ru.ts`: Russian localization dictionary conforming to PartialLocaleType
- `app/locales/sk.ts`: Slovak localization dictionary conforming to PartialLocaleType
- `app/locales/tr.ts`: Turkish localization dictionary conforming to PartialLocaleType
- `app/locales/tw.ts`: Traditional Chinese localization dictionary
- `app/locales/vi.ts`: Vietnamese localization dictionary conforming to PartialLocaleType

## Public interface
- default export / locale dictionary constants conforming to LocaleType or PartialLocaleType (e.g., en, cn, ar, bn, cs, da, de)
- default: LocaleType (merged fallback/target locale dictionary)
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
- ../store/config (SubmitKey)
- ../locales/index (PartialLocaleType)
- ./index (PartialLocaleType)
- ../config/client (getClientConfig)
- @/app/constant (SAAS_CHAT_UTM_URL)

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
