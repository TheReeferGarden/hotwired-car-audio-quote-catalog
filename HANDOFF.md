# How this repo hands changes to the HW site (hotwiredcaraudio-site)

This repo is where the HW quote-builder bot leaves finished deliverables. The HW Grok Build chat pulls them from here, builds, and pushes to the site repo. Richard presses Publish.

## Flow

1. The bot commits the deliverable to this repo under `handoff/<YYYY-MM-DD>-<name>/`.
2. Richard pastes the prompt below into the HW Grok Build chat.
3. The chat pulls this repo, builds, and pushes to `hotwiredcaraudio-site`.
4. Richard presses Publish.
5. The bot verifies the live md5 and byte count.

## Current handoff

Pending: `rename-allsiterepos`, in `handoff/2026-10-28-rename-allsiterepos/` (see the README.md in that folder). Only the jsDelivr owner in the two quote-builder files changes (`TheReeferGarden` becomes `allsiterepos`). Paste the prompt only AFTER the GitHub account rename is done.

Previous: bundle8, md5 `647bce0a57edc87dece9e7ed3ea3688d`, 724,716 bytes, in `handoff/2026-10-28-bundle8/` (matches the site repo main when this was staged).

Before that: bundle7, md5 `cbf260374807a4aa63cc8d194f307b38`, 724,128 bytes, live (verified 2026-10-28). Folder `handoff/2026-10-28-bundle7/`.

The site repo is a full app. Static pages live under `public/`.

| Files (in `handoff/2026-10-28-rename-allsiterepos/`) | md5 | Bytes | Destination in `hotwiredcaraudio-site` | Status |
|---|---|---|---|---|
| `index.html` | `57fe4dfe6d2ed8ec1fd7d3217055cf01` | 724,710 | `public/quote/index.html` | staged, waiting for the rename |
| `Hotwired-Quote-Builder.html` | `57fe4dfe6d2ed8ec1fd7d3217055cf01` | 724,710 | `public/quote/Hotwired-Quote-Builder.html` | staged, waiting for the rename |

The two quote-builder files are byte-identical twins, so both rows carry the same md5 and byte count.

## Ready-to-paste prompt for the HW Grok Build chat

````markdown
Pull the latest main from allsiterepos/hotwired-car-audio-quote-catalog.

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
