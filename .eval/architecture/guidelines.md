# Guidelines

Conventions backed by **≥2** real, verbatim code examples. Anything with fewer is omitted below.

## Each provider proxy in app/api is its own file exporting an `async function handle(req, params)` that is dispatched by the catch-all [provider]/[...path] route; add new providers as a new handler file plus a dispatcher case rather than a separate route.

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

## Server-only configuration is read once at module scope via `getServerSideConfig()` in API handlers and server components; never import it into client components.

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

## Build-time and deployment behaviour is driven by environment variables with explicit defaults in next.config.mjs (e.g. BUILD_MODE, DISABLE_CHUNK) rather than hardcoded values.

- `next.config.mjs`:

  ```
  const mode = process.env.BUILD_MODE ?? "standalone";
  ```

- `next.config.mjs`:

  ```
  const disableChunk = !!process.env.DISABLE_CHUNK || mode === "export";
  ```

## Shared literal constants (owner, repo, URLs, paths) live in app/constant.ts as UPPER_CASE named exports and are imported elsewhere instead of being re-declared.

- `app/constant.ts`:

  ```
  export const OWNER = "ChatGPTNextWeb";
  ```

- `app/constant.ts`:

  ```
  export const REPO = "ChatGPT-Next-Web";
  ```

## Model domain types are declared in app/typing.ts and app/command.ts as exported type aliases/interfaces; use `as const` tuples to derive union types from literal arrays.

- `app/typing.ts`:

  ```
  export type Updater<T> = (updater: (value: T) => void) => void;
  ```

- `app/typing.ts`:

  ```
  export const ROLES = ["system", "user", "assistant"] as const;
  ```

- `app/command.ts`:

  ```
  type Command = (param: string) => void;
  ```

- `app/command.ts`:

  ```
  interface Commands {
  ```

## Utility helpers in app/utils.ts are exported named functions with explicit parameter types, async where they touch browser APIs.

- `app/utils.ts`:

  ```
  export function trimTopic(topic: string) {
  ```

- `app/utils.ts`:

  ```
  export async function copyToClipboard(text: string) {
  ```

## Next.js root files use framework-typed named exports (`metadata: Metadata`, `viewport: Viewport`) and an async default-exported server component for the page.

- `app/layout.tsx`:

  ```
  export const metadata: Metadata = {
  ```

- `app/layout.tsx`:

  ```
  export const viewport: Viewport = {
  ```

- `app/page.tsx`:

  ```
  export default async function App() {
  ```

## Jest is configured through next/jest's createJestConfig with a typed `Config` object and jsdom environment; add global mocks in jest.setup.ts.

- `jest.config.ts`:

  ```
  const createJestConfig = nextJest({
  ```

- `jest.config.ts`:

  ```
  const config: Config = {
  ```

- `jest.setup.ts`:

  ```
  type: "basic",
  ```

## Edge handlers derive the proxied subpath from the dynamic route params (joining params.path / prefixing with /api/provider) instead of parsing the raw URL.

- `app/api/[provider]/[...path]/route.ts`:

  ```
  const apiPath = `/api/${params.provider}`;
  ```

- `app/api/azure.ts`:

  ```
  const subpath = params.path.join("/");
  ```
