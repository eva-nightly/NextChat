# Guidelines

Conventions backed by **≥2** real, verbatim code examples. Anything with fewer is omitted below.

## Each provider proxy file under app/api exposes a single exported `async function handle(req, { params })`; the dynamic [provider]/[...path] route dispatches to these handlers instead of each provider owning its own route file.

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

## Read server configuration once at module scope with `const serverConfig = getServerSideConfig();` rather than re-parsing environment variables inside request handlers or components.

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

## Declare shared constants (owners, repo names, roles, allowed paths) as UPPER_SNAKE_CASE `export const` values in constant/handler modules so they can be referenced by both client and server code.

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

## Build-time toggles in next.config.mjs are derived from `process.env` with explicit defaults and coerced to booleans before use.

- `next.config.mjs`:

  ```
  const mode = process.env.BUILD_MODE ?? "standalone";
  ```

- `next.config.mjs`:

  ```
  const disableChunk = !!process.env.DISABLE_CHUNK || mode === "export";
  ```

## Restrict upstream access by allow-listing provider subpaths: derive the subpath from route params and validate it against a Set of permitted paths before proxying.

- `app/api/anthropic.ts`:

  ```
  const ALLOWD_PATH = new Set([Anthropic.ChatPath, Anthropic.ChatPath1]);
  ```

- `app/api/azure.ts`:

  ```
  const subpath = params.path.join("/");
  ```

- `app/api/[provider]/[...path]/route.ts`:

  ```
  const apiPath = `/api/${params.provider}`;
  ```

## Model local shapes with TypeScript `type` aliases and `interface` declarations near their usage (commands, updaters, polyfill augmentations) instead of untyped objects.

- `app/command.ts`:

  ```
  type Command = (param: string) => void;
  ```

- `app/command.ts`:

  ```
  interface Commands {
  ```

- `app/polyfill.ts`:

  ```
  interface Array<T> {
  ```

- `app/typing.ts`:

  ```
  export type Updater<T> = (updater: (value: T) => void) => void;
  ```

## Next.js framework entry points export typed `metadata`/`viewport` objects and default-export async server components.

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

## Jest is configured through `next/jest`'s createJestConfig wrapper with a typed `Config` object and a jest.setup.ts that installs DOM matchers and a global fetch mock.

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

## Utilities in app/utils.ts are plain named `export function`/`export async function` helpers with explicit parameter types, keeping them tree-shakeable and easy to unit test.

- `app/utils.ts`:

  ```
  export function trimTopic(topic: string) {
  ```

- `app/utils.ts`:

  ```
  export async function copyToClipboard(text: string) {
  ```
