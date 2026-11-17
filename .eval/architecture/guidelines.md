# Guidelines

Conventions backed by **≥2** real, verbatim code examples. Anything with fewer is omitted below.

## Each provider API module under app/api exports a single async `handle` function with the same signature so the dynamic [provider]/[...path] route can dispatch to it uniformly.

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

## Read server-side settings by calling `getServerSideConfig()` once at module scope (or at the top of the handler) rather than reading process.env directly inside provider logic.

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

## Derive the upstream sub-path from the route `params` (provider name and joined path segments) instead of parsing the raw request URL.

- `app/api/[provider]/[...path]/route.ts`:

  ```
  const apiPath = `/api/${params.provider}`;
  ```

- `app/api/azure.ts`:

  ```
  const subpath = params.path.join("/");
  ```

## Put shared repository/provider constants in app/constant.ts as named `export const` values so client and server code import a single source of truth.

- `app/constant.ts`:

  ```
  export const OWNER = "ChatGPTNextWeb";
  ```

- `app/constant.ts`:

  ```
  export const REPO = "ChatGPT-Next-Web";
  ```

- `app/typing.ts`:

  ```
  export const ROLES = ["system", "user", "assistant"] as const;
  ```

## Define shared TypeScript types with `type`/`interface` declarations alongside the code that uses them (app/typing.ts, app/command.ts) and export them for reuse.

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

## Expose reusable client helpers from app/utils.ts as plain named `export function` / `export async function` declarations.

- `app/utils.ts`:

  ```
  export function trimTopic(topic: string) {
  ```

- `app/utils.ts`:

  ```
  export async function copyToClipboard(text: string) {
  ```

## Control build-time behavior (output mode, chunking) via environment variables resolved at the top of next.config.mjs with explicit defaults.

- `next.config.mjs`:

  ```
  const mode = process.env.BUILD_MODE ?? "standalone";
  ```

- `next.config.mjs`:

  ```
  const disableChunk = !!process.env.DISABLE_CHUNK || mode === "export";
  ```

## Declare Next.js page metadata and viewport as typed `export const` values in the root layout.

- `app/layout.tsx`:

  ```
  export const metadata: Metadata = {
  ```

- `app/layout.tsx`:

  ```
  export const viewport: Viewport = {
  ```

## Configure Jest through `next/jest` by building a typed `Config` object and passing it to `createJestConfig`.

- `jest.config.ts`:

  ```
  const createJestConfig = nextJest({
  ```

- `jest.config.ts`:

  ```
  const config: Config = {
  ```

## Declare ambient module shapes (e.g. CSS/SVG imports) in app/global.d.ts with a typed `const content` and `export default content`.

- `app/global.d.ts`:

  ```
  const content: Record<string, string>;
  ```

- `app/global.d.ts`:

  ```
  export default content;
  ```
