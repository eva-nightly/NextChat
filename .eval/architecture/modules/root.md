# Module: (root) [AI]

Provides root-level development, test, and build configurations for NextChat, including Prettier code formatting, Jest/jsdom test setup with mocked fetch, and Next.js configuration defining Webpack SVG loaders, build modes (export/standalone), CORS headers, and proxy rewrites for model provider endpoints.

## Key files
- `next.config.mjs`: Next.js configuration defining Webpack rules, build modes, CORS headers, and proxy rewrites for Azure, Google, OpenAI, Anthropic, Alibaba DashScope, and ShareGPT APIs.
- `jest.config.ts`: Jest test runner configuration integrating with Next.js, configuring jsdom environment, path aliases, and setup files.
- `jest.setup.ts`: Test setup script configuring @testing-library/jest-dom and providing a default global.fetch mock implementation.
- `.prettierrc.js`: Code style and formatting configuration for Prettier.

## Public interface
- default (next.config.mjs: NextConfig)
- default (jest.config.ts: Config)
- module.exports (.prettierrc.js: PrettierConfig)

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
