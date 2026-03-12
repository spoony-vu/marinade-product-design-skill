---
name: marinade-product-design
description: Build internal tools and dashboards for Marinade Finance. Uses React + TypeScript, Shadcn UI, Tailwind CSS, Lucide React icons, and Geist typeface. Follows Marinade's visual language with teal accents, clean card surfaces, and a strict design token system with full light/dark mode support (light default). Enforces component conventions, typography rules, and layout patterns specific to Marinade's products.
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

The full token definitions are embedded below as JSON. When scaffolding a project, generate CSS variables + Tailwind config from these tokens.

**Every color in the system has a light and dark variant.** Light mode is the default. Dark mode must also work. Use CSS custom properties that switch based on a `.dark` / `.light` class on `<html>` or via `prefers-color-scheme`.

#### tokens.json (embedded)

```json
{
  "colors": {
    "background":           { "light": "#FFFFFF", "dark": "#030707" },
    "background-page":      { "light": "#F3F7F7", "dark": "#050D0C" },
    "foreground":           { "light": "#182120", "dark": "#F6F9F9" },
    "card":                 { "light": "#FFFFFF", "dark": "#050D0C" },
    "card-foreground":      { "light": "#081211", "dark": "#F6F9F9" },
    "popover":              { "light": "#FFFFFF", "dark": "#182120" },
    "popover-foreground":   { "light": "#042F2E", "dark": "#F6F9F9" },
    "primary":              { "light": "#0C9790", "dark": "#179F99" },
    "primary-20":           { "light": "#0C979026", "dark": "#179F9933" },
    "primary-90":           { "light": "#0C9790E6", "dark": "#179F99E6" },
    "primary-foreground":   { "light": "#F6F9F9", "dark": "#042F2E" },
    "secondary":            { "light": "#E7EEEF", "dark": "#212C2B" },
    "secondary-foreground": { "light": "#3A4E4D", "dark": "#F6F9F9" },
    "tertiary":             { "light": "#DDE7E8", "dark": "#3A4E4D" },
    "tertiary-foreground":  { "light": "#6F8383", "dark": "#9AB1B2" },
    "muted":                { "light": "#F3F7F7", "dark": "#111a19" },
    "muted-foreground":     { "light": "#6C8383", "dark": "#6C8383" },
    "accent":               { "light": "#E7EEEF", "dark": "#212C2B" },
    "accent-foreground":    { "light": "#081211", "dark": "#F0FDFA" },
    "destructive":          { "light": "#DC2626", "dark": "#F87171" },
    "destructive-20":       { "light": "#DC262633", "dark": "#F871714D" },
    "info":                 { "light": "#6366F1", "dark": "#818CF8" },
    "info-20":              { "light": "#6366F133", "dark": "#818CF84D" },
    "warning":              { "light": "#E59606", "dark": "#FB923C" },
    "warning-20":           { "light": "#E5960633", "dark": "#FB923C33" },
    "warning-10":           { "light": "#E596061A", "dark": "#FB923C33" },
    "border":               { "light": "#DDE7E8", "dark": "#FFFFFF26" },
    "border-grid":          { "light": "#E7EEEF", "dark": "#FFFFFF0F" },
    "input":                { "light": "#E7EEEF", "dark": "#FFFFFF26" },
    "ring":                 { "light": "#9AB1B24D", "dark": "#6F838380" },
    "sidebar-background":          { "light": "#FFFFFF", "dark": "#081211" },
    "sidebar-foreground":          { "light": "#042F2E", "dark": "#F6F9F9" },
    "sidebar-primary":             { "light": "#182120", "dark": "#1D4ED8" },
    "sidebar-primary-foreground":  { "light": "#F6F9F9", "dark": "#F6F9F9" },
    "sidebar-accent":              { "light": "#F3F7F7", "dark": "#212C2B" },
    "sidebar-accent-foreground":   { "light": "#182120", "dark": "#F6F9F9" },
    "sidebar-border":              { "light": "#F3F7F7", "dark": "#FFFFFF1A" },
    "sidebar-ring":                { "light": "#9AB1B2", "dark": "#6F8383" },
    "chart-1":  { "light": "#0C9790", "dark": "#3AC3BC" },
    "chart-2":  { "light": "#818CF8", "dark": "#6366F1" },
    "chart-3":  { "light": "#FBBF24", "dark": "#F59E0B" },
    "chart-4":  { "light": "#C084FC", "dark": "#A855F7" },
    "chart-5":  { "light": "#FB7185", "dark": "#F43F5E" },
    "tag-1":    { "light": "#CA8A04", "dark": "#FACC15" },
    "tag-1-20": { "light": "#EAB30826", "dark": "#FACC1526" },
    "tag-2":    { "light": "#EA580C", "dark": "#FB923C" },
    "tag-2-20": { "light": "#EA580C26", "dark": "#FB923C26" },
    "tag-3":    { "light": "#64748B", "dark": "#CBD5E1" },
    "tag-3-20": { "light": "#64748B26", "dark": "#CBD5E126" },
    "tag-4":    { "light": "#3B82F6", "dark": "#60A5FA" },
    "tag-4-20": { "light": "#3B82F626", "dark": "#60A5FA26" }
  },
  "fonts": {
    "sans":  "Geist",
    "serif": "PT Serif",
    "mono":  "Geist Mono"
  },
  "breakpoints": { "sm": 640, "md": 768, "lg": 1024, "xl": 1280, "2xl": 1536 },
  "containers": { "3xs": 256, "2xs": 288, "xs": 320, "sm": 384, "md": 448, "lg": 512, "xl": 576, "2xl": 672, "3xl": 768, "4xl": 896, "5xl": 1024 },
  "shadow": { "offset-x": 0, "offset-y": 2, "blur-radius": 10, "spread-radius": 0, "color": "#0000000D" }
}
```

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
- Light mode is the **default**
- Both modes must work using the token system
- Toggle via `.dark` class on `<html>` or `prefers-color-scheme`
- Never use Tailwind `dark:` modifier for colors — all color switching happens through CSS variables
- Test both modes before shipping

### Animation & Motion (from /emil-design-engineering)

#### Decision: Should I Animate This?
```
Will users see this 100+ times daily?
├── Yes → Don't animate (e.g. sidebar toggle, frequent actions)
└── No
    ├── Is this user-initiated? → Animate with ease-out (150-250ms)
    └── Is this a page transition? → Animate (300-400ms max)
```

#### Decision: What Easing?
```
Is the element entering or exiting?
├── Yes → ease-out
└── No
    ├── Is it moving on screen? → ease-in-out
    └── Is it a hover/color change? → ease
```

#### Easing Tokens (use these, not generic `ease-out`)
```css
--ease-out-quint: cubic-bezier(0.23, 1, 0.32, 1);     /* Strong ease-out for modals, drawers */
--ease-out-cubic: cubic-bezier(0.215, 0.61, 0.355, 1); /* Standard ease-out for tooltips, dropdowns */
--ease-in-out-quart: cubic-bezier(0.77, 0, 0.175, 1);  /* Movement on screen */
```

#### Duration
| Element Type | Duration |
|---|---|
| Micro-interactions (button press, toggle) | 100-150ms |
| Tooltips, dropdowns, popovers | 150-250ms |
| Modals, drawers, sheets | 200-300ms |
| Page transitions | 300-400ms max |

#### Rules
- Only animate `transform` and `opacity` — never `height`, `width`, `padding`, `margin` (triggers layout)
- **Paired elements rule**: Elements that animate together (modal + overlay, tooltip + arrow) must share the same easing and duration
- Exit animations can be faster than entrances
- Avoid `blur` filters above 20px (expensive, especially Safari)
- `will-change: transform` for janky animations — remove when not animating
- Never use `transition: all` — specify explicit properties
- Avoid `ease-in` and `linear` for UI elements (feels sluggish/robotic)

#### Reduced Motion — MANDATORY
Every animation needs a `prefers-reduced-motion` fallback:
```css
@media (prefers-reduced-motion: reduce) {
  .animated { animation: none; transition: none; }
}
```

#### Theme Transitions
Switching dark/light mode must NOT trigger transitions on elements. Disable transitions during theme changes.

### Interactivity Patterns (from /emil-design-engineering)

#### Touch-First, Hover-Enhanced
- Design for touch first, add hover as progressive enhancement
- **Never rely on hover for core functionality** — hover enhances, not enables
- Disable hover effects on touch devices:
```css
@media (hover: hover) and (pointer: fine) {
  .element:hover { background: var(--accent); }
}
```
- Set `touch-action: manipulation` on buttons/links to prevent double-tap zoom

#### Tap Targets
- **44px minimum** on all interactive elements
- Small icon buttons: use `::before` pseudo-element to expand hit area:
```css
.icon-button { position: relative; width: 24px; height: 24px; }
.icon-button::before { content: ''; position: absolute; inset: -10px; }
```

#### Button Press Feel
Add `transform: scale(0.97)` on `:active` for tactile feedback:
```css
.button:active { transform: scale(0.97); }
```

#### No Layout Shift
- Use `font-variant-numeric: tabular-nums` for all changing numbers
- Never change font weight on hover/selected states
- Use hardcoded dimensions for skeleton loaders and image placeholders

#### Tooltips
- **Delay before showing**: 200ms to prevent accidental activation
- **Sequential ("warm") tooltips**: Once one tooltip is open, subsequent tooltips open instantly with no delay/animation. Track warm state and clear after 300ms of no tooltip being open.
- Tooltip content must not rely on hover for functionality — it's supplementary only

#### Focus & Keyboard
- Tab order must be consistent — only tab through visible elements
- `scrollIntoView({ behavior: 'smooth', block: 'nearest' })` when keyboard navigation scrolls
- Focus moves to modal content on open, returns to trigger on close
- Icon buttons always need `aria-label`
- Focus outlines: grey, black, or white only — never colored outlines

#### Forms & Inputs
- Wrap inputs with `<form>` for Enter-to-submit
- Support `Cmd+Enter` / `Ctrl+Enter` for textarea submission
- Input font size: **16px minimum** (prevents iOS auto-zoom)
- Label clicks must focus the associated input
- Disable button after submission to prevent duplicate requests
- Colocate errors near the field that caused them

### Hover States — Component Reference

Every interactive element must have a defined hover state. All hover styles are guarded with `@media (hover: hover) and (pointer: fine)` to prevent sticky hover on touch devices. Transitions use `150ms ease` on explicit properties (never `transition: all`). All elements get `active: transform: scale(0.97)` for press feedback.

#### Buttons
| Variant | Default | Hover | Active |
|---------|---------|-------|--------|
| Primary | `bg: var(--primary)`, `color: var(--primary-foreground)` | `bg: var(--primary-90)` | `scale(0.97)` |
| Secondary | `bg: var(--secondary)`, `color: var(--secondary-foreground)` | `bg: var(--tertiary)` | `scale(0.97)` |
| Ghost | `bg: transparent`, `color: var(--foreground)` | `bg: var(--accent)` | `scale(0.97)` |
| Outline | `bg: transparent`, `border: var(--input)`, `color: var(--foreground)` | `bg: var(--accent)` | `scale(0.97)` |
| Destructive | `bg: var(--destructive)`, `color: white` | `opacity: 0.9` | `scale(0.97)` |
| Link | `bg: transparent`, `color: var(--primary)` | `text-decoration: underline` | — |

```css
@media (hover: hover) and (pointer: fine) {
  .btn-primary:hover { background: var(--primary-90); }
  .btn-secondary:hover { background: var(--tertiary); }
  .btn-ghost:hover { background: var(--accent); }
  .btn-outline:hover { background: var(--accent); }
  .btn-destructive:hover { opacity: 0.9; }
  .btn-link:hover { text-decoration: underline; }
}
button, [role="button"] {
  transition: background 150ms ease, opacity 150ms ease, transform 100ms ease;
  touch-action: manipulation;
}
button:active, [role="button"]:active { transform: scale(0.97); }
```

#### Tabs & Segmented Controls
| State | Style |
|-------|-------|
| Unselected | `bg: transparent`, `color: var(--muted-foreground)` |
| Unselected hover | `bg: var(--accent)`, `color: var(--foreground)` |
| Selected | `bg: var(--secondary)`, `color: var(--foreground)` |
| Selected hover | No change (already active) |

```css
@media (hover: hover) and (pointer: fine) {
  .tab-trigger:not([data-state="active"]):hover {
    background: var(--accent);
    color: var(--foreground);
  }
}
.tab-trigger {
  transition: background 150ms ease, color 150ms ease;
}
```

**Critical**: Never use `var(--primary)` for tab selection background — tabs use neutral grey (`var(--secondary)`) to avoid competing with content. The hover uses `var(--accent)` which is one step lighter than `var(--secondary)`.

#### Links
| Context | Default | Hover |
|---------|---------|-------|
| Inline text | `color: var(--primary)`, no underline | `text-decoration: underline` |
| Navigation | `color: var(--muted-foreground)` | `color: var(--foreground)` |
| Sidebar nav | `color: var(--sidebar-foreground)` | `bg: var(--sidebar-accent)` |

```css
@media (hover: hover) and (pointer: fine) {
  a.inline-link:hover { text-decoration: underline; }
  a.nav-link:hover { color: var(--foreground); }
}
a { transition: color 150ms ease; }
```

#### Cards (clickable/interactive)
Not all cards are interactive. Only apply hover to cards with `onClick`, `<a>` wrapper, or explicit interactive intent.

| State | Style |
|-------|-------|
| Default | `bg: var(--card)`, `border: var(--border-grid)` |
| Hover | `border-color: var(--border)`, `box-shadow: 0 4px 12px rgba(0,0,0,0.08)` |

```css
@media (hover: hover) and (pointer: fine) {
  .card-interactive:hover {
    border-color: var(--border);
    box-shadow: 0 4px 12px rgba(0,0,0,0.08);
  }
}
.card-interactive {
  transition: border-color 150ms ease, box-shadow 150ms ease;
  cursor: pointer;
}
```

#### Table Rows
| State | Style |
|-------|-------|
| Default | `bg: transparent` |
| Hover | `bg: var(--muted)` |

```css
@media (hover: hover) and (pointer: fine) {
  tbody tr:hover { background: var(--muted); }
}
tbody tr { transition: background 150ms ease; }
```

#### Sidebar Items
| State | Style |
|-------|-------|
| Default | `bg: transparent`, `color: var(--sidebar-foreground)` |
| Hover | `bg: var(--sidebar-accent)`, `color: var(--sidebar-accent-foreground)` |
| Active | `bg: var(--sidebar-accent)`, `color: var(--sidebar-accent-foreground)`, `font-weight: 500` |

#### Dropdown / Select / Menu Items
| State | Style |
|-------|-------|
| Default | `bg: transparent` |
| Hover / Focus | `bg: var(--accent)`, `color: var(--accent-foreground)` |

```css
@media (hover: hover) and (pointer: fine) {
  [role="menuitem"]:hover,
  [role="option"]:hover {
    background: var(--accent);
    color: var(--accent-foreground);
  }
}
```

#### Inputs & Textareas
| State | Style |
|-------|-------|
| Default | `border: var(--input)` |
| Hover | `border-color: var(--border)` (slightly more contrast) |
| Focus | `ring: 2px var(--ring)`, `border-color: var(--primary)` |

```css
@media (hover: hover) and (pointer: fine) {
  input:hover, textarea:hover, select:hover {
    border-color: var(--border);
  }
}
input, textarea, select {
  transition: border-color 150ms ease, box-shadow 150ms ease;
}
input:focus-visible, textarea:focus-visible {
  outline: none;
  border-color: var(--primary);
  box-shadow: 0 0 0 2px var(--ring);
}
```

#### Icon Buttons
| State | Style |
|-------|-------|
| Default | `bg: transparent` |
| Hover | `bg: var(--accent)` |
| Active | `scale(0.97)` |

Always include `aria-label`. Expand hit area to 44px minimum with `::before` pseudo-element.

#### Badges & Tags (when clickable)
| State | Style |
|-------|-------|
| Default | Normal opacity |
| Hover | `opacity: 0.8` |

Only apply hover styles to badges that are links or have click handlers. Static badges have no hover state.

#### Toggle / Switch
| State | Style |
|-------|-------|
| Track default | Token background |
| Track hover | `brightness(1.1)` filter |

#### Universal Hover Rules
1. **Guard everything**: `@media (hover: hover) and (pointer: fine) { ... }`
2. **Explicit transitions**: Never `transition: all`. Specify `background`, `color`, `border-color`, `opacity`, `transform`, `box-shadow`.
3. **Duration**: `150ms ease` for all hover transitions.
4. **No font-weight changes**: Never change font weight on hover — causes layout shift.
5. **No color-only indicators**: Hover state changes must include background or border shift, not just color.
6. **Active feedback**: All clickable elements get `transform: scale(0.97)` on `:active` with `100ms ease` transition.
7. **Focus-visible**: Use `var(--ring)` token. Outlines must be grey, black, or white — never colored.
8. **Reduced motion**: All transitions respect `prefers-reduced-motion: reduce`.

### Visual Polish (from /frontend-design + /emil-design-engineering)

#### Anti-Slop Checklist
Every Marinade UI must avoid generic AI aesthetics. Before shipping, verify:
- No default/generic font choices (the system uses Geist — enforce it)
- No arbitrary colors outside the token system
- No cookie-cutter card layouts with identical padding everywhere
- Every visual choice (color, spacing, radius, shadow) must be intentional for the context

#### Shadows for Borders
Use `box-shadow` instead of `border` for subtle dividers — blends better with varying backgrounds:
```css
box-shadow: 0 0 0 1px rgba(0, 0, 0, 0.08);
```

#### Hairline Borders
```css
:root { --border-hairline: 1px; }
@media (min-resolution: 192dpi) { :root { --border-hairline: 0.5px; } }
```

#### Decorative Elements
- `pointer-events: none` on all decorative/background elements
- `user-select: none` on code illustrations and decorative art

#### Mask Over Gradient
Prefer `mask-image` over gradients for fades — works better with varying content:
```css
.fade-bottom { mask-image: linear-gradient(to bottom, black 80%, transparent); }
```
Do NOT apply fades on scrollable lists — it restricts viewable area.

#### Z-Index Scale
```css
:root { --z-dropdown: 100; --z-modal: 200; --z-tooltip: 300; --z-toast: 400; }
```
Prefer `isolation: isolate` over z-index when possible.

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

### Mobile Responsiveness — MANDATORY

Every UI must work on mobile (320px+) while maintaining the design language. Mobile is not an afterthought — it's a core requirement. Test at 375px (iPhone SE/Mini), 390px (iPhone 15), and 768px (iPad mini) viewports.

#### Layout Strategy
- **Mobile-first CSS**: Write base styles for mobile, add complexity via `min-width` breakpoints
- **Single column default**: Cards, stats, and grids stack vertically below `md` (768px)
- **No horizontal scroll**: Nothing should overflow the viewport. Use `overflow-x: hidden` on body as a safety net, but fix the root cause.
- **Container padding**: `16px` on mobile, `24px` on desktop

```css
.container { padding: 0 16px; }
@media (min-width: 768px) { .container { padding: 0 24px; } }
```

#### Grid Patterns
| Component | Desktop | Tablet (md) | Mobile (sm) |
|-----------|---------|-------------|-------------|
| Stat cards | 3-4 columns | 2 columns | 1 column |
| Data tables | Full table | Full table with horizontal scroll | Card layout or horizontal scroll |
| Sidebar + content | Side-by-side | Collapsible sidebar | Bottom sheet or hamburger menu |
| Charts | Full width in card | Full width | Full width, reduce Y-axis labels |
| Form inputs | Multi-column | Multi-column | Single column, full width |

```css
.stat-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 12px;
}
@media (min-width: 640px) { .stat-grid { grid-template-columns: repeat(2, 1fr); } }
@media (min-width: 1024px) { .stat-grid { grid-template-columns: repeat(4, 1fr); } }
```

#### Typography Scaling
| Element | Desktop | Mobile |
|---------|---------|--------|
| Page title (h1) | 32-36px | 24-28px |
| Section heading (h2) | 24px | 20px |
| Card title (h3) | 18px | 16px |
| Body text | 14-15px | 14px |
| Small / labels | 12-13px | 12px |
| Stat values | 24-32px | 20-24px |

Use `clamp()` for fluid sizing on hero/display text:
```css
.page-title { font-size: clamp(24px, 5vw, 36px); }
```

#### Touch Targets — Mobile Critical
- **44px minimum** on all interactive elements (buttons, links, tabs, toggles)
- Tab bar items: 48px minimum height
- Table row tap targets: full row is tappable, minimum 48px row height
- Spacing between tappable items: 8px minimum to prevent mis-taps
- `touch-action: manipulation` on all buttons and links

#### Tables on Mobile
Tables wider than viewport must adapt. Prefer these patterns in order:
1. **Card layout**: Below `sm`, transform rows into stacked cards
2. **Horizontal scroll**: Wrap table in `overflow-x: auto` container with `-webkit-overflow-scrolling: touch`
3. **Column hiding**: Hide less important columns on mobile, show key data only

```css
.table-container {
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
  scrollbar-width: thin;
}
```

#### Sidebar Navigation on Mobile
- Below `lg` (1024px): Sidebar collapses to a hamburger menu or bottom sheet
- Use `position: fixed` overlay with backdrop blur
- Animate in with `transform: translateX(-100%)` → `translateX(0)` at 250ms ease-out
- Close on backdrop tap and on route change
- Body scroll must be locked while sidebar is open (`overflow: hidden` on body)

#### Charts on Mobile
- Full width, no side padding inside chart container
- Reduce X-axis labels to 3-5 on mobile
- Hide Y-axis labels on very small screens (< 375px), show only grid lines
- Tooltip position: Above the touch point, clamped to viewport
- Range selector pills: Smaller padding, horizontally scrollable if needed
- Disable brush/zoom on touch — use pinch-to-zoom if needed

#### Modals & Sheets on Mobile
- Below `sm`: Modals become full-screen bottom sheets
- Slide up animation: `transform: translateY(100%)` → `translateY(0)` at 300ms ease-out
- Include a drag handle (40px wide, 4px tall, centered, `var(--muted-foreground)` at 30% opacity)
- Support swipe-to-dismiss gesture
- Max height: `85vh` on mobile, with internal scroll

#### Input Forms on Mobile
- All inputs: `font-size: 16px` minimum (prevents iOS auto-zoom)
- Full width inputs below `sm`
- Stack label above input (not inline/side-by-side)
- Submit button: Full width on mobile, sticky at bottom if form scrolls
- Use `inputmode` attribute for numeric keyboards: `inputmode="decimal"` for SOL amounts

#### Images & Media
- Use `max-width: 100%` and `height: auto` on all images
- Lazy load images below the fold: `loading="lazy"`
- Avatar/icon sizes: Same on mobile and desktop (don't shrink below 32px)

#### Safe Areas (iOS)
Account for notch/dynamic island and home indicator:
```css
body {
  padding-top: env(safe-area-inset-top);
  padding-bottom: env(safe-area-inset-bottom);
  padding-left: env(safe-area-inset-left);
  padding-right: env(safe-area-inset-right);
}
```

#### Mobile Auto-Fix Rules
- Fixed/sticky elements without `bottom: env(safe-area-inset-bottom)` → Add it
- Text truncation without `min-width: 0` on flex children → Add it
- Horizontal overflow on mobile → Debug and fix (common: tables, code blocks, long addresses)
- Tap targets < 44px on mobile → Increase
- Input font-size < 16px → Increase to prevent iOS zoom
- Missing `viewport` meta tag → Add `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
- Hover-dependent interactions on mobile → Provide tap alternative

## UI Quality Audit (Auto-Fix Mode)

When building or reviewing any Marinade UI, automatically check for and fix these issues without being asked. Integrates quality standards from **/frontend-design** (anti-slop aesthetics, bold design) and **/emil-design-engineering** (interactivity, polish, accessibility).

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

### Interactivity Issues — Auto-Fix (from /emil-design-engineering)
- Hover effects without `@media (hover: hover)` guard → Add media query
- Buttons without `:active` scale feedback → Add `transform: scale(0.97)`
- Tooltips without delay → Add 200ms delay, implement warm state for sequential
- `transition: all` → Specify exact properties
- Font weight change on hover/selected → Remove (use color change instead)
- Paired elements with different easing/duration → Synchronize
- Animations on frequently-used actions → Remove or drastically reduce
- Missing `touch-action: manipulation` on buttons → Add it
- Inputs < 16px font size → Increase to prevent iOS zoom
- Forms without Enter-to-submit → Wrap in `<form>`

### Accessibility Issues — Auto-Fix
- Touch targets < 44px → Increase with padding or `::before` pseudo-element
- Icon buttons without `aria-label` → Add descriptive label
- Missing focus-visible styles → Add using `ring` token
- Color-only status indicators → Add icon or text supplement
- Missing hover states on interactive elements → Add subtle background shift with `@media (hover: hover)` guard
- Keyboard navigation doesn't scroll → Add `scrollIntoView` on focus
- Focus doesn't move to modal on open → Add focus management
- Colored focus outlines → Change to grey/black/white

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
- Layout shell (light mode default, Geist font loaded, dark mode toggle)
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
