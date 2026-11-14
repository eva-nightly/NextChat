# Module: (root) [AI]

Provides root-level build, bundling, code formatting, and test configurations for the Next.js application, including proxy rewrites for various AI model provider endpoints and CORS configuration.

## Key files
- `next.config.mjs`: Configures Next.js build output mode, SVGR webpack loading, CORS headers, and API proxy rewrites for model providers (OpenAI, Azure, Google, Anthropic, Alibaba) and third-party services.
- `jest.config.ts`: Configures Jest test runner using next/jest, setting up jsdom environment, path mappings, and setup files.
- `jest.setup.ts`: Initializes test environment extensions with @testing-library/jest-dom and provides a default mock for global fetch.
- `.prettierrc.js`: Defines code formatting rules across the project.

## Public interface
- default export in next.config.mjs (NextConfig object)
- default export in jest.config.ts (Jest configuration promise wrapper)
- module.exports in .prettierrc.js (Prettier configuration object)

## Dependencies
- next
- webpack
- @svgr/webpack
- jest
- @testing-library/jest-dom
- @jest/globals

## AI touchpoints [AI]
- `next.config.mjs`

## Open questions
- _none_
