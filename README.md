# Daily Pokédex

A single-file browser app that surfaces a new Pokémon every day with full stats, Pokédex browser, evolution chains, and alternate forms — no build step, no dependencies, no server required.

![Daily Pokédex screenshot](https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/official-artwork/143.png)

---

## Features

**Daily Discovery**
- A new Pokémon is selected every day based on a date seed — the same Pokémon shows for all visitors on the same day
- Includes official artwork, genus, generation/region, height/weight, flavor text, and a curated fact

**Search**
- Live autocomplete by name or Pokédex number
- Filter chips narrow results by type (all 18) or category (Legendary, Mythical, Ultra Beast)
- Smart keyword detection — typing "fire", "legendary", etc. activates the matching filter automatically

**Pokédex Drawer**
- Full side drawer with all 1,025 Pokémon (Generations I–IX)
- Filter by generation tab, type chip, or category chip
- Badges for Legendary (★), Mythical, and Ultra Beast entries
- Active Pokémon is highlighted

**Pokémon Card**
- Animated type-based accent color theming
- Base stats with animated bars
- Full evolution chain with sprites — each stage is clickable
- Alternate form selector for Kyurem, Necrozma, Zacian, and Zamazenta

**Daily Notifications**
- Browser push notification support — opt-in reminder at midnight when the daily Pokémon changes

---

## Live Demo

Deploy to GitHub Pages, Netlify, or Cloudflare Pages — see [Deployment](#deployment) below.

---

## Usage

### Run locally

Just open `index.html` in any modern browser. No server, no install.

```
open index.html
```

### Deploy to GitHub Pages

1. Push this repository to GitHub
2. Go to **Settings → Pages**
3. Set source to **Deploy from a branch**, select `main`, folder `/` (root)
4. Your site will be live at `https://<your-username>.github.io/<repo-name>/`

### Deploy to Netlify (fastest)

1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag and drop `index.html` onto the page
3. Done — live in seconds at a generated URL

### Deploy to Cloudflare Pages

1. Push to GitHub
2. Connect repo at [pages.cloudflare.com](https://pages.cloudflare.com)
3. No build command needed, output directory is `/`

---

## Data Sources

| Data | Source |
|---|---|
| Pokémon stats, types, sprites, evolution chains | [PokéAPI](https://pokeapi.co) — free, open, no key required |
| Official artwork | [PokeAPI sprites GitHub](https://github.com/PokeAPI/sprites) |
| Pokédex list | `https://pokeapi.co/api/v2/pokemon?limit=1025` |

All data is fetched at runtime from public APIs. Nothing is bundled or stored locally.

---

## Alternate Forms

The following Pokémon have a form selector that appears on their card:

| Pokémon | Forms |
|---|---|
| Kyurem (#646) | Base · Black Kyurem · White Kyurem |
| Necrozma (#800) | Base · Dusk Mane · Dawn Wings · Ultra Necrozma |
| Zacian (#888) | Hero of Many Battles · Crowned Sword |
| Zamazenta (#889) | Hero of Many Battles · Crowned Shield |

---

## Project Structure

```
index.html        ← entire app (HTML + CSS + JS, self-contained)
README.md         ← this file
LICENSE           ← MIT license
.gitignore        ← standard web gitignore
netlify.toml      ← zero-config Netlify deployment
_headers          ← Cloudflare Pages / Netlify security headers
```

---

## Browser Support

| Browser | Support |
|---|---|
| Chrome / Edge 90+ | ✅ Full, including notifications |
| Firefox 90+ | ✅ Full, including notifications |
| Safari 16+ | ✅ Full (notifications require HTTPS) |
| Mobile Chrome / Safari | ✅ Responsive layout |

Requires `color-mix()` CSS support (available in all modern browsers since 2023).

---

## Deployment Notes

- **Notifications require HTTPS** — they will not work on `file://` URLs or plain HTTP. GitHub Pages, Netlify, and Cloudflare Pages all provide HTTPS automatically.
- The daily seed is based on UTC date, so the Pokémon changes at midnight UTC.
- All API requests go directly from the user's browser to PokéAPI — there is no backend.

---

## License

MIT — see [LICENSE](LICENSE). This project is an unofficial fan work and is not affiliated with Nintendo, Game Freak, or The Pokémon Company. Pokémon and all related names are trademarks of their respective owners.
