# Eepy Guys Website

GitHub Pages-ready static website for the Eepy Guys World of Warcraft guild.

## Upload to GitHub

Upload the contents of this folder to the root of your repo, not the zip itself.

Required root files:

- `index.html`
- `guild-hall.html`
- `raiding.html`
- `memory-hoard.html`
- `welcome-home.html`
- `guild-goods.html`
- `assets/`

Then enable Pages: **Settings → Pages → Deploy from branch → main → /root → Save**.

## Shopify link

Open `assets/main.js` and replace:

```js
shopifyUrl: 'SHOPIFY_LINK_GOES_HERE'
```

with your Shopify store URL.

## Raider.IO stats

The Raiding page attempts to load live guild progression from Raider.IO in the visitor's browser. If Raider.IO blocks browser requests or changes the API, the page falls back to a button linking to the guild profile.

## Discord-to-website images

GitHub Pages is static, so Discord cannot post images directly to the website without automation.

Best options:

1. Manual: upload images into `assets/gallery/` and list them in `assets/gallery/gallery.json`.
2. Automated: create a Discord bot or Cloudflare Worker that watches a Discord channel, downloads image attachments, commits them to this GitHub repo using the GitHub API, and updates `gallery.json`.
3. Semi-automated: use Zapier/Make to send Discord attachments to a storage bucket, then update `gallery.json` with public image URLs.

Avoid relying on Discord CDN URLs as permanent image hosting; they can change or expire.
