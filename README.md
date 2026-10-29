# Coffee Dial-In Tracker

A personal, mobile-first web app for logging espresso and pour-over brews and getting the next adjustment from taste feedback.

- **One file:** `index.html` with inline CSS and JS. No build step, no framework.
- **Data stays in the browser** (IndexedDB, falling back to localStorage). Nothing is sent to a server.
- **Backup:** Settings → Backup & move data → export/import JSON.

## Features

- **Brew:** log espresso (dose, yield, shot time, pre-infusion) or pour-over (dose, water, bloom, total time). Rate strength and extraction on 5-point scales. The form pre-fills from your last brew of that bean with the suggested change applied and highlighted.
- **Tuning suggestions:** one primary change sized by severity, one alternative, and a plain-English reason. Uses the standard brew-chart / espresso-compass rules. "Dialed in" brews become the bean's best recipe.
- **Beans:** roast, started and finished dates, brew history, best recipe, rating trend.
- **History:** filter by method and bean; edit or delete brews.
- **Tracker:** brews and coffee over time, espresso vs pour-over split, beans used vs coffee made, per-bean bag usage.
- **Settings:** grinders (step size and direction), brewers, °F/°C, default recipes, export/import.

## Editing the tuning rules

All suggestion amounts live in `TUNING_RULES` near the top of the script. Pour-over volume uses `POUROVER_RETENTION_G_PER_G` (default 2 g of water held per gram of grounds).

## Hosting

Any static host works. For Cloudflare Pages, connect this repo with no build command and the output directory set to `/`.

Data is tied to the site's exact address. Export before moving to a new domain, then import on the new one.
