# Module: app/masks [AI]

Defines, manages, and builds built-in system prompts and persona configurations ('masks') for different languages (Chinese, Traditional Chinese, English) along with their default model settings.

## Key files
- `app/masks/index.ts`: Client-side store and fetch loader for built-in masks from /masks.json
- `app/masks/build.ts`: Node script that compiles localized masks (CN, TW, EN) into public/masks.json
- `app/masks/typing.ts`: TypeScript types for BuiltinMask data structures
- `app/masks/cn.ts`: Built-in mask definitions and system prompts in Simplified Chinese
- `app/masks/tw.ts`: Built-in mask definitions and system prompts in Traditional Chinese
- `app/masks/en.ts`: Built-in mask definitions and system prompts in English

## Public interface
- BUILTIN_MASK_ID
- BUILTIN_MASK_STORE
- BUILTIN_MASKS
- CN_MASKS
- TW_MASKS
- EN_MASKS
- type BuiltinMask

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
