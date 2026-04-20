# `@red-hat-developer-hub/lightspeed-playwright-e2e`

Reusable **Playwright** helpers for [Lightspeed](https://github.com/redhat-developer/rhdh-plugins/tree/main/workspaces/lightspeed): page objects, API route mocks, i18n strings, and `bootstrapLightspeedE2ePage`. Consume it from **rhdh-plugins**, **rhdh-plugin-export-overlays**, or any other repo—same idea as depending on a small shared npm package.

## Install

**Published on npm** (after a maintainer runs `npm publish`; requires publish rights on the [`@red-hat-developer-hub`](https://www.npmjs.com/org/red-hat-developer-hub) scope):

```bash
npm install -D @red-hat-developer-hub/lightspeed-playwright-e2e@^0.1.0 @playwright/test
```

**From GitHub until then** — pin a **tag or commit** so installs stay reproducible (`#main` moves with every push):

```bash
npm install -D "github:redhat-developer/lightspeed-playwright-e2e#v0.1.0"
# or: github:redhat-developer/lightspeed-playwright-e2e#<commit-sha>
```

If no release tag exists yet, use `#main` or a full commit SHA until you tag.

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

Source repo: [redhat-developer/lightspeed-playwright-e2e](https://github.com/redhat-developer/lightspeed-playwright-e2e). The `package.json` `repository.url` matches that origin.

To publish **`@red-hat-developer-hub/lightspeed-playwright-e2e`** to npm you need **maintainer/publish access** to the `@red-hat-developer-hub` org on npm. Until then, depend via **`github:redhat-developer/lightspeed-playwright-e2e#<tag-or-commit>`** (see Install).

1. Bump `version` in `package.json`.
2. Tag and push, e.g. `git tag v0.1.0 && git push origin v0.1.0`.
3. `npm publish` (while logged in as an org member with publish rights).

## Syncing from rhdh-plugins

Lightspeed UI strings live under `src/i18n/` (copied from `backstage-plugin-lightspeed`). When plugin translations change, copy those files again or automate sync in CI.

## License

Apache-2.0 (same as rhdh-plugins Lightspeed).
