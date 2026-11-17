# Module: app/masks [AI]

Defines and manages built-in prompt templates and system persona presets (masks) in multiple languages (English, Simplified Chinese, Traditional Chinese), providing preconfigured conversation contexts and model configurations, as well as build and runtime fetching utilities.

## Key files
- `app/masks/index.ts`: Runtime store and client-side loader for built-in masks
- `app/masks/build.ts`: Build script that exports all language masks into public/masks.json
- `app/masks/typing.ts`: Type definitions for BuiltinMask
- `app/masks/cn.ts`: Simplified Chinese built-in mask definitions
- `app/masks/en.ts`: English built-in mask definitions
- `app/masks/tw.ts`: Traditional Chinese built-in mask definitions

## Public interface
- BUILTIN_MASK_ID: number
- BUILTIN_MASK_STORE: { buildinId: number, masks: Record<string, BuiltinMask>, get(id?: string): Mask | undefined, add(m: BuiltinMask): Mask }
- BUILTIN_MASKS: BuiltinMask[]
- type BuiltinMask
- CN_MASKS: BuiltinMask[]
- EN_MASKS: BuiltinMask[]
- TW_MASKS: BuiltinMask[]

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
