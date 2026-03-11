---
name: marinade-product-design
description: Build internal tools and dashboards for Marinade Finance. Uses React + TypeScript, Shadcn UI, Tailwind CSS, Lucide React icons, and Geist typeface. Follows Marinade's dark-mode-first visual language with teal accents, glassy card surfaces, and a strict design token system with full light/dark mode support. Enforces component conventions, typography rules, and layout patterns specific to Marinade's products.
---

You are helping build an internal tool/dashboard for Marinade Finance.

## DESIGN SYSTEM RULES — follow these strictly

### Stack
- React + TypeScript
- Shadcn UI (https://ui.shadcn.com) as the base component library
- Tailwind CSS for utility styling
- Lucide React for all icons
- Geist as the primary typeface (import via `next/font/google` or CDN)

### Color Tokens — THE SOURCE OF TRUTH

The canonical token file is `tokens.json` bundled with this skill. When scaffolding a project, copy it into the project root and generate CSS variables + Tailwind config from it.

**Every color in the system has a light and dark variant.** Dark mode is the default. Light mode must also work. Use CSS custom properties that switch based on a `.dark` / `.light` class on `<html>` or via `prefers-color-scheme`.

#### Semantic Color Tokens

| Token | Light | Dark | Usage |
|-------|-------|------|-------|
| `background` | `#FFFFFF` | `#030707` | Page body background |
| `background-page` | `#F3F7F7` | `#050D0C` | Page-level surface behind cards |
| `foreground` | `#182120` | `#F6F9F9` | Primary text color |
| `card` | `#FFFFFF` | `#050D0C` | Card surface |
| `card-foreground` | `#081211` | `#F6F9F9` | Text on cards |
| `popover` | `#FFFFFF` | `#182120` | Dropdown/popover surface |
| `popover-foreground` | `#042F2E` | `#F6F9F9` | Text in popovers |
| `primary` | `#0C9790` | `#179F99` | Primary actions, brand accent (teal) |
| `primary-foreground` | `#F6F9F9` | `#042F2E` | Text on primary buttons |
| `secondary` | `#E7EEEF` | `#212C2B` | Secondary surfaces |
| `secondary-foreground` | `#3A4E4D` | `#F6F9F9` | Text on secondary |
| `tertiary` | `#DDE7E8` | `#3A4E4D` | Tertiary surfaces |
| `tertiary-foreground` | `#6F8383` | `#9AB1B2` | Text on tertiary |
| `muted` | `#F3F7F7` | `#111a19` | Muted backgrounds (stat cards, subtle surfaces) |
| `muted-foreground` | `#6C8383` | `#6C8383` | Muted text (same in both modes) |
| `accent` | `#E7EEEF` | `#212C2B` | Accent surfaces |
| `accent-foreground` | `#081211` | `#F0FDFA` | Text on accent |
| `destructive` | `#DC2626` | `#F87171` | Error, delete, danger |
| `info` | `#6366F1` | `#818CF8` | Informational (indigo) |
| `warning` | `#E59606` | `#FB923C` | Warning states (amber/orange) |
| `border` | `#DDE7E8` | `rgba(255,255,255,0.15)` | Default borders |
| `border-grid` | `#E7EEEF` | `rgba(255,255,255,0.06)` | Subtle grid/divider lines |
| `input` | `#E7EEEF` | `rgba(255,255,255,0.15)` | Input field borders |
| `ring` | `rgba(154,177,178,0.3)` | `rgba(111,131,131,0.5)` | Focus ring |

#### Alpha Variants
Tokens with `-20`, `-10`, `-90` suffixes are the base color at that opacity percentage. Use them for:
- `primary-20` — subtle primary tint backgrounds
- `destructive-20` — error badge backgrounds
- `warning-10` / `warning-20` — warning badge backgrounds
- `primary-90` — slightly transparent primary for overlays

#### Chart Colors (5-color palette)
| Token | Light | Dark |
|-------|-------|------|
| `chart-1` | `#0C9790` | `#3AC3BC` |
| `chart-2` | `#818CF8` | `#6366F1` |
| `chart-3` | `#FBBF24` | `#F59E0B` |
| `chart-4` | `#C084FC` | `#A855F7` |
| `chart-5` | `#FB7185` | `#F43F5E` |

#### Tag Colors (4-color palette)
| Token | Light | Dark |
|-------|-------|------|
| `tag-1` | `#CA8A04` (yellow) | `#FACC15` |
| `tag-2` | `#EA580C` (orange) | `#FB923C` |
| `tag-3` | `#64748B` (slate) | `#CBD5E1` |
| `tag-4` | `#3B82F6` (blue) | `#60A5FA` |

Each tag also has a `-20` alpha variant for badge backgrounds.

#### Sidebar Tokens
| Token | Light | Dark |
|-------|-------|------|
| `sidebar-background` | `#FFFFFF` | `#081211` |
| `sidebar-foreground` | `#042F2E` | `#F6F9F9` |
| `sidebar-primary` | `#182120` | `#1D4ED8` |
| `sidebar-primary-foreground` | `#F6F9F9` | `#F6F9F9` |
| `sidebar-accent` | `#F3F7F7` | `#212C2B` |
| `sidebar-accent-foreground` | `#182120` | `#F6F9F9` |
| `sidebar-border` | `#F3F7F7` | `rgba(255,255,255,0.1)` |
| `sidebar-ring` | `#9AB1B2` | `#6F8383` |

#### CSS Variable Implementation

When scaffolding, generate this in `globals.css`:

```css
:root {
  --background: #FFFFFF;
  --background-page: #F3F7F7;
  --foreground: #182120;
  --card: #FFFFFF;
  --card-foreground: #081211;
  --primary: #0C9790;
  --primary-foreground: #F6F9F9;
  --secondary: #E7EEEF;
  --secondary-foreground: #3A4E4D;
  --muted: #F3F7F7;
  --muted-foreground: #6C8383;
  --accent: #E7EEEF;
  --accent-foreground: #081211;
  --destructive: #DC2626;
  --info: #6366F1;
  --warning: #E59606;
  --border: #DDE7E8;
  --input: #E7EEEF;
  --ring: rgba(154,177,178,0.3);
}

.dark {
  --background: #030707;
  --background-page: #050D0C;
  --foreground: #F6F9F9;
  --card: #050D0C;
  --card-foreground: #F6F9F9;
  --primary: #179F99;
  --primary-foreground: #042F2E;
  --secondary: #212C2B;
  --secondary-foreground: #F6F9F9;
  --muted: #111a19;
  --muted-foreground: #6C8383;
  --accent: #212C2B;
  --accent-foreground: #F0FDFA;
  --destructive: #F87171;
  --info: #818CF8;
  --warning: #FB923C;
  --border: rgba(255,255,255,0.15);
  --input: rgba(255,255,255,0.15);
  --ring: rgba(111,131,131,0.5);
}
```

Wire into `tailwind.config.ts`:
```ts
colors: {
  background: "var(--background)",
  "background-page": "var(--background-page)",
  foreground: "var(--foreground)",
  card: { DEFAULT: "var(--card)", foreground: "var(--card-foreground)" },
  primary: { DEFAULT: "var(--primary)", foreground: "var(--primary-foreground)" },
  secondary: { DEFAULT: "var(--secondary)", foreground: "var(--secondary-foreground)" },
  muted: { DEFAULT: "var(--muted)", foreground: "var(--muted-foreground)" },
  accent: { DEFAULT: "var(--accent)", foreground: "var(--accent-foreground)" },
  destructive: "var(--destructive)",
  info: "var(--info)",
  warning: "var(--warning)",
  border: "var(--border)",
  input: "var(--input)",
  ring: "var(--ring)",
}
```

### Fonts
- **Sans:** Geist
- **Serif:** PT Serif (rarely used, for special display text)
- **Mono:** Geist Mono (data, code, addresses, numbers)

### Component Conventions
- All components live in `/components/ui` (Shadcn pattern)
- Custom Marinade components extend Shadcn primitives — never replace them
- Use `cn()` utility for conditional class merging
- Prefer composition over prop-drilling

### Typography
- Use `font-variant-numeric: tabular-nums` for any dynamic numbers (timers, counters, prices, TVL, APY)
- Anti-aliased font smoothing (`-webkit-font-smoothing: antialiased`)
- `text-wrap: balance` on headings

### Icons
- Lucide React only. Import individually: `import { Wallet } from "lucide-react"`
- Size default: 16px inline, 20px standalone UI elements

### Visual Language
- Dark backgrounds, glassy card surfaces with subtle borders
- Teal primary accent — always use the `primary` token, never hardcode
- Rounded corners: `rounded-lg` (8px) for cards, `rounded-md` (6px) for buttons, `rounded-sm` (4px) for inputs
- Subtle shadows (`0 2px 10px rgba(0,0,0,0.05)`) and backdrop-blur on overlays
- Eased gradients over linear ones
- Hairline borders: use `border-grid` token or `ring-1 ring-white/10` patterns

### Dark / Light Mode
- Dark mode is the **default**
- Both modes must work using the token system
- Toggle via `.dark` / `.light` class on `<html>` or `prefers-color-scheme`
- Never use Tailwind `dark:` modifier for colors — all color switching happens through CSS variables
- Test both modes before shipping

### Animation
- Micro-interactions: 100-150ms
- Tooltips, dropdowns: 150-250ms
- Modals, drawers: 200-300ms
- Use `ease-out` for appearing elements, `ease-in-out` for movement
- Only animate `transform` and `opacity` — never layout properties
- Include `prefers-reduced-motion: reduce` fallbacks

### Data Display Patterns
- Use Geist Mono for all numerical data (balances, APY, TVL, addresses)
- Truncate Solana addresses: `AB1c...Xz9f` (4 prefix + 4 suffix)
- Format large numbers with locale-aware grouping (1,234,567.89)
- SOL values: 2-4 decimal places depending on context
- USD values: always 2 decimal places with `$` prefix
- Percentage values: 2 decimal places with `%` suffix
- Use green/red semantic colors for positive/negative changes

### Charts & Data Visualization

#### Library
- Use **Recharts** (`recharts`) for all charts — it's React-native, composable, and works with Shadcn patterns
- Wrap charts in a reusable `<ChartContainer>` component that handles responsive sizing and theme tokens

#### Chart Styling Rules
- **Always** use the `chart-1` through `chart-5` CSS variables for series colors — never hardcode
- Background: transparent or `var(--card)` — charts sit on card surfaces
- Grid lines: use `var(--border-grid)` (very subtle)
- Axis labels: `var(--muted-foreground)`, Geist Mono, 11-12px
- Axis ticks: `var(--border-grid)` or hidden
- No chart borders — let the card handle containment

#### Interactivity Patterns — CRITICAL

All chart interactive elements (tooltip, crosshair, active dot) must be **hidden by default** and only appear on hover. Never show them statically.

- **Tooltips**: Hidden by default (`opacity: 0`). On `mousemove` over the chart area, show with `opacity: 1` and `transition: opacity 150ms ease-out`. On `mouseleave`, hide again. Style: `var(--popover)` background, `var(--popover-foreground)` text, `var(--border)` border, `rounded-lg`, `shadow-lg`, `pointer-events: none`. Use Geist Mono for values. Position tooltip to follow the cursor X, clamped to chart bounds so it never overflows.
- **Crosshair line**: Hidden by default (`display: none`). On hover, show a vertical dashed line at the nearest data point X. Use `var(--border)` stroke, `strokeDasharray="4 4"`, spanning full chart height.
- **Active dot**: Hidden by default (`display: none`). On hover, show at the nearest data point. Style: `var(--background)` fill, 2.5px border in series color, radius 5px. Snaps to nearest data point — never free-floats between points. **CRITICAL: Never place the dot inside an SVG that uses `preserveAspectRatio="none"` — this distorts circles into ellipses.** Always render the dot as an absolutely-positioned HTML `<div>` with `border-radius: 50%` outside the SVG, converting SVG coordinates to pixel coordinates via `(svgX / viewBoxWidth) * containerWidth` and `(svgY / viewBoxHeight) * containerHeight`. Use `transform: translate(-50%, -50%)` to center it on the data point.
- **Hover on series**: When multiple series exist, dim non-hovered series to 30% opacity. Active series stays at full opacity. Transition: `opacity 150ms ease-out`.
- **Cursor**: Set `cursor: crosshair` on the chart container.
- **Legend**: Clickable to toggle series visibility. Use `var(--muted-foreground)` for labels, chart color dots (8px circles). On click, toggle the series and update the legend item opacity.
- **Brush/zoom**: For time-series > 30 data points, add a brush selector at the bottom using `var(--secondary)` for the handle.

**Implementation with Recharts:**
```tsx
<Tooltip
  content={<CustomTooltip />}  // Never use default Recharts tooltip
  cursor={{ stroke: 'var(--border)', strokeDasharray: '4 4' }}
  isAnimationActive={false}
/>
<Area
  activeDot={{ r: 5, fill: 'var(--background)', stroke: 'var(--chart-1)', strokeWidth: 2.5 }}
  dot={false}  // No dots on the line itself — only active dot on hover
/>
```

**CustomTooltip must:**
- Use `var(--popover)` bg, `var(--border)` border, `rounded-lg`, `shadow-lg`
- Show date in muted-foreground, value in Geist Mono bold, change % in primary/destructive
- Never render when not active (`if (!active || !payload) return null`)

#### Chart Types & When to Use
| Type | Use For | Notes |
|------|---------|-------|
| Area chart | TVL over time, staking trends | Fill with `chart-1` at 10% opacity, stroke at full |
| Line chart | APY history, price trends | 2px stroke, smooth curve (`type="monotone"`) |
| Bar chart | Validator comparison, distribution | `rounded-t-sm` on bars, 4px gap between |
| Stacked bar | Composition breakdown | Use chart-1 through chart-5 in order |
| Pie/donut | Portfolio allocation, vote share | Donut preferred (60% inner radius), no more than 5 slices |
| Sparkline | Inline mini-charts in tables | 40px tall, no axes, single color, `strokeWidth={1.5}` |

#### Time-Series Conventions
- X-axis: Show 5-7 date labels max, use relative format ("Mar 1", "Mar 8") for < 3 months, month format ("Jan", "Feb") for > 3 months
- Y-axis: Auto-scale with 20% padding above max value. Use compact notation for large numbers (1.2M, 450K)
- Default range selector: 7d / 30d / 90d / 1y / All — styled as tab pills. **Selected**: `background: var(--secondary)`, `color: var(--foreground)` (grey fill with readable text). **Unselected**: `background: transparent`, `color: var(--muted-foreground)` (no background, just muted text). Never use `primary` (green) for tab selection — tabs use neutral grey to avoid competing with chart colors.
- Loading state: Skeleton shimmer using `var(--muted)` with a subtle pulse animation

#### Formatting in Charts
- SOL values in tooltips: `1,234.56 SOL` (Geist Mono)
- USD values: `$1,234.56`
- Percentages: `7.12%`
- Epoch numbers: `#567` (mono, with hash prefix)

### Breakpoints
| Name | Width |
|------|-------|
| sm | 640px |
| md | 768px |
| lg | 1024px |
| xl | 1280px |
| 2xl | 1536px |

## UI Quality Audit (Auto-Fix Mode)

When building or reviewing any Marinade UI, automatically check for and fix these issues without being asked. This integrates the **frontend-design** skill's quality standards into Marinade's design system.

### Color & Theme Issues — Auto-Fix
- Hardcoded hex/rgb values → Replace with CSS variable tokens
- Missing dark mode support → Wire through CSS variables
- Low contrast text on backgrounds → Swap to correct foreground token
- Inconsistent opacity values → Use token alpha variants (primary-20, etc.)
- `dark:` Tailwind modifiers for colors → Remove, use CSS variable switching

### Typography Issues — Auto-Fix
- Non-Geist fonts → Replace with Geist (sans) or Geist Mono (data)
- Dynamic numbers without `tabular-nums` → Add `font-variant-numeric: tabular-nums`
- Missing `-webkit-font-smoothing: antialiased` → Add to body/root
- Headings without `text-wrap: balance` → Add it
- Font weight change on hover → Remove (causes layout shift)
- Inputs under 16px → Set minimum 16px to prevent iOS auto-zoom

### Layout & Spacing Issues — Auto-Fix
- Inconsistent border-radius → Apply token scale (lg/md/sm)
- `z-index: 9999` or arbitrary z values → Use a fixed scale or `isolation: isolate`
- `border` property for subtle dividers → Switch to `border-grid` token or box-shadow
- Missing `isolation: isolate` on stacking contexts → Add it
- Inconsistent card padding → Standardize to 24px (or 16px for compact)

### Animation Issues — Auto-Fix
- `transition: all` → Specify explicit properties
- Animations > 300ms for standard UI → Reduce to token timing
- Missing `prefers-reduced-motion` → Add media query fallback
- Animating `width`, `height`, `padding`, `margin` → Refactor to `transform`/`opacity`
- `ease-in` on UI elements → Switch to `ease-out` (entering) or `ease-in-out` (moving)

### Accessibility Issues — Auto-Fix
- Touch targets < 44px → Increase with padding
- Icon buttons without `aria-label` → Add descriptive label
- Missing focus-visible styles → Add using `ring` token
- Color-only status indicators → Add icon or text supplement
- Missing hover states on interactive elements → Add subtle background shift

### Chart Issues — Auto-Fix
- Charts without tooltips → Add custom styled tooltip
- Static charts that should be interactive → Add hover/click handlers
- Hardcoded chart colors → Replace with chart-1 through chart-5 tokens
- Missing loading states → Add skeleton shimmer
- Unformatted axis labels → Apply Geist Mono + compact number formatting
- Legend not clickable → Make series toggleable

### Marinade-Specific Issues — Auto-Fix
- Solana addresses shown in full → Truncate to `XXXX...XXXX` (4+4)
- Unformatted SOL amounts → Add locale grouping + 2-4 decimals
- Missing `$` on USD values → Add prefix with 2 decimal places
- Percentage without `%` suffix → Add it
- Positive changes not colored green → Apply `primary` token
- Negative changes not colored red → Apply `destructive` token

## Starting a New Tool

When the user starts a new internal tool project, ask these questions before scaffolding:

1. **What is this tool for?** (2 sentence description)
2. **What are the 3 main data entities or concepts this tool manages?**
3. **Should this have a sidebar nav or top nav?**
4. **Are there any specific pages or views I need first?**

Then scaffold the project with:
- Layout shell (dark mode default, Geist font loaded, light mode toggle)
- Navigation (sidebar or top, based on answer)
- Placeholder home dashboard with stat cards and an empty state
- 3 starter components relevant to the tool's purpose
- Token-based Tailwind config wired to CSS variables (from `tokens.json`)
- `cn()` utility and base Shadcn setup
- Theme provider with dark/light mode toggle

## Code Quality

- Never introduce unused imports or dead code
- All components must be typed — no `any`
- Extract repeated patterns into shared components after 2+ uses
- Keep files under 200 lines — split into composition when larger
- Use React Server Components where possible (Next.js App Router)
- Client components must have `"use client"` directive
