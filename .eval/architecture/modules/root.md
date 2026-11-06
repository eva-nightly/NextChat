# Module: (root) [AI]

Provide root-level build, bundling, code formatting, testing configuration, and API proxy rewrites for the NextChat Next.js application.

## Key files
- `next.config.mjs`: Configures Next.js output modes, Webpack SVG loaders and chunk limits, CORS headers, and API proxy rewrites for OpenAI, Azure, Google, Anthropic, Alibaba, ShareGPT, and Google Fonts.
- `jest.config.ts`: Defines Jest test environment configuration with jsdom, Next.js integration, module aliases, and test match patterns.
- `jest.setup.ts`: Sets up testing environment extensions (@testing-library/jest-dom) and mocks the global fetch API.
- `.prettierrc.js`: Defines code formatting rules across the repository.

## Public interface
- default export createJestConfig (jest.config.ts)
- default export nextConfig (next.config.mjs)

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
