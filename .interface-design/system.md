# Melbourne Laneway Journal — Design System

## Direction

**Who:** A couple from Singapore browsing their upcoming Melbourne trip together — excited, planning mode, checking costs and imagining places.

**Task:** Navigate day-by-day through a 10-day itinerary. Find what happens when, how to get there, what it costs, what to book. Feel confident every detail is sorted.

**Feel:** Like opening a beautifully made travel journal — warm, curated, personal. Not a spreadsheet, not a travel agency upsell. The anticipation of a trip planned just for them.

**Metaphor:** A personal travel journal grounded in Melbourne's material world. The page is limestone parchment. The sidebar is a bluestone laneway at dusk. The timeline is a tram route map. Cards are postcards laid on a table.

## Signature

**Tram-route timeline.** Each day is a route. Each activity is a stop. The vertical connector is a tram track (3px warm line). Color-coded dots reference Melbourne's tram route diagram aesthetics. Sidebar day numbers are styled as outlined tram stops, filled gold when active.

Five places the signature appears:
1. Timeline vertical connector (3px warm track)
2. Timeline dots (14px circles with halo rings, color-coded by activity type)
3. Sidebar nav day-num circles (outlined → filled tram stops)
4. Tram-gold accent throughout (heritage tram livery)
5. Times in monospace along the track (like station departure boards)

## Palette

Derived from Melbourne's physical world — not applied to it.

### Primary

| Token | Hex | Source |
|-------|-----|--------|
| `--bluestone` | `#2C363F` | Heritage basalt pavers and facades |
| `--limestone` | `#FAF6EE` | Twelve Apostles, Victorian facades, warm paper |
| `--cream` | `#FFFCF7` | Card surfaces — lighter than limestone |
| `--tram-gold` | `#C5933A` | Heritage tram livery, autumn leaves |
| `--tram-gold-soft` | `#E8C97A` | Gold highlights, secondary accents |

### Activity Types

| Token | Hex | Source |
|-------|-----|--------|
| `--ocean` | `#3D6B7E` | Southern Ocean — transport, links |
| `--eucalyptus` | `#6B8F71` | Australian bush — nature, success |
| `--terracotta` | `#B4654A` | Richmond/Fitzroy brick — food |
| `--plum` | `#8B6E99` | Arts Precinct dusk — culture |
| `--laneway-red` | `#C4384E` | Street art energy — warnings |

### Text Hierarchy (coffee espresso)

| Token | Hex | Role |
|-------|-----|------|
| `--ink` | `#3D2E1F` | Primary text |
| `--ink-secondary` | `#5C4F42` | Descriptions, supporting text |
| `--ink-tertiary` | `#8A7E72` | Metadata, labels, muted |
| `--ink-ghost` | `#B5ADA3` | Placeholder, disabled |

### Borders

| Token | Value | Role |
|-------|-------|------|
| `--stitch` | `rgba(60,46,31,0.10)` | Standard separation |
| `--stitch-soft` | `rgba(60,46,31,0.06)` | Subtle separation |
| `--stitch-strong` | `rgba(60,46,31,0.18)` | Emphasis |

## Depth

**Strategy: Subtle warm shadows.** Cards float like postcards on a table.

| Token | Value |
|-------|-------|
| `--postcard` | `0 1px 4px rgba(60,46,31,0.06), 0 6px 16px rgba(60,46,31,0.04)` |
| `--postcard-lift` | `0 6px 24px rgba(60,46,31,0.10)` |

No mixed strategies. All shadows use warm `rgba(60,46,31)` base. Borders are separation, shadows are elevation.

## Typography

| Role | Font | Weight | Size | Why |
|------|------|--------|------|-----|
| Display/headlines | DM Serif Display | 400 | 28-34px | Editorial travel magazine quality |
| Activity titles | DM Serif Display | 400 | 17-18px | Connects each card to the journal metaphor |
| Body | DM Sans | 400 | 13.5-15px | Warm humanist sans, same design family |
| Labels/meta | DM Sans | 600 | 10-11px | Uppercase, wide tracking for section headers |
| Costs/times | JetBrains Mono | 400-600 | 12-18px | Tabular figures for financial data and timetables |

Google Fonts load:
```html
<link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=DM+Serif+Display&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet">
```

## Spacing

**Base: 4px.** All spacing uses multiples.

| Token | Value | Use |
|-------|-------|-----|
| `--sp-1` | 4px | Micro gaps (icon-text) |
| `--sp-2` | 8px | Tight component spacing |
| `--sp-3` | 12px | Standard component padding |
| `--sp-4` | 16px | Card internal padding |
| `--sp-5` | 20px | Card padding, sidebar padding |
| `--sp-6` | 24px | Section spacing |
| `--sp-8` | 32px | Major section gaps |
| `--sp-10` | 40px | Page margins |
| `--sp-12` | 48px | Hero padding |

## Radius

| Token | Value | Use |
|-------|-------|-----|
| `--r-sm` | 6px | Buttons, action links, small badges |
| `--r-md` | 10px | Callouts, summary items |
| `--r-lg` | 14px | Cards, overview cards, compare cards |
| `--r-pill` | 100px | Tags, hero badge, weather badge |

## Component Patterns

### Sidebar (240px fixed)
- Background: `--bluestone`
- Header: DM Serif Display title in `--tram-gold`
- Nav buttons: 13px DM Sans, `rgba(255,255,255,0.55)` default
- Active state: `--tram-gold-bg` background, gold border-left 3px, gold text
- Day numbers: 26px circles, 2px outlined border, filled gold on active
- Footer: JetBrains Mono, 11px, very low opacity

### Activity Card
- Surface: `--cream` with `--postcard` shadow
- Border: `--stitch-soft` (barely visible)
- Image: 180px height, warm placeholder gradient `#E8E0D4 → #D6CEC2`
- Title: DM Serif Display 18px
- Description: DM Sans 13.5px in `--ink-secondary`
- Hover: lift -1px with `--postcard-lift` shadow

### Timeline Item
- Time: JetBrains Mono 13px in `--ink-tertiary`
- Track: 3px wide, `--stitch` color, 2px radius
- Stop marker: 14px circle, 3px limestone border, 2px color halo
- Stop colors: gold (default), ocean (transport), terracotta (food), eucalyptus (nature), plum (culture)

### Atmosphere Tags
- Pill-shaped (`--r-pill`), 11px 600 weight
- Warm-shifted colors tied to Melbourne palette
- Key pairs: quiet=#E8F0E9/#3D6B4A, busy=#F5EBD8/#8B6B2F, scenic=#DCF0E0/#3D6B4A, coastal=#D8ECF3/#2C5F75

### Note Callouts
- Tip: eucalyptus-soft bg, eucalyptus left border
- Warn: warm tan `#F5EBD8` bg, tram-gold left border
- Info: ocean-soft bg, ocean left border
- All: 3px left border, 10px radius, 13px text

### Day Summary
- Same card surface treatment as activity cards
- Title: DM Serif Display 16px
- Grid of summary items on limestone background
- Values: JetBrains Mono 16px bold

## Design Decisions

- **Dark sidebar kept** — intentional: it frames content like a book binding frames pages, reinforcing the journal metaphor
- **Serif for headlines only** — body text stays sans-serif for screen readability at small sizes
- **No texture/noise on backgrounds** — warm colors carry the personality without visual noise
- **Card hover lifts -1px** — subtle enough to feel intentional, not bouncy
- **Monospace for all financial/time data** — tabular alignment matters for cost comparison and timetables
