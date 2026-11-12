# Guidelines

Conventions backed by **≥2** real, verbatim code examples. Anything with fewer is omitted below.

## Each provider proxy in app/api is implemented as an exported `async function handle(req, { params })`; the dynamic `app/api/[provider]/[...path]` route dispatches to these handlers rather than duplicating routing logic.

- `app/api/302ai.ts`:

  ```
  export async function handle(
  ```

- `app/api/alibaba.ts`:

  ```
  export async function handle(
  ```

- `app/api/anthropic.ts`:

  ```
  export async function handle(
  ```

- `app/api/azure.ts`:

  ```
  export async function handle(
  ```

- `app/api/baidu.ts`:

  ```
  export async function handle(
  ```

- `app/api/bytedance.ts`:

  ```
  export async function handle(
  ```

- `app/api/[provider]/[...path]/route.ts`:

  ```
  async function handle(
  ```

## Read server-side configuration once at module scope via `getServerSideConfig()` instead of calling it repeatedly inside request handlers.

- `app/api/302ai.ts`:

  ```
  const serverConfig = getServerSideConfig();
  ```

- `app/api/alibaba.ts`:

  ```
  const serverConfig = getServerSideConfig();
  ```

- `app/api/artifacts/route.ts`:

  ```
  const serverConfig = getServerSideConfig();
  ```

- `app/api/baidu.ts`:

  ```
  const serverConfig = getServerSideConfig();
  ```

- `app/api/bytedance.ts`:

  ```
  const serverConfig = getServerSideConfig();
  ```

- `app/api/common.ts`:

  ```
  const serverConfig = getServerSideConfig();
  ```

- `app/page.tsx`:

  ```
  const serverConfig = getServerSideConfig();
  ```

## Drive build/bundler behavior from environment variables with sensible defaults in next.config.mjs (e.g., BUILD_MODE, DISABLE_CHUNK) rather than hardcoding modes.

- `next.config.mjs`:

  ```
  const mode = process.env.BUILD_MODE ?? "standalone";
  ```

- `next.config.mjs`:

  ```
  const disableChunk = !!process.env.DISABLE_CHUNK || mode === "export";
  ```

## Centralize shared literals (repo owner/name, URLs, provider identifiers) as named exported constants in app/constant.ts.

- `app/constant.ts`:

  ```
  export const OWNER = "ChatGPTNextWeb";
  ```

- `app/constant.ts`:

  ```
  export const REPO = "ChatGPT-Next-Web";
  ```

## Define explicit TypeScript types and interfaces for callback signatures and shared shapes; prefer `as const` tuples for literal unions.

- `app/command.ts`:

  ```
  type Command = (param: string) => void;
  ```

- `app/command.ts`:

  ```
  interface Commands {
  ```

- `app/typing.ts`:

  ```
  export type Updater<T> = (updater: (value: T) => void) => void;
  ```

- `app/typing.ts`:

  ```
  export const ROLES = ["system", "user", "assistant"] as const;
  ```

## Expose Next.js page metadata and viewport as typed exported constants from the root layout.

- `app/layout.tsx`:

  ```
  export const metadata: Metadata = {
  ```

- `app/layout.tsx`:

  ```
  export const viewport: Viewport = {
  ```

## Keep general-purpose helpers as named exported functions in app/utils.ts with typed parameters.

- `app/utils.ts`:

  ```
  export function trimTopic(topic: string) {
  ```

- `app/utils.ts`:

  ```
  export async function copyToClipboard(text: string) {
  ```

## Configure Jest through next/jest with a typed Config object so Next.js transforms and module aliases are applied consistently.

- `jest.config.ts`:

  ```
  const createJestConfig = nextJest({
  ```

- `jest.config.ts`:

  ```
  const config: Config = {
  ```

## Put ambient/global type shims (asset modules, Array polyfills) in dedicated declaration files rather than inline casts.

- `app/global.d.ts`:

  ```
  const content: Record<string, string>;
  ```

- `app/global.d.ts`:

  ```
  export default content;
  ```

- `app/polyfill.ts`:

  ```
  interface Array<T> {
  ```
