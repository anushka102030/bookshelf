# bookshelf

Created with the following setup:

```bash
>npx sv create bookshelf
┌  Welcome to the Svelte CLI! (v0.8.3)
│
◇  Which template would you like?
│  SvelteKit minimal
│
◇  Add type checking with TypeScript?
│  Yes, using TypeScript syntax
│
◆  Project created
│
◇  What would you like to add to your project? (use arrow keys / space bar)
│  prettier, eslint, playwright, tailwindcss, sveltekit-adapter, drizzle, mdsvex, paraglide, storybook
│
◇  tailwindcss: Which plugins would you like to add?
│  typography, forms
│
◇  sveltekit-adapter: Which SvelteKit adapter would you like to use?
│  auto
│
◇  drizzle: Which database would you like to use?
│  PostgreSQL
│
◇  drizzle: Which PostgreSQL client would you like to use?
│  Postgres.JS
│
◇  drizzle: Do you want to run the database locally with docker-compose?
│  Yes
│
◇  paraglide: Which languages would you like to support? (e.g. en,de-ch)
│  en, es
│
◇  paraglide: Do you want to include a demo?
│  Yes
│
◇  storybook: Running external command (npx storybook@latest init --skip-install --no-dev)
╭───────────────────────────────────────────────────────╮
│                                                       │
│   Adding Storybook version 8.6.12 to your project..   │
│                                                       │
╰───────────────────────────────────────────────────────╯
√ What do you want to use Storybook for? » Documentation: MDX, auto-generated component docs, Testing: Fast browser-based component tests, watch mode
 • Detecting project type. ✓
WARN An issue occurred while trying to find dependencies metadata using npm.
WARN An issue occurred while trying to find dependencies metadata using npm.
 • Adding Storybook support to your "SvelteKit" appWARN An issue occurred while trying to find dependencies metadata using npm.

  ✅ Getting the correct version of 8 packages
    Configuring eslint-plugin-storybook in your package.json
  ✅ Installing Storybook dependencies
WARN An issue occurred while trying to find dependencies metadata using npm.
. ✓

attention => Storybook now collects completely anonymous telemetry regarding usage.
This information is used to shape Storybook's roadmap and prioritize features.
You can learn more, including how to opt-out if you'd not like to participate in this anonymous program, by visiting the following URL:
https://storybook.js.org/telemetry

> npx storybook@8.6.12 add @storybook/experimental-addon-test@8.6.12
npm warn deprecated inflight@1.0.6: This module is not supported, and leaks memory. Do not use it. Check out lru-cache if you want a good and tested way to coalesce async requests by a key value, which is much more comprehensive and powerful.
npm warn deprecated rimraf@2.6.3: Rimraf versions prior to v4 are no longer supported
npm warn deprecated glob@7.2.3: Glob versions prior to v9 are no longer supported
Verifying @storybook/experimental-addon-test
The version of @storybook/experimental-addon-test (8.6.12) you are installing is not the same as the version of Storybook you are using (undefined). This may lead to unexpected behavior.
Installing @storybook/experimental-addon-test@^8.6.12
Adding '@storybook/experimental-addon-test@8.6.12' to the "addons" field in .storybook\main.ts
Running postinstall script for @storybook/experimental-addon-test

╭ 👋 Howdy! ─────────────────────────────────────────────────────────────────╮
│                                                                            │
│   I'm the installation helper for @storybook/experimental-addon-test       │
│                                                                            │
│   Hold on for a moment while I look at your project and get it set up...   │
│                                                                            │
╰────────────────────────────────────────────────────────────────────────────╯

╭ 🙈 Let me cover this for you ──────────────────────────────────────────────────────────────────────────────────────────────╮
│                                                                                                                            │
│   You don't seem to have a coverage reporter installed. Vitest needs either V8 or Istanbul to generate coverage reports.   │
│                                                                                                                            │
│   Adding @vitest/coverage-v8 to enable coverage reporting.                                                                 │
│   Read more about Vitest coverage providers at https://vitest.dev/guide/coverage.html#coverage-providers                   │
│                                                                                                                            │
╰────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────╯

› Installing dependencies:
  vitest@latest, @vitest/browser@latest, playwright, @vitest/coverage-v8@latest

› Configuring Playwright with Chromium (this might take some time):
  npx playwright install chromium --with-deps

› Creating a Vitest setup file for Storybook:
  C:/Users/tejas/Documents/bookshelf/bookshelf/.storybook/vitest.setup.ts

╭ ⚠️ Cannot update config file ───────────────────────────────────────────────────╮
│                                                                                 │
│   Could not update your existing Vite config file:                              │
│   C:\Users\tejas\Documents\bookshelf\bookshelf\vite.config.ts                   │
│                                                                                 │
│   Your existing config file cannot be safely updated, so instead a new Vitest   │
│   workspace file will be created, extending from your config file.              │
│                                                                                 │
│   Please refer to the Vitest documentation to learn about the workspace file:   │
│   https://vitest.dev/guide/workspace.html                                       │
│                                                                                 │
╰─────────────────────────────────────────────────────────────────────────────────╯

› Creating a Vitest workspace file:
  C:/Users/tejas/Documents/bookshelf/bookshelf/vitest.workspace.ts

╭ 🎉 All done! ─────────────────────────────────────────────────────────────────────────────────────╮
│                                                                                                   │
│   The Storybook Test addon is now configured and you're ready to run your tests!                  │
│                                                                                                   │
│   Here are a couple of tips to get you started:                                                   │
│   • You can run tests with npx vitest --project=storybook                                         │
│   • When using the Vitest extension in your editor, all of your stories will be shown as tests!   │
│                                                                                                   │
│   Check the documentation for more information about its features and options at:                 │
│   https://storybook.js.org/docs/writing-tests/test-addon                                          │
│                                                                                                   │
╰───────────────────────────────────────────────────────────────────────────────────────────────────╯

╭──────────────────────────────────────────────────────────────────────────────╮
│                                                                              │
│   Storybook was successfully installed in your project! 🎉                   │
│   Additional features: Documentation, Testing                                │
│                                                                              │
│   To run Storybook manually, run npm run storybook. CTRL+C to stop.          │
│                                                                              │
│   Wanna know more about Storybook? Check out https://storybook.js.org/       │
│   Having trouble or want to chat? Join us at https://discord.gg/storybook/   │
│                                                                              │
╰──────────────────────────────────────────────────────────────────────────────╯
│
◆  Successfully setup add-ons
│
◇  Which package manager do you want to install dependencies with?
│  npm
│
◆  Successfully installed dependencies
│
◇  Successfully formatted modified files
│
◇  Project next steps ─────────────────────────────────────────────────────╮
│                                                                          │
│  1: cd bookshelf                                                         │
│  2: git init && git add -A && git commit -m "Initial commit" (optional)  │
│  3: npm run dev -- --open                                                │
│                                                                          │
│  To close the dev server, hit Ctrl-C                                     │
│                                                                          │
│  Stuck? Visit us at https://svelte.dev/chat                              │
│                                                                          │
├──────────────────────────────────────────────────────────────────────────╯
│
◇  Add-on next steps ──────────────────────────────────────────────────╮
│                                                                      │
│  drizzle:                                                            │
│  - You will need to set DATABASE_URL in your production environment  │
│  - Run npm run db:start to start the docker container                │
│  - Run npm run db:push to update your database schema                │
│                                                                      │
│  paraglide:                                                          │
│  - Edit your messages in messages/en.json                            │
│  - Visit /demo/paraglide route to view the demo                      │
│                                                                      │
├──────────────────────────────────────────────────────────────────────╯
│
└  You're all set!
```