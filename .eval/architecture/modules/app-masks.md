# Module: app/masks [AI]

Defines built-in prompt presets (masks) in multiple languages (English, Simplified Chinese, Traditional Chinese) and provides utilities to build masks.json and fetch/store built-in masks at runtime.

## Key files
- `app/masks/index.ts`: Exports the built-in mask storage manager BUILTIN_MASK_STORE, the initial mask ID offset, and handles browser-side fetching of /masks.json into BUILTIN_MASKS.
- `app/masks/build.ts`: Build script bundling language-specific mask collections (CN_MASKS, TW_MASKS, EN_MASKS) into public/masks.json.
- `app/masks/typing.ts`: TypeScript type definition for BuiltinMask extending store/mask Mask and store ModelConfig.
- `app/masks/cn.ts`: Built-in prompt templates and system configurations in Simplified Chinese.
- `app/masks/en.ts`: Built-in prompt templates and system configurations in English.
- `app/masks/tw.ts`: Built-in prompt templates and system configurations in Traditional Chinese.

## Public interface
- BUILTIN_MASK_ID: number constant (100000)
- BUILTIN_MASK_STORE: object with methods get(id?: string) and add(m: BuiltinMask)
- BUILTIN_MASKS: BuiltinMask[] array populated at runtime in the browser
- CN_MASKS: BuiltinMask[]
- TW_MASKS: BuiltinMask[]
- EN_MASKS: BuiltinMask[]
- type BuiltinMask

## Dependencies
- fs
- path
- ../store/mask
- ../store

## AI touchpoints [AI]
- `app/masks/cn.ts`
- `app/masks/en.ts`
- `app/masks/tw.ts`

## Open questions
- _none_
