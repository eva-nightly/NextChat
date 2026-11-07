# Module: (root) [AI]

Root configuration files managing project formatting, Jest unit testing setup with DOM and fetch mocks, and Next.js build options including proxy rewrites to upstream AI providers and CORS settings.

## Key files
- `next.config.mjs`: Configures Next.js build modes, Webpack SVG loaders, CORS headers for /api/:path*, and proxy rewrites to Azure, Google, OpenAI, Anthropic, Alibaba, and ShareGPT endpoints.
- `jest.config.ts`: Defines Jest test runner configuration using next/jest, targeting jsdom and configuring path aliases.
- `jest.setup.ts`: Configures testing environment extensions including @testing-library/jest-dom and global mock for window.fetch.
- `.prettierrc.js`: Defines code formatting rules across the repository.

## Public interface
- default (nextConfig export from next.config.mjs)
- default (createJestConfig export from jest.config.ts)
- module.exports (prettier configuration from .prettierrc.js)

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
