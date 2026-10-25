# «Люблю» — design refinements, 25 October 2026

The existing flower-shop concept is preserved: an expressive pink canvas, large floral photography, plum text, lime actions on dark surfaces, and illustrated bouquets. The audience is someone choosing a mood or beginning a conversation with a florist. Primary action: build an idea, then call or write. The website remains an independent demo, with no real booking or submission.

## References and deliberate adaptations

- [Refero / Adam Lippes](https://styles.refero.design/style/cdc4a162-cefa-49a1-81e7-4857e421ae24): retain the established photograph as the hero's main material and reduce redundant introductory UI. The monochrome palette and small labels are deliberately not copied; this site keeps floral color and readable Russian typography. Public design-system text inspected on 25 October 2026.
- [21st / Spotlight Card by Hossain Jahed](https://21st.dev/@jahed/components/spotlight-card): borrow the described relationship between local pointer coordinates and a decorative light, not the React component. The public page describes CSS custom properties; its component source requires an account and was not imported. This implementation is original vanilla JS/CSS, with stationary buttons and native text selection.
- [MotionSites / Cursor-tracking lesson](https://motionsites.ai/lesson/cursor-tracking-website-with-motionsites): adapt bounded input-to-artwork response across sections. No video scrubbing, paid prompt, external font, custom cursor, or generated component is reused. The new rose, SVG petals, shadows and light react locally.

Source pages inform composition and behavior; reading them is not a claim that their live previews were tested. Browser QA of this site's actual implementation is performed separately.

## Visual system

- Canvas `#f8c9cf`; ink `#3b1733`; berry action `#842751`; light paper `#fffaf4`; foliage `#dae7c5`; lime emphasis `#edff95`.
- Existing locally served Golos Text, large headings, 18 px body, 16 px controls, 14 px secondary labels. Marquee 27–46 px; reduced-motion phrases 20 px.
- Existing maximum width 1320 px and established desktop/mobile section rhythm remain. Hero eyebrow is removed. The hero address is a meaningful map link; its unrelated circular arrow is removed.
- Original top-view rose SVG: irregular outer petals, nested folds and a curled center. It replaces every asterisk-like brand decoration, including header/footer, hero seal, note, marquee separators, garden label/card cover, constructor seal, manifesto, map, confirmation and favicon. `assets/rose-mark.svg` is the standalone master; inline copies allow lightweight CSS petal reactions.

## Interaction map

| Surface | Trigger and response | Bound and stable targets | Touch / keyboard | Reduced motion |
|---|---|---|---|---|
| Hero | Pointer shifts photo, rose seal and small rose; outer petals open | Photo 18 px, rose 42 px maximum; headings, address and CTA stationary | Tap/focus activates decorative response; map is a normal link | No tracking or petal movement |
| Phrase ribbon | Twelve floral phrases loop seamlessly, with matching repeated groups; hover pauses for reading/selection | Exact half-track translation; about 42 px/second; no scroll transform on same track | Explicit Pause/Play button; readable static accessible phrase text | All twelve phrases wrap, second copy hidden, no loop |
| Mood cards | Bouquet parallax, local light, changing art corner and rose contour | Up to 25 px decorative movement; card boundaries and labels stable | Focus/tap retains clear highlighting and selection | Static bouquet, color/focus feedback |
| Pair game | Botanical sprigs and card rose open/tilt; matching behavior unchanged | Only decorative SVG children move; card targets stable | Existing native buttons, focus state and game feedback | No decorative travel, full game retained |
| Bouquet composer | Bouquet/rose seal track pointer, frame brightens, selected choices and field focus respond | Illustration only; fields/range/submit stationary | Existing radios, range and save dialog | Static illustration, normal state feedback |
| Manifesto | Large rose, petals and contour respond to input; scroll scale preserved | Decorative rose only; heading and link stable | Focus activates atmosphere | Static rose |
| Visit / contact | Rose/map lines react; contact underline and background rose follow input; hovered/focused fields have an outline | No translation of text, links, inputs or submit | Visible focus and tap feedback | Static ornament and field outline |
| Footer / navigation | Rose petals and small mark respond on hover/focus | Link hit areas fixed; sticky Contacts retained | Native links and menu controls | No petal movement |

All decorative overlays use `pointer-events:none` and `aria-hidden`. Text selection still changes only letter color. Directional CTA arrows remain northeast at rest and rightward on hover/focus; no scroll-driven arrow rotation is introduced.

The existing finite requestAnimationFrame interpolation stops when settled, offscreen, hidden, or blurred. The marquee uses one CSS transform animation, paused offscreen, in a hidden tab, on hover, or by its accessible control. Reduced motion removes the loop. No new library or runtime dependency was added.

## Preserved functional scenarios and checks

The pair game retains automatic mismatch closing after one second, six-pair victory, and reset. The bouquet constructor retains its explicit local-save action. The demo callback form retains validation, honest success copy, clearing of personal inputs and retry. Sticky header, contact anchor offsets, accent actions and transparent text selection remain.

Static checks completed after this update: JavaScript syntax, Git whitespace, unique HTML IDs, absence of the removed hero label and circular arrow, twelve phrases repeated exactly twice, no asterisk glyphs, and XML parsing of both new SVG assets. Browser interaction, viewport and publication checks are owned by the parent task.
