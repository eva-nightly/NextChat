# Module: app/masks [AI]

Defines built-in prompt templates (masks) across multiple languages (Simplified Chinese, Traditional Chinese, English) along with a build script to export them to a public JSON asset and browser-side loader logic to register built-in masks in memory.

## Key files
- `app/masks/index.ts`: Manages in-memory built-in mask storage and fetches masks from /masks.json when running in the browser.
- `app/masks/typing.ts`: Defines the BuiltinMask TypeScript type based on Mask and ModelConfig.
- `app/masks/build.ts`: Node build script compiling CN, TW, and EN mask definitions into public/masks.json.
- `app/masks/cn.ts`: Contains built-in prompt templates (masks) in Simplified Chinese.
- `app/masks/tw.ts`: Contains built-in prompt templates (masks) in Traditional Chinese.
- `app/masks/en.ts`: Contains built-in prompt templates (masks) in English.

## Public interface
- BUILTIN_MASK_ID: number
- BUILTIN_MASK_STORE: { buildinId: number, masks: Record<string, BuiltinMask>, get(id?: string): Mask | undefined, add(m: BuiltinMask): Mask }
- BUILTIN_MASKS: BuiltinMask[]
- BuiltinMask: type alias
- CN_MASKS: BuiltinMask[]
- TW_MASKS: BuiltinMask[]
- EN_MASKS: BuiltinMask[]

## Dependencies
- fs (node:fs)
- path (node:path)
- ../store
- ../store/mask

## AI touchpoints [AI]
- `app/masks/cn.ts`
- `app/masks/en.ts`
- `app/masks/tw.ts`

## Open questions
- _none_
