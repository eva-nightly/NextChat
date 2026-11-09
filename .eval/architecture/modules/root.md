# Module: (root) [AI]

Provides root-level build, testing, code formatting, and runtime configuration for the Next.js application, including proxy rewrites for external AI provider APIs.

## Key files
- `next.config.mjs`: Configures Next.js output modes, Webpack rules (SVGR, chunk limits), CORS headers, and API proxy rewrites for AI provider endpoints (OpenAI, Azure, Google, Anthropic, Alibaba).
- `jest.config.ts`: Defines test runner settings using next/jest, configuring jsdom environment, path aliases, and setup files.
- `jest.setup.ts`: Sets up test environment extensions (@testing-library/jest-dom) and establishes a default mock implementation for global.fetch.
- `.prettierrc.js`: Specifies code formatting rules across the repository.

## Public interface
- default (nextConfig in next.config.mjs)
- default (createJestConfig in jest.config.ts)
- module.exports (.prettierrc.js)

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
