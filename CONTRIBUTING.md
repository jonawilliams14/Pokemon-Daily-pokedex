# Contributing

This is a single-file project — all HTML, CSS, and JavaScript lives in `index.html`. There's no build step or package manager.

## How to contribute

1. Fork the repository
2. Open `index.html` in your browser — that's the whole app
3. Make your changes directly in `index.html`
4. Test in a modern browser (Chrome or Firefox recommended)
5. Open a pull request with a clear description of what changed and why

## Things to keep in mind

**No dependencies.** The app intentionally has no npm, no bundler, no framework. Keep it that way. External resources are limited to Google Fonts (loaded via `<link>`) and the PokéAPI (fetched at runtime).

**Single file.** All CSS and JS stays inline in `index.html`. This is a deliberate design choice — it means the app is drag-and-drop deployable anywhere.

**API rate limits.** PokéAPI has a rate limit. The app caches responses where it can. Avoid adding features that fire large numbers of uncached parallel requests.

**Pokémon count.** The app covers Pokémon #1–1025 (Generations I–IX as of the `pokemon?limit=1025` endpoint). If PokéAPI adds more, the limit can be bumped.

## Adding alternate forms

Alternate forms are defined in the `ALTERNATE_FORMS` object near the top of the JS section, and the reverse map in `FORM_BASE_ID`. To add a new Pokémon's forms:

```js
const ALTERNATE_FORMS = {
  // ... existing entries ...
  649: [
    { slug: 'genesect',            label: 'Genesect' },
    { slug: 'genesect-burn',       label: 'Burn Drive' },
    { slug: 'genesect-chill',      label: 'Chill Drive' },
    { slug: 'genesect-douse',      label: 'Douse Drive' },
    { slug: 'genesect-shock',      label: 'Shock Drive' },
  ]
};
```

The `slug` must match the PokéAPI Pokémon endpoint name exactly (e.g. `https://pokeapi.co/api/v2/pokemon/genesect-burn`).

## Adding custom facts

Custom facts override the PokéAPI flavor text for specific Pokémon. Add entries to the `FACTS` object:

```js
const FACTS = {
  // ... existing entries ...
  384: "Rayquaza lived for hundreds of millions of years in the ozone layer, never descending to the ground."
};
```

## Bug reports

Open an issue with:
- Which Pokémon was affected (name and #ID)
- What you expected vs. what happened
- Browser and OS
