# Guidelines

Conventions backed by **≥2** real, verbatim code examples. Anything with fewer is omitted below.

## Each provider proxy file in app/api exposes a single exported async `handle(req, { params })` function; the dynamic [provider]/[...path] route dispatches to it. Add new providers by following this signature rather than inventing a new route shape.

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

## Server-side code reads configuration once via `getServerSideConfig()` (module scope or at the top of the handler) instead of reading process.env directly in business logic.

- `app/page.tsx`:

  ```
  const serverConfig = getServerSideConfig();
  ```

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

## Build/runtime toggles in next.config.mjs are derived from environment variables with explicit defaults (e.g., BUILD_MODE, DISABLE_CHUNK) and composed into local flags before use.

- `next.config.mjs`:

  ```
  const mode = process.env.BUILD_MODE ?? "standalone";
  ```

- `next.config.mjs`:

  ```
  const disableChunk = !!process.env.DISABLE_CHUNK || mode === "export";
  ```

## Shared constants are exported from app/constant.ts and app/typing.ts as UPPER_SNAKE_CASE `export const` values (using `as const` for literal unions) so the rest of the app imports from a central registry.

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

## Define small named type aliases and interfaces for callbacks and option bags (e.g., Command, Commands, Updater<T>) rather than inlining complex function types.

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

## Utility helpers in app/utils.ts are exported named functions with explicitly typed parameters; async helpers are marked `async` and return Promises.

- `app/utils.ts`:

  ```
  export function trimTopic(topic: string) {
  ```

- `app/utils.ts`:

  ```
  export async function copyToClipboard(text: string) {
  ```

## Next.js layout metadata is declared via typed `export const metadata: Metadata` and `export const viewport: Viewport` rather than ad-hoc head tags.

- `app/layout.tsx`:

  ```
  export const metadata: Metadata = {
  ```

- `app/layout.tsx`:

  ```
  export const viewport: Viewport = {
  ```

## Jest is configured through next/jest's `nextJest` wrapper with a typed `Config` object, and default Response-like mocks are set in jest.setup.ts.

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

## Ambient module declarations in global.d.ts type asset imports as `Record<string, string>` with a default export so SVG/SCSS imports type-check.

- `app/global.d.ts`:

  ```
  const content: Record<string, string>;
  ```

- `app/global.d.ts`:

  ```
  export default content;
  ```

## Request routing helpers compute paths from route params (joining `params.path`, prefixing `/api/<provider>`) and forward headers like x-forwarded-for when extracting client identity.

- `app/api/[provider]/[...path]/route.ts`:

  ```
  const apiPath = `/api/${params.provider}`;
  ```

- `app/api/azure.ts`:

  ```
  const subpath = params.path.join("/");
  ```

- `app/api/auth.ts`:

  ```
  function getIP(req: NextRequest) {
  ```

- `app/api/auth.ts`:

  ```
  const forwardedFor = req.headers.get("x-forwarded-for");
  ```
