# Guidelines

Conventions backed by **≥2** real, verbatim code examples. Anything with fewer is omitted below.

## Each AI provider proxy in app/api lives in its own file and exports an `async function handle(req, ...)` entry point; the dynamic [provider]/[...path] route dispatches to these handlers rather than embedding provider logic in the route.

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

## Read server-side settings exclusively through `getServerSideConfig()` (typically once at module level as `const serverConfig`) instead of touching `process.env` directly in route handlers or server components.

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

## Build-mode and feature toggles are resolved from environment variables at the top of next.config.mjs with sensible defaults, and derived flags are computed from them rather than re-reading env elsewhere.

- `next.config.mjs`:

  ```
  const mode = process.env.BUILD_MODE ?? "standalone";
  ```

- `next.config.mjs`:

  ```
  const disableChunk = !!process.env.DISABLE_CHUNK || mode === "export";
  ```

## Shared constants (repo identity, provider paths, role lists) are exported from app/constant.ts or typing.ts as UPPER_SNAKE_CASE named exports and reused across client, API, and store code.

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

- `app/api/anthropic.ts`:

  ```
  const ALLOWD_PATH = new Set([Anthropic.ChatPath, Anthropic.ChatPath1]);
  ```

## Define explicit TypeScript types/interfaces for callback signatures and generic updaters near their usage rather than relying on inline function types.

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

- `app/polyfill.ts`:

  ```
  interface Array<T> {
  ```

## Shared helpers in app/utils.ts are exported as named, individually typed functions (sync or async as appropriate) so they can be unit-tested in isolation under test/.

- `app/utils.ts`:

  ```
  export function trimTopic(topic: string) {
  ```

- `app/utils.ts`:

  ```
  export async function copyToClipboard(text: string) {
  ```

## Next.js App Router metadata and viewport are declared as typed named exports from app/layout.tsx, and the root page is an async server component.

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

## Jest is configured via next/jest's createJestConfig wrapper with a typed Config object so Next.js module aliases and transforms apply to tests.

- `jest.config.ts`:

  ```
  const createJestConfig = nextJest({
  ```

- `jest.config.ts`:

  ```
  const config: Config = {
  ```

## Proxy handlers rebuild the upstream subpath from route params (joining catch-all segments or prefixing with the provider api path) instead of hardcoding URLs.

- `app/api/[provider]/[...path]/route.ts`:

  ```
  const apiPath = `/api/${params.provider}`;
  ```

- `app/api/azure.ts`:

  ```
  const subpath = params.path.join("/");
  ```
