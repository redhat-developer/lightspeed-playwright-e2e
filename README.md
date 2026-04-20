# `@red-hat-developer-hub/lightspeed-playwright-e2e`

Reusable **Playwright** helpers for [Lightspeed](https://github.com/redhat-developer/rhdh-plugins/tree/main/workspaces/lightspeed): page objects, API route mocks, i18n strings, and `bootstrapLightspeedE2ePage`. Consume it from **rhdh-plugins**, **rhdh-plugin-export-overlays**, or any other repo—same idea as depending on a small shared npm package.

## Install

**Published (recommended once you publish to npm):**

```bash
npm install -D @red-hat-developer-hub/lightspeed-playwright-e2e@^0.1.0 @playwright/test
```

**Git (pin a tag or commit):**

```bash
npm install -D "github:redhat-developer/lightspeed-playwright-e2e#main"
```

**Local path (monorepo / sibling clone):**

```json
{
  "devDependencies": {
    "@red-hat-developer-hub/lightspeed-playwright-e2e": "file:../lightspeed-playwright-e2e"
  }
}
```

## Use

```ts
import {
  bootstrapLightspeedE2ePage,
  openChatbot,
  models,
} from '@red-hat-developer-hub/lightspeed-playwright-e2e';
```

Your repo keeps **only** `playwright.config.ts` and `*.spec.ts` / `*.test.ts` files; mocks and page objects live here.

## Publish

1. `git init` / push this tree to `github.com/redhat-developer/lightspeed-playwright-e2e` (or your org).
2. Bump `version` in `package.json`, tag, `npm publish` (with npm org access to `@red-hat-developer-hub`).

## Syncing from rhdh-plugins

Lightspeed UI strings live under `src/i18n/` (copied from `backstage-plugin-lightspeed`). When plugin translations change, copy those files again or automate sync in CI.

## License

Apache-2.0 (same as rhdh-plugins Lightspeed).
