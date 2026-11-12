# Module: (root) [AI]

Provides project-level configuration for build pipelines, Next.js runtime/bundler behavior, proxy rewrites to external AI/LLM providers, code formatting, and Jest test environments.

## Key files
- `next.config.mjs`: Next.js configuration setting up Webpack rules, build modes (standalone or static export), CORS headers for API routes, and proxy rewrites for LLM provider APIs (OpenAI, Azure, Anthropic, Google, Alibaba).
- `jest.config.ts`: Jest testing configuration using next/jest with jsdom test environment, module aliasing, and setup file hooks.
- `jest.setup.ts`: Test setup script configuring @testing-library/jest-dom and providing global fetch mock definitions.
- `.prettierrc.js`: Prettier code formatting rules for the repository.

## Public interface
- export default nextConfig (next.config.mjs)
- export default createJestConfig(config) (jest.config.ts)
- module.exports (prettier configuration object in .prettierrc.js)

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
