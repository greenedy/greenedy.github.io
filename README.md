# greenedy.com

Personal website for Dylan Greene. Built with [Astro](https://astro.build),
styled with hand-written CSS, deployed to GitHub Pages.

## Structure

```
src/pages/          one file per route — index, about, projects, 404
src/layouts/        Layout.astro — the <html> shell, <head>, footer
src/components/     Header, ScrollToTop, LinkCard, CopyEmail, icons/
src/styles/         global.css — everything, light + dark via CSS variables
public/             copied verbatim into the build (CNAME lives here)
```

Header and footer live in `Layout.astro` and `Header.astro`. Change them once
and every page picks it up.

## Local development

```bash
npm install
```

```bash
npm run dev
```

Opens <http://localhost:4321>. `npm run build` writes the static site to
`dist/`; `npm run preview` serves that build. `npm run check` type-checks the
`.astro` files.

### Versions

Node 24 LTS and Astro 7. Astro 7 requires Node >= 22.12, and CI builds on
Node 24 to match.

TypeScript is held at v6 — `@astrojs/check` peers on `^5 || ^6`, so
`typescript@latest` (v7) breaks `npm run check` while leaving `npm run build`
working. Revisit once `@astrojs/check` supports v7.

## Deploying

`.github/workflows/deploy.yml` builds and publishes on every push to `main`.

This requires **Settings → Pages → Source = "GitHub Actions"** (not "Deploy
from a branch"). The custom domain is set by `public/CNAME`.

## Adding things

- **A project** — add an entry to the `projects` array in
  `src/pages/projects.astro`. Screenshots go in `public/projects/`.
- **A link on the home page** — add a `<LinkCard>` in `src/pages/index.astro`.
  Brand icons are small `.astro` files in `src/components/icons/`.
- **A page** — drop a `.astro` file in `src/pages/`; the filename becomes the
  URL. Wrap the content in `<Layout>` and the chrome comes with it.

## Credits

The design and layout are closely modelled on
[lukeberrypi.com](https://lukeberrypi.com) by Luke Berry
([source](https://github.com/LukeberryPi/blog)), used under the MIT License:

> Copyright (c) 2025 LukeberryPi
>
> Permission is hereby granted, free of charge, to any person obtaining a copy
> of this software and associated documentation files (the "Software"), to deal
> in the Software without restriction, including without limitation the rights
> to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
> copies of the Software, and to permit persons to whom the Software is
> furnished to do so, subject to the following conditions:
>
> The above copyright notice and this permission notice shall be included in
> all copies or substantial portions of the Software.
>
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
> IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
> FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
> AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
> LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
> FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS
> IN THE SOFTWARE.

Interface icons are [Lucide](https://lucide.dev), ISC License:

> Copyright (c) for portions of Lucide are held by Cole Bemis 2013-2022 as part
> of Feather (MIT). All other copyright (c) for Lucide are held by Lucide
> Contributors 2022.
>
> Permission to use, copy, modify, and/or distribute this software for any
> purpose with or without fee is hereby granted, provided that the above
> copyright notice and this permission notice appear in all copies.
>
> THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH
> REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF MERCHANTABILITY
> AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT,
> INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER RESULTING FROM
> LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR
> OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR
> PERFORMANCE OF THIS SOFTWARE.

Brand marks (GitHub, LinkedIn, X, Bluesky) are
[Simple Icons](https://simpleicons.org), released under CC0 1.0. The
[Karla](https://fonts.google.com/specimen/Karla) typeface is served by Google
Fonts under the SIL Open Font License 1.1.
