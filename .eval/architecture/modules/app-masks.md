# Module: app/masks [AI]

Manages multilingual builtin prompt templates (masks) for LLM conversations, providing prompt definitions (CN, TW, EN), a build script to serialize them to a public JSON file, and client-side runtime loading and caching into a builtin mask store.

## Key files
- `app/masks/typing.ts`: Defines the BuiltinMask type extending the base Mask interface with builtin metadata and partial model configuration.
- `app/masks/index.ts`: Provides the in-memory BUILTIN_MASK_STORE and BUILTIN_MASKS array, and fetches masks from /masks.json in browser environments.
- `app/masks/build.ts`: Build script that compiles CN, TW, and EN mask arrays and writes public/masks.json.
- `app/masks/cn.ts`: Contains builtin prompt templates, context history, and default model configs in Simplified Chinese.
- `app/masks/en.ts`: Contains builtin prompt templates, context history, and default model configs in English.
- `app/masks/tw.ts`: Contains builtin prompt templates, context history, and default model configs in Traditional Chinese.

## Public interface
- type BuiltinMask
- BUILTIN_MASK_ID
- BUILTIN_MASK_STORE
- BUILTIN_MASKS
- CN_MASKS
- EN_MASKS
- TW_MASKS

## Dependencies
- fs
- path
- app/store
- app/store/mask

## AI touchpoints [AI]
- `app/masks/cn.ts`
- `app/masks/en.ts`
- `app/masks/tw.ts`

## Open questions
- _none_
