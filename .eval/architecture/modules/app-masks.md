# Module: app/masks [AI]

Defines and compiles built-in prompt templates (masks) across multiple languages (CN, TW, EN) with role contexts and default model configurations, and provides client-side runtime loading and build-time bundling to static JSON.

## Key files
- `app/masks/index.ts`: Manages runtime client-side fetching from /masks.json, maintains the in-memory BUILTIN_MASK_STORE, and assigns incremental IDs to loaded masks.
- `app/masks/build.ts`: Node.js build script that aggregates language-specific masks and writes them to public/masks.json.
- `app/masks/typing.ts`: Defines the BuiltinMask type definition based on Mask and ModelConfig.
- `app/masks/cn.ts`: Contains built-in Chinese prompt templates with predefined role messages and model parameters.
- `app/masks/en.ts`: Contains built-in English prompt templates with predefined role messages and model parameters.
- `app/masks/tw.ts`: Contains built-in Traditional Chinese prompt templates with predefined role messages and model parameters.

## Public interface
- BUILTIN_MASK_ID: number
- BUILTIN_MASK_STORE: { buildinId: number; masks: Record<string, BuiltinMask>; get(id?: string): Mask | undefined; add(m: BuiltinMask): BuiltinMask }
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
