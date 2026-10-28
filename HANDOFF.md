# How this repo hands changes to the HW site (hotwiredcaraudio-site)

This repo is where the HW quote-builder bot leaves finished deliverables. The HW Grok Build chat pulls them from here, builds, and pushes to the site repo. Richard presses Publish.

## Flow

1. The bot commits the deliverable to this repo under `handoff/<YYYY-MM-DD>-<name>/`.
2. Richard pastes the prompt below into the HW Grok Build chat.
3. The chat pulls this repo, builds, and pushes to `hotwiredcaraudio-site`.
4. Richard presses Publish.
5. The bot verifies the live md5 and byte count.

## Current handoff

No pending handoff.

Last one: bundle6, md5 `90120dc456ab60695c1c7c3bdb5b1a6d`, 723,758 bytes, published 2026-10-27 via site commit `5e196324`. It was pushed directly into `hotwiredcaraudio-site` as a one-time test, which worked.

The site repo is a full app. Static pages live under `public/`.

| Files (in `handoff/<folder>/`) | md5 | Bytes | Destination in `hotwiredcaraudio-site` | Status |
|---|---|---|---|---|
| `index.html` | (fill in) | (fill in) | `public/quote/index.html` | none pending |
| `Hotwired-Quote-Builder.html` | (fill in) | (fill in) | `public/quote/Hotwired-Quote-Builder.html` | none pending |

The two quote-builder files are byte-identical twins, so both rows carry the same md5 and byte count.

## Ready-to-paste prompt for the HW Grok Build chat

````markdown
Pull the latest main from TheReeferGarden/hotwired-car-audio-quote-catalog.

Copy these files from handoff/<folder>/ into hotwiredcaraudio-site, byte-for-byte (no editing, merging, or regenerating):
- handoff/<folder>/<file 1>  ->  <destination path 1>
- handoff/<folder>/<file 2>  ->  <destination path 2>

Confirm the md5 of each copied file matches:
- <file 1>: <md5 1> (<bytes 1> bytes)
- <file 2>: <md5 2> (<bytes 2> bytes)

Commit and push to hotwiredcaraudio-site, then say "ready to publish".
````

## Rules

- The catalog data (`data/catalog/`, `img/products/`) is NOT part of handoffs. It keeps going live through jsDelivr.
- Keep the SEO tags, the fixed step bar, the 10-digit phone check, and the 14-key Web3Forms payload.
- The bot never pushes into the site repo itself.
- Always list md5 and bytes for every file.
- Test with Web3Forms intercepted. Never send a real quote.
