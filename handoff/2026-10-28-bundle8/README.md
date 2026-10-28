# Bundle8 handoff (2026-10-28)

Quote builder update for hotwiredcaraudio-site. Built on the live bundle7 page (md5 `cbf260374807a4aa63cc8d194f307b38`, 724,128 bytes).

## What changed

- Slimmer sticky "Add selected to quote / Done with this area" row on phones only (screens 600px wide or less). One CSS block, added right after the existing `#stepGear .wizard-actions` rules. Nothing else differs from bundle7.
- At 390px wide the row drops from about 108px to 76px tall (about 122px to 85px once the "Next step" cue shows), so more cards show. Buttons are at least 44px tall (the Done button was 40px before). Same buttons, same status line, same next-step cue, no text or controls hidden or changed.
- Desktop (above 600px) is byte-for-byte the same rules as before; measured identical at 1280px.

## Files and destinations

| File in this folder | md5 | Bytes | Destination in `hotwiredcaraudio-site` |
|---|---|---|---|
| `index.html` | `647bce0a57edc87dece9e7ed3ea3688d` | 724,716 | `public/quote/index.html` |
| `Hotwired-Quote-Builder.html` | `647bce0a57edc87dece9e7ed3ea3688d` | 724,716 | `public/quote/Hotwired-Quote-Builder.html` |

The two files are byte-identical twins. Copy byte-for-byte. No editing, merging, or regenerating. Do not change anything else in the site repo.

## Must keep

- SEO tags (meta description, canonical, og:url, og:image, twitter:image)
- Fixed step bar
- 10-digit phone check
- 14-key Web3Forms payload (access_key, name, email, phone, first_name, last_name, subject, message, vehicle, option, radio, parts_total, from_name, botcheck)
- CP3-LEX17 hidden page-side (bundle7)
- CDN line: `var HW_DATA_BASE_DEFAULT = 'https://cdn.jsdelivr.net/gh/TheReeferGarden/hotwired-car-audio-quote-catalog@main/';`

## Tested

Headless Chrome at 390, 375, 360 and 1280 wide with Web3Forms intercepted (no real quote sent): b5 suite 57 pass / 0 fail, b2 suite 76 pass / 0 fail (14 payload keys, phone check, sticky row, last card reachable above the row).
