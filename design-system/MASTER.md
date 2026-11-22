# Nastya & Max — Home Dog Sitting · Design System (MASTER)

Source of truth for colour, type, spacing and motion. Page-level overrides go in `design-system/pages/<page>.md`.

Reference: editorial mentor landing page (warm off-white, serif display headline with an italic accent word,
narrow left-aligned text column, numbered section eyebrows, two-tone sans headings, comparison table with a
highlighted middle column, alternating review cards, serif CTA) + the "lanyard rail" flip-badge component.

## Product / tone
Small, personal, trusted. Two people, their flat, their walks. Calm and warm, never cutesy. Real photos only.

## Colour tokens (CSS custom properties in `index.html :root`)
| Token | Hex | Use |
|---|---|---|
| `--bg` | `#F5F2ED` | page background (warm paper) |
| `--paper` | `#FFFFFF` | cards, table, badges |
| `--ink` | `#151413` | primary text, black buttons |
| `--ink-2` | `#4F4A44` | body copy (≥ 7:1 on bg) |
| `--muted` | `#8C857C` | second line of headings, large text only (≥ 3:1) |
| `--muted-sm` | `#6E675F` | small labels, dates (≥ 4.5:1) |
| `--line` | `#E4DED5` | hairlines |
| `--band` | `#ECE7DF` | highlighted table column |
| `--accent` | `#B4432E` | italic accent words, checks, reviewer names, CTA (5.7:1 on bg) |
| `--accent-soft` | `#F2E1DA` | avatar circles, chip dots |
| `--terracotta` `--sage` `--navy` `--mustard` | `#C4573F` `#6E8B76` `#2E4357` `#D4A343` | lanyard straps + badge bands only |
| `--telegram` (`--telegram-hover`) | `#26A5E4` (`#1C96D3`) | Telegram button only, with `--ink` text (≥ 5.5:1) |
| `--whatsapp` (`--whatsapp-hover`) | `#25D366` (`#1FBE5B`) | WhatsApp button only, with `--ink` text (≥ 7.5:1) |

No gradients except material textures (metal rail, woven strap). No purple/pink.

## Typography
- Display: **Cormorant Garamond** 500 / italic 500 (has Cyrillic + Spanish glyphs). Hero & CTA only.
- UI/body: **Onest** 400/500/600 (Cyrillic + Latin-ext).
- Hero: `clamp(56px, 9.6vw, 144px)`, line-height .9, tracking -0.02em.
- H2: Onest 500 `clamp(28px, 3.6vw, 44px)`, line-height 1.08, tracking -0.025em; second line in `--muted`.
- Body 16/1.65 `--ink-2`. Eyebrow 11px, uppercase, tracking .16em, `--ink-2` (darkened from `--muted-sm` for readability, client request 2026-11-16).

## Spacing & layout
- Gutter `clamp(16px, 4vw, 40px)`; section padding `clamp(96px, 13vw, 176px)` block.
- Text column 680px (left-aligned, centred on page); wide blocks 1040px; page max 1200px.
- Asymmetric photo asides outside the text column at ≥ 1200px (About → right, Fit → left).
- Radius: cards 16px, photos 6px, chips/buttons pill.

## Motion
- Easing: entrances `cubic-bezier(0.16, 1, 0.3, 1)`; UI `cubic-bezier(0.4, 0, 0.2, 1)`.
- Durations: hover 0.2s; reveals 0.7s with 70ms stagger; badge flip 0.8s.
- Lanyards: spring-damped pendulum (k 38, c 3.2) + pull spring (k 140, c 9); transforms only.
- `prefers-reduced-motion`: reveals instant, no floating chips, no physics, flip without rotation.

## Anti-patterns
No emoji icons (inline SVG only), no stock photos, no invented facts (prices, locations, counts),
no breed names on photos unless the breed is clear, no AI gradients, no bouncy UI except the physical lanyards.
