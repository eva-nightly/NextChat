# Guidelines

Conventions backed by **≥2** real, verbatim code examples. Anything with fewer is omitted below.

## Each provider proxy under app/api exposes a single exported `async function handle(req, { params })` with the same signature so the dynamic [provider]/[...path] route can dispatch to it uniformly.

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

## Resolve server-side configuration through `getServerSideConfig()` at the top of each API handler or server component rather than reading process.env directly in request logic.

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

## In build/config files, read environment variables with sensible defaults via `??` and derive boolean feature flags from them in one place.

- `next.config.mjs`:

  ```
  const mode = process.env.BUILD_MODE ?? "standalone";
  ```

- `next.config.mjs`:

  ```
  const disableChunk = !!process.env.DISABLE_CHUNK || mode === "export";
  ```

## Declare shared constants (repo identifiers, role lists, provider names) as `export const` in app/constant.ts or app/typing.ts, using `as const` for literal unions where consumers need narrow types.

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

## Annotate exported framework configuration objects with their explicit types (e.g. Next.js Metadata/Viewport, Jest Config) instead of relying on inference.

- `jest.config.ts`:

  ```
  const config: Config = {
  ```

- `app/layout.tsx`:

  ```
  export const metadata: Metadata = {
  ```

- `app/layout.tsx`:

  ```
  export const viewport: Viewport = {
  ```

## Model callback and updater shapes with small named type aliases or interfaces (Command, Commands, Updater<T>) rather than inline function types.

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

## Expose shared helpers as named exported functions in app/utils.ts with explicit parameter types, using async only when the helper awaits browser or network APIs.

- `app/utils.ts`:

  ```
  export function trimTopic(topic: string) {
  ```

- `app/utils.ts`:

  ```
  export async function copyToClipboard(text: string) {
  ```

## Derive upstream request paths from the dynamic route params (provider segment and joined path array) rather than hard-coding URLs per handler.

- `app/api/[provider]/[...path]/route.ts`:

  ```
  const apiPath = `/api/${params.provider}`;
  ```

- `app/api/azure.ts`:

  ```
  const subpath = params.path.join("/");
  ```

## Keep server-page entry points as async server components that fetch server config before rendering the client shell.

- `app/page.tsx`:

  ```
  const serverConfig = getServerSideConfig();
  ```

- `app/page.tsx`:

  ```
  export default async function App() {
  ```
