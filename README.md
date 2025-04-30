# Nuxt Boilerplate

![Nuxt Boilerplate](https://github.com/fleek-tools/nuxt-template/assets/74613246/614fa65c-e839-4ff0-8692-be7a3df55169)

Static site starter application built on Nuxt. Output directory set to `.output/public` and build command `pnpm install && pnpm generate`.

## 🚀 Project Structure

Inside of your Nuxt project, you'll see the following folders and files:

```text
/
├── assets/
├── public/
├── components/
├── app.vue
├── nuxt.config.js
└── package.json
```

If you want to learn more about `Nuxt`, you can checkout the official [Nuxt Documentation](https://nuxt.com/docs).

## 🧞 Commands

All commands are run from the root of the project, from a terminal:

| Command             | Action                                       |
| :------------------ | :------------------------------------------- |
| `pnpm install`      | Installs dependencies                        |
| `pnpm run dev`      | Starts local dev server at `localhost:3000`  |
| `pnpm run build`    | Build your production site to `.out/public`  |
| `pnpm run start`    | Start your production site locally           |
| `pnpm run generate` | Generate static project ready for deployment |

## ⚡ How to deploy to Fleek (IPFS)

### 1. Create a `fleek.json` config file

You can configure this site deployment using [Fleek CLI](https://fleek.xyz/docs/cli/) and running:

```bash
 > fleek sites init
   WARN! Fleek CLI is in beta phase, use it under your own responsibility
   ? Choose one of the existing sites or create a new one. ›
   ❯ Create a new site
```

It will prompt you for a `name`, `dist` directory location & `build command`

- `name`: How you want to name the site
- `dist`: The output directory where the site is located, for this template it's `.output/public`
- `build command`: Command to build your site, this will be used to deploy the latest version either by CLI or Github Actions

### 2. Deploy the site

After configuring your `fleek.json` file, you can deploy the site by running

```bash
fleek sites deploy
```

After running it you will get an output like this:

```bash
 WARN! Fleek CLI is in beta, use it at your own discretion
 > Success! Deployed!
 > Site IPFS CID: QmeMeqXPbcW6mdwMrZtZcmzntn7Di28LYxdFWj7SZchASp

 > You can visit through the gateway:
 > https://ipfs.io/ipfs/QmeMeqXPbcW6mdwMrZtZcmzntn7Di28LYxdFWj7SZchASp
```

### Extra features

- **Continuous Integration (CI):** `fleek sites ci` [Documentation.](https://fleek.xyz/docs/cli/sites/#continuous-integration)
- **Adding custom domains:** `fleek domains create` [Documentation.](https://fleek.xyz/docs/platform/domains/)

### Keep in mind

This template has been configured to produce a static output. This means you can deploy it directly to IPFS without needing a server. Make sure to generate your static site before deploying using `pnpm run generate`.

In order to make the routing compatible with IPFS, we've set the cdnURL to:

```js
// nuxt.config.js

// https://nuxt.com/docs/api/configuration/nuxt-config
export default defineNuxtConfig({
  app: {
    cdnURL: "./",
  }
}
```

This ensures our site can be rendered when accessed from a public gateway. Please test this thoroughly.

## 👀 Want to learn more?

Feel free to check [Fleek Documentation](https://fleek.xyz/docs/) & [Nuxt Documentation](https://nuxtjs.org/guide).
