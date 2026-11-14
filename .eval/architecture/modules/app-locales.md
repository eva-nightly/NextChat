# Module: app/locales [AI]

(part 1 of 3) Provides internationalization (i18n) dictionary objects and UI translation strings across multiple languages (e.g., Arabic, Bengali, Chinese, Czech, Danish, German, English) for chat interactions, authentication, settings, synchronization, masks, and error handling. (part 2 of 3) Manages internationalization (i18n) and UI translations for NextChat, providing localized strings, prompt/mask labels, error messages, language detection, locale switching, and speech-to-text language mappings. (part 3 of 3) Provides localization string dictionaries (Russian, Slovak, Turkish, Traditional Chinese, Vietnamese) for the NextChat user interface, covering chat controls, prompts, masks, error messages, and provider settings.

_This module does not fit in one model call, so it was read in 3 parts and their summaries were combined without a further model call._

## Key files
- `app/locales/en.ts`: Defines the base English locale dictionary implementing the full LocaleType interface.
- `app/locales/cn.ts`: Defines the Simplified Chinese locale dictionary.
- `app/locales/ar.ts`: Defines the Arabic translation dictionary implementing PartialLocaleType.
- `app/locales/bn.ts`: Defines the Bengali translation dictionary implementing PartialLocaleType.
- `app/locales/cs.ts`: Defines the Czech translation dictionary implementing PartialLocaleType.
- `app/locales/da.ts`: Defines the Danish translation dictionary implementing PartialLocaleType.
- `app/locales/de.ts`: Defines the German translation dictionary implementing PartialLocaleType.
- `app/locales/index.ts`: Entry point that aggregates all language dictionaries, performs fallback merging, detects browser language, manages locale selection in localStorage, and exports STT and ISO language utilities.
- `app/locales/es.ts`: Spanish locale dictionary containing UI strings, prompt labels, error messages, and settings texts.
- `app/locales/fr.ts`: French locale dictionary containing UI strings, prompt labels, error messages, and settings texts.
- `app/locales/id.ts`: Indonesian locale dictionary containing UI strings, prompt labels, error messages, and settings texts.
- `app/locales/it.ts`: Italian locale dictionary containing UI strings, prompt labels, error messages, and settings texts.
- `app/locales/jp.ts`: Japanese locale dictionary containing UI strings, prompt labels, error messages, and settings texts.
- `app/locales/ko.ts`: Korean locale dictionary containing UI strings, prompt labels, error messages, and settings texts.
- `app/locales/no.ts`: Norwegian locale dictionary containing UI strings, prompt labels, error messages, and settings texts.
- `app/locales/pt.ts`: Portuguese locale dictionary containing UI strings, prompt labels, error messages, and settings texts.
- `app/locales/ru.ts`: Russian localization dictionary exporting strings for UI elements, error handling, prompts, and configuration.
- `app/locales/sk.ts`: Slovak localization dictionary exporting strings for UI elements, error handling, prompts, and configuration.
- `app/locales/tr.ts`: Turkish localization dictionary exporting strings for UI elements, error handling, prompts, and configuration.
- `app/locales/tw.ts`: Traditional Chinese localization dictionary exporting strings for UI elements, error handling, prompts, and configuration.
- `app/locales/vi.ts`: Vietnamese localization dictionary exporting strings for UI elements, error handling, prompts, and configuration.

## Public interface
- ar (default/named export PartialLocaleType object)
- bn (default/named export PartialLocaleType object)
- cn (default/named export object)
- cs (default/named export PartialLocaleType object)
- da (default/named export PartialLocaleType object)
- de (default/named export PartialLocaleType object)
- en (default/named export LocaleType object)
- default (LocaleType): Active merged locale dictionary
- AllLangs: Array of supported language identifiers
- ALL_LANG_OPTIONS: Record mapping language codes to their native display names
- getLang(): Retrieves the current selected or detected language code
- changeLang(lang: Lang): Updates language in storage and reloads the application
- getISOLang(): Returns the ISO language code for the active locale
- STT_LANG_MAP: Record mapping language codes to Speech-to-Text BCP 47 locale codes
- getSTTLang(): Returns Speech-to-Text language string for current locale
- type Lang
- type LocaleType
- type PartialLocaleType
- ru: PartialLocaleType - Russian locale translation object
- sk: PartialLocaleType - Slovak locale translation object
- tr: PartialLocaleType - Turkish locale translation object
- tw: object - Traditional Chinese locale translation object
- vi: PartialLocaleType - Vietnamese locale translation object

## Dependencies
- app/config/client
- app/constant
- app/locales/index
- app/store/config
- @/app/constant
- @/app/utils
- ../config/client
- ../store/config
- ../utils/merge
- @/app/constant (SAAS_CHAT_UTM_URL)
- app/config/client (getClientConfig)
- app/store/config (SubmitKey)
- app/locales/index (PartialLocaleType)

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
