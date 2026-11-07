# Module: (root) [AI]

Provides root-level configuration for Next.js build and routing proxy rules (including provider rewrites and CORS headers), Jest unit testing environment and fetch mocking, and Prettier code formatting.

## Key files
- `next.config.mjs`: Next.js configuration defining Webpack SVG loaders, chunk limits, CORS headers, build output modes, and URL rewrites/reverse-proxies to AI providers (Azure, Google, OpenAI, Anthropic, Alibaba) and ShareGPT.
- `jest.config.ts`: Jest test runner configuration integrating next/jest, setting jsdom test environment, and mapping module path aliases.
- `jest.setup.ts`: Global Jest setup script importing @testing-library/jest-dom and providing a default mock for global.fetch.
- `.prettierrc.js`: Code style and formatting configuration for Prettier.

## Public interface
- export default createJestConfig(config) (jest.config.ts)
- export default nextConfig (next.config.mjs)

## Dependencies
- webpack
- next/jest.js
- @jest/globals
- @testing-library/jest-dom
- @svgr/webpack

## AI touchpoints [AI]
- `next.config.mjs`

## Open questions
- _none_
