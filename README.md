# Meishe's Garden Book

A warm, quiet family journal for faith, movement, meals, weaning and spending. It's an installable phone app with a soft garden palette.

<p align="center">
  <img src="hero-home.jpg" alt="Home" width="49%">
  <img src="hero-wish.jpg" alt="Wish List" width="49%">
</p>

## Features

| Page | What it does |
|---|---|
| **Home** | Today's habits at a glance, weekly streak, and **How Josh is doing**, a small read-only summary of his day |
| **Faith** | Daily habit checklist with weekly adherence and a habit-by-habit view |
| **Weaning** | Peter's weaning journal: foods tried, allergen introductions and variety over two weeks |
| **Fitness** | Log a move, see the week, celebrate every step |
| **Food** | Belgian meal journal and a recipe box of family favorites |
| **Spending** | Weekly budget and category caps (Unavoidable, Optional, Frivolous) |
| **Wishes** | Shared wish lists: edit your own, view his, and tick what you bought so it vanishes from your view only |

Also: cloud sync with the household database and offline use.

## Gallery

<table>
  <tr>
    <td><img src="hero-faith.jpg" alt="Faith"><br><sub>Faith</sub></td>
    <td><img src="hero-baby.jpg" alt="Weaning"><br><sub>Weaning</sub></td>
  </tr>
  <tr>
    <td><img src="hero-fit.jpg" alt="Fitness"><br><sub>Fitness</sub></td>
    <td><img src="hero-food.jpg" alt="Food"><br><sub>Food</sub></td>
  </tr>
  <tr>
    <td><img src="hero-spend.jpg" alt="Spending"><br><sub>Spending</sub></td>
    <td></td>
  </tr>
</table>

## Stack

- **Front end:** a single `index.html` of vanilla HTML, CSS and JavaScript. No framework and no build step.
- **PWA:** service worker (`sw.js`) and web manifest for home-screen install and offline use.
- **Storage:** `localStorage` on the device, synced to **Supabase** (Auth plus a shared JSON snapshot row). Her data lives under its own key so the two apps never overwrite each other.
- **Fonts:** Jost and Pinyon Script from Google Fonts.

## Files

```
index.html               the whole app
sw.js                    offline cache
manifest.webmanifest     install metadata
hero-*.jpg               page background images
```

## Run it

1. Serve the folder over HTTPS (GitHub Pages works) and open `index.html`.
2. On iPhone: Safari, Share, **Add to Home Screen**.
3. Sign in from the **Cloud backup** card to sync with the household database.

## Security notes

- The publishable key in `index.html` is meant to be public. Access is controlled by Supabase row-level security, so never commit service keys.
- Both apps share one database row and one login, so "edit only your own list" is enforced by the apps themselves, not by the database.

## Credits

Background images are used for personal, non-commercial purposes. Replace them with your own if you publish this.
