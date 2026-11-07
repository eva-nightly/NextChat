# Module: app/masks [AI]

Defines, manages, and bundles builtin prompt presets (masks) in multiple languages (Chinese, Traditional Chinese, English) along with their default model configurations, context prompts, and browser/build loader utilities.

## Key files
- `app/masks/index.ts`: Exports the runtime BUILTIN_MASK_STORE and BUILTIN_MASKS list, and dynamically fetches masks.json when running in the browser.
- `app/masks/build.ts`: Build script that gathers builtin masks from cn, tw, and en language modules and writes them to public/masks.json.
- `app/masks/typing.ts`: Type definition for BuiltinMask based on Mask and ModelConfig.
- `app/masks/cn.ts`: Preset masks collection in Simplified Chinese with system prompts and model parameters.
- `app/masks/tw.ts`: Preset masks collection in Traditional Chinese with system prompts and model parameters.
- `app/masks/en.ts`: Preset masks collection in English with system prompts and model parameters.

## Public interface
- BUILTIN_MASK_ID
- BUILTIN_MASK_STORE
- BUILTIN_MASKS
- BuiltinMask
- CN_MASKS
- TW_MASKS
- EN_MASKS

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
