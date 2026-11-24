# Loop test site

A small Astro site for a made-up bakery. It exists only as a target for testing Niftly's AI update loops.

## Layout

- `src/data/site.json`: business name, tagline, phone, email, address and opening hours. Change facts here, not in the pages.
- `src/layouts/Base.astro`: the shared page shell (head, header, navigation, footer). Add new navigation links to its `links` list.
- `src/pages/`: one `.astro` file per page (`index`, `about`, `contact`).
- `src/styles/global.css`: all styles. Plain CSS, no framework.

## Conventions

- Plain Astro and CSS only. Do not add Tailwind, UI frameworks or client-side JavaScript unless the task asks for it.
- Every page uses the `Base` layout and passes a `title`.
- Two-space indentation, double quotes.

## Before opening a pull request

Run both and make sure they pass:

    pnpm install
    pnpm check
    pnpm build
