# Module: app/masks [AI]

Manages and builds the builtin prompt templates (masks) in multiple languages (English, Simplified Chinese, Traditional Chinese) with their associated system contexts and model configurations, and exposes runtime fetching and in-memory storage for builtin masks.

## Key files
- `app/masks/index.ts`: Provides the runtime BUILTIN_MASK_STORE and BUILTIN_MASKS array, fetching /masks.json in browser runtime to initialize available builtin masks.
- `app/masks/typing.ts`: Defines the BuiltinMask type definition extending and customizing the base Mask type.
- `app/masks/build.ts`: Build script that bundles language-specific masks (CN, TW, EN) into the static public/masks.json file.
- `app/masks/en.ts`: Defines default English language prompt templates and model configurations.
- `app/masks/cn.ts`: Defines default Simplified Chinese language prompt templates and model configurations.
- `app/masks/tw.ts`: Defines default Traditional Chinese language prompt templates and model configurations.

## Public interface
- type BuiltinMask
- BUILTIN_MASK_ID
- BUILTIN_MASK_STORE
- BUILTIN_MASKS
- CN_MASKS
- TW_MASKS
- EN_MASKS

## Dependencies
- fs
- path
- ../store
- ../store/mask

## AI touchpoints [AI]
- `app/masks/cn.ts`
- `app/masks/en.ts`
- `app/masks/tw.ts`

## Open questions
- _none_
