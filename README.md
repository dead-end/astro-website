# Installation

## Node js

Ensure that we have a propper node version.

```sh
nvm use --lts
Now using node v20.10.0 (npm v10.2.3)
```

## Astro Project

Create a new astro project.

```sh
npm create astro@latest
```

I am using the following configurations:

- Project: astro-website
- Include sample files
- Install dependencies
- Typescript: yes
- Mode: strict
- Initialize git: yes

## Tailwind

Install tailwind:

```sh
npx astro add tailwind
```

Create a css file: `src/styles/base.css` with this content:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Import the css file in the layout component: `src/layouts/Layout.astro`

```
---
import "../styles/base.css";
---
```

Deactivate the default css file:

```js
import { defineConfig } from "astro/config";

import tailwind from "@astrojs/tailwind";

export default defineConfig({
  integrations: [
    tailwind({
      applyBaseStyles: false,
    }),
  ],
});
```

## Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |
