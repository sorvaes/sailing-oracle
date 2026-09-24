# Sailing Oracle

A hobby web app that reads the Open-Meteo forecast and tells you whether it's a good day to sail. Built by Esko as a vibe-coding learning project.

## Tech
- One self-contained file: `index.html` (HTML, CSS, vanilla JavaScript). No framework, no build step.
- Weather data: Open-Meteo forecast API, no API key. Hourly wind, gusts, direction, rain chance, weather code, visibility and temperature. Wind in m/s, timezone Europe/Helsinki, 8 forecast days.
- Fonts from Google Fonts: Barlow, Barlow Condensed, Source Serif 4 (italic, for place names).
- Only browser storage: the last selected spot, in localStorage.

## Behaviour
- Spots: Turku, Nauvo, Korppoo, Utö, Hanko, Helsinki. Default is Nauvo.
- Sailing window 08–22. The verdict uses the average wind and the strongest gust in that window.
- Day strip: today plus 7 days, each with a verdict-coloured dot.
- Verdict rules, tuned for a cruising yacht:
  - Thunder, gusts of 16 m/s or more, or wind of 12 m/s or more: "Stay in harbour."
  - Wind of 9 m/s or more, or gusts of 13 m/s or more: "Reef early."
  - Wind under 2.5 m/s: "Bring a paddle."
  - Otherwise: "Go sailing."
  - Rain chance of 60% or more turns "Go sailing" into "Go, in oilskins."
  - Visibility under 1000 m gives "Mind the fog."
  - Air under 8 °C adds a dress-warm note.
- If the live fetch fails, the page falls back to what-if sliders.
- Look: nautical chart palette, buoy colours (green go, yellow caution, red stay) with matching topmarks. Light and dark mode.

## Must keep
- The reminder under the verdict and the full disclaimer section: hobby project, the captain decides, no liability, use at your own risk.
- The Open-Meteo attribution in the footer.

## Hosting
- Public repo: https://github.com/sorvaes/sailing-oracle
- Live on GitHub Pages from the `main` branch: https://sorvaes.github.io/sailing-oracle/
- A push to `main` rebuilds the site in about a minute.

## Plans
- Link to the live site from Esko's WordPress site.

## Working style
- Esko is learning Claude Code: explain each change briefly.
- Commit after each working change, then push to publish it.
- Commits use the name `sorvaes` and the GitHub noreply address, set for this repo only. Never commit with a personal or work email.
