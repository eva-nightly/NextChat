# Module: (root) [AI]

Root-level configuration for Next.js build and runtime behavior (including API rewrites for AI provider proxies and CORS settings), Jest testing suite setup, and Prettier code formatting.

## Key files
- `next.config.mjs`: Configures Next.js compilation, Webpack SVG loaders, standalone or export output modes, API CORS headers, and reverse proxy rewrites to AI providers.
- `jest.config.ts`: Defines Jest test runner settings using next/jest, configuring jsdom environment, ESM support, and module path aliasing.
- `jest.setup.ts`: Configures Jest test environment extensions (@testing-library/jest-dom) and global fetch mock.
- `.prettierrc.js`: Defines code formatting rules across the codebase.

## Public interface
- nextConfig (default export from next.config.mjs)
- createJestConfig(config) (default export from jest.config.ts)
- module.exports (default export from .prettierrc.js)

## Dependencies
- webpack
- next/jest.js
- @testing-library/jest-dom
- @jest/globals
- @svgr/webpack

## AI touchpoints [AI]
- `next.config.mjs`

## Open questions
- _none_
