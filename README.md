# Physics Experiments

A collection of small, visually driven physics and geometry simulations built with [Astro](https://astro.build). Each experiment runs on an HTML `<canvas>` and has a collapsible control panel with speed, reset and fullscreen controls.

## Experiments

| Experiment | Route | Description |
| :--- | :--- | :--- |
| Bouncing Balls | `/experiments/bouncing-balls` | Balls collide inside a circle and spawn new balls on each collision. |
| Circle Painter | `/experiments/circle-painter` | A bouncing ball paints the circle, switching color each time it fills. |
| Growing Ball | `/experiments/growing-ball` | A ball grows with every bounce until it fills the whole circle. |
| Spirograph Classic | `/experiments/spirograph` | A wheel rolling inside another traces a hypotrochoid curve. |
| Spirograph Harmonograph | `/experiments/harmonograph` | Two damped pendulums trace decaying Lissajous-like curves. |

## Project structure

```text
/
├── public/                  # Static assets (favicon)
├── src/
│   ├── layouts/Layout.astro # Shared page layout
│   ├── styles/global.css    # Global styles and theme variables
│   └── pages/
│       ├── index.astro      # Landing page listing all experiments
│       └── experiments/     # One page per simulation
├── astro.config.mjs
└── wrangler.json            # Cloudflare deployment config (serves ./dist)
```

To add a new experiment, create a page in `src/pages/experiments/` and add a card linking to it in `src/pages/index.astro`.

## Development

This project uses [pnpm](https://pnpm.io).

| Command | Action |
| :--- | :--- |
| `pnpm install` | Install dependencies |
| `pnpm dev` | Start the dev server at `localhost:4321` |
| `pnpm build` | Build the static site to `./dist/` |
| `pnpm preview` | Preview the production build locally |

## Deployment

The site builds to static files in `./dist/`, which `wrangler.json` serves as Cloudflare Workers static assets. After building, deploy with:

```sh
npx wrangler deploy
```
