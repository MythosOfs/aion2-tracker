# Aion 2 Tracker

A single-file, dependency-free web tracker for **AION 2** — a daily/weekly checklist plus field-boss respawn timers.

No build step, no server, no external requests. Open `index.html` in a browser (or host it anywhere static) and it just works.

![Aion 2 Tracker](preview.png)

## Features

**Checklist page**
- Dailies, weeklies and season tasks, split into account-wide and per-character
- Multiple characters with an inline add/remove list
- Configurable weekly reset day/time; dailies and weeklies reset themselves automatically
- Odyle Energy tracker per character, with refill projection and a "caps in under 24 h" warning
- Progress bars per section

**Timers page**
- **Field bosses** — all 49 (24 Elyos, 24 Asmodian, 1 Abyss), grouped by zone with their respawn cycle
- Tap **Killed** when you kill one: the respawn countdown starts
- The timer then **keeps rolling on its own**, assuming a kill 30 minutes after each spawn, so the cycle stays roughly accurate without further input
- Filter by faction, sort by zone or by next respawn, clear all timers at once
- Optional panel for other timed events (Spacetime Rift, Shugo Festival, Dimensional Invasion)

## Usage

```bash
git clone https://github.com/MythosOfs/aion2-tracker.git
cd aion2-tracker
xdg-open index.html      # or just double-click it
```

Everything is stored in a cookie on your own device — nothing is sent anywhere.

### Hosting

Because it is a single static file, any static host works (GitHub Pages, Cloudflare Pages, nginx, Caddy, …). If you serve it behind a reverse proxy, a plain `file_server` on the directory containing `index.html` is all that is needed.

## Data sources

- **Field boss list and respawn cycles** — [aion2timers.com](https://www.aion2timers.com/world-boss-timer/)
- **Reset times and event schedules** — community reports

Respawn cycles are community-maintained and can change with patches; treat every countdown as an estimate and re-log a real kill to re-sync it.

## Notes / limitations

- Field boss respawns are **kill-based**, so no static page can know the exact state without live kill data. This tracker therefore relies on the kill you log, then extrapolates.
- AION 2 has no public API for boss spawns or kills.
- Only affects the browser it is opened in.

## Disclaimer

Unofficial fan project. Not affiliated with, endorsed by, or sponsored by NCSOFT. Aion 2 and all related logos, characters and assets are trademarks or registered trademarks of NCSOFT Corporation.

## License

[MIT](LICENSE)