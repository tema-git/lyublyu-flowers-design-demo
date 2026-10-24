# «Люблю» — independent design demo

Flower shop «Люблю»: Moscow, 1st Vrazhsky Lane, 4. Phone: +7 910 412-48-04. Email: kotovastacy@gmail.com.

Source record: `outputs/no_site_selected_500.json`, zero-based index 10. Verified live spreadsheet row: 12 (24 October 2026).

Contact sources:
- https://urbanplaces.su/ru_moskva/moskva/card-70000001090614915-liubliu
- https://mebelhomeroom.ru/flowers/moskva/kievskaya — matching name, address, and phone.

This is an independent design concept, not the company's official website. Illustrated bouquets are not a live inventory. No hours or prices are asserted. The enquiry form validates inputs, displays an explicit demo confirmation, and clears the name and phone. It sends no personal data. The bouquet composer stores the idea locally only after the user presses its save button.

## Navigation and interaction

Sticky header at every viewport, visible contact action, accented primary buttons, transparent text-selection background.

Every directional arrow uses the same right-pointing SVG path. Rest: -45 degrees. Hover/focus: exactly 0 degrees. ScrollTrigger never animates arrows. Reduced motion: always horizontal.

Cursor reactions across all six main sections:
- `.hero`: large photograph, botanical emblem, small flower on the note.
- `.feeling-strip`: accent text color and flower dividers.
- `.moods`, `.mood-card`: petals, contour, bouquet movement inside stationary cards.
- `.garden-section`: botanical sprigs; card flowers respond to hover/focus while hit targets remain stationary.
- `.composer-section`: bouquet SVG and decorative seal. Form inputs remain stationary; focus adds a highlight.
- `.manifesto`: large flower, petals, and a botanical contour.
- `.visit`: flower and street lines on the illustrative map, soft map framing.
- `.callback-panel`: decorative botanical atmosphere; text, controls and buttons do not move.
- `.footer`: floral logo mark.

Scene CSS variables: `--scene-x`, `--scene-y`, `--scene-turn`, `--pointer-x`, `--pointer-y`. Active flag: `.is-pointer-active`. Decoration uses `aria-hidden` and `pointer-events:none`. The native cursor and text selection are preserved. requestAnimationFrame stops after settling, when the scene leaves the viewport, and when the tab is hidden. Touch uses focus/active feedback; reduced motion disables movement. Pointer effects use individual translate/rotate properties on decorative layers, separate from GSAP transforms.

Static checks: `node --check app.js`, `git diff --check`, old brand/contact/hours checks. The botanical kind identifier `protea` denotes a flower species, not the previous company brand. Browser QA and deployment are performed separately.
