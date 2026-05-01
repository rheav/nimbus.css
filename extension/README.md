# NimbusCatcher Extension Style System

A frosted glass, blue-gradient design system for Chrome extensions based on [nimbus.css](https://github.com/rheav/nimbus.css).

![NimbusCatcher Theme](https://img.shields.io/badge/theme-NimbusCatcher-7abcff?style=flat-square)

---

## Table of Contents

- [Quick Start](#quick-start)
- [Color Palette](#color-palette)
- [CSS Variables](#css-variables)
- [Components](#components)
  - [Containers](#containers)
  - [Cards](#cards)
  - [Buttons](#buttons)
  - [Status Indicators](#status-indicators)
  - [List Items](#list-items)
  - [Badges](#badges)
- [Typography](#typography)
- [Animations](#animations)
- [Scrollbar](#scrollbar)
- [Utility Classes](#utility-classes)
- [Tailwind CSS Integration](#tailwind-css-integration)
- [React/JSX Usage](#reactjsx-usage)
- [Design Guidelines](#design-guidelines)

---

## Quick Start

### 1. Import the CSS

```html
<link rel="stylesheet" href="nimbus-extension.css" />
```

Or in your JS/React:

```js
import "./nimbus-extension.css";
```

### 2. Basic Structure

```html
<div class="nc-popup">
  <h1 class="nc-title-gradient">myExtension</h1>
  <div class="nc-glass-card">
    <!-- Your content -->
  </div>
</div>
```

---

## Color Palette

### Primary Colors (Blue Tones)

| Variable        | Hex       | Preview | Usage                               |
| --------------- | --------- | ------- | ----------------------------------- |
| `--nc-frost`    | `#7abcff` | 🔵      | Primary accent, borders, highlights |
| `--nc-ocean`    | `#006bc8` | 🔷      | Links, active states, primary text  |
| `--nc-sapphire` | `#004e93` | 🔹      | Dark gradients, headers             |
| `--nc-midnight` | `#000e19` | ⬛      | Near-black for headers              |
| `--nc-sky`      | `#deeffe` | 🩵      | Very light blue highlights          |

### Neutral Colors

| Variable      | Hex       | Preview | Usage                      |
| ------------- | --------- | ------- | -------------------------- |
| `--nc-snow`   | `#ffffff` | ⬜      | Pure white backgrounds     |
| `--nc-fog`    | `#fafafa` | 🔳      | Off-white card backgrounds |
| `--nc-ash`    | `#f5f5f5` | ▫️      | Inactive states, disabled  |
| `--nc-pebble` | `#8a8d90` | 🩶      | Secondary/muted text       |
| `--nc-ink`    | `#0a0a0a` | ⬛      | Primary text               |

### Accent Colors

| Variable       | Hex       | Preview | Usage                      |
| -------------- | --------- | ------- | -------------------------- |
| `--nc-emerald` | `#00c87b` | 🟢      | Success, enabled, ON state |
| `--nc-forest`  | `#007447` | 🌲      | Dark green for text        |
| `--nc-sandy`   | `#f7c77a` | 🟡      | Favorites, starred items   |
| `--nc-danger`  | `#ef4444` | 🔴      | Errors, warnings, delete   |

---

## CSS Variables

All variables are defined in `:root` and can be used anywhere:

```css
/* Colors */
var(--nc-frost)     /* #7abcff */
var(--nc-ocean)     /* #006bc8 */
var(--nc-sapphire)  /* #004e93 */
var(--nc-midnight)  /* #000e19 */
var(--nc-snow)      /* #ffffff */
var(--nc-fog)       /* #fafafa */
var(--nc-ash)       /* #f5f5f5 */
var(--nc-pebble)    /* #8a8d90 */
var(--nc-ink)       /* #0a0a0a */
var(--nc-sky)       /* #deeffe */
var(--nc-emerald)   /* #00c87b */
var(--nc-forest)    /* #007447 */
var(--nc-sandy)     /* #f7c77a */
var(--nc-danger)    /* #ef4444 */

/* Border Radius */
var(--nc-radius-sm) /* 6px - buttons, small elements */
var(--nc-radius-md) /* 6px - cards, inputs */
var(--nc-radius-lg) /* 8px - large containers */

/* Shadows */
var(--nc-shadow-frost) /* Blue-tinted shadow for cards */
var(--nc-shadow-ocean) /* Deeper blue shadow */
```

---

## Components

### Containers

#### Popup Container (`.nc-popup`)

Fixed-width container with gradient background for extension popups.

```html
<div class="nc-popup">
  <!-- Your popup content -->
</div>
```

**Styles:**

- Width: `420px`
- Background: White to frost gradient
- Border: 1px frost
- Padding: 24px

#### Gradient Background (`.nc-gradient-bg`)

Full-page gradient background for sidepanels or larger views.

```html
<div class="nc-gradient-bg">
  <!-- Full page content -->
</div>
```

**Styles:**

- Background: `linear-gradient(to bottom, #ffffff, rgba(122, 188, 255, 0.5))`

---

### Cards

#### Glass Card (`.nc-glass-card`)

Frosted glass effect with blur and shadow.

```html
<div class="nc-glass-card" style="padding: 12px;">
  <p>Frosted glass content</p>
</div>
```

**Styles:**

- Background: `rgba(250, 250, 250, 0.7)`
- Backdrop filter: `blur(12px)`
- Border: 1px frost with 50% opacity
- Border radius: 6px
- Box shadow: Frost-tinted shadow

---

### Buttons

#### Tab Buttons (`.nc-tab-active` / `.nc-tab-inactive`)

Segmented tab buttons for navigation.

```html
<div style="display: flex;">
  <button class="nc-tab-active" style="border-radius: 6px 0 0 6px;">
    Active Tab
  </button>
  <button class="nc-tab-inactive" style="border-radius: 0 6px 6px 0;">
    Inactive Tab
  </button>
</div>
```

**Active State:**

- Background: Frost to sapphire gradient
- Color: White
- Shadow: Strong frost glow

**Inactive State:**

- Background: Ash (#f5f5f5)
- Color: Ink (#0a0a0a)
- Shadow: Subtle frost

---

#### Toggle Buttons (`.nc-toggle-on` / `.nc-toggle-off`)

ON/OFF toggle buttons.

```html
<button class="nc-toggle-on">ON</button>
<button class="nc-toggle-off">OFF</button>
```

**ON State:**

- Background: Emerald (#00c87b)
- Color: White

**OFF State:**

- Background: Ash (#f5f5f5)
- Color: Pebble (#8a8d90)

---

#### Icon Buttons (`.nc-icon-btn` / `.nc-icon-btn-active`)

Small icon buttons for actions like favorite, close, etc.

```html
<!-- Default state -->
<button class="nc-icon-btn">
  <svg>...</svg>
</button>

<!-- Active/Favorite state (yellow) -->
<button class="nc-icon-btn-active">
  <svg>...</svg>
</button>
```

**Default:**

- Background: Frost with 20% opacity
- Border: Frost with 50% opacity
- Hover: Scale 1.1

**Active:**

- Background: Sandy (#f7c77a)
- Border: Frost with 50% opacity

---

### Status Indicators

#### Status Dot (`.nc-status-dot`)

Pulsing status indicator.

```html
<!-- Active (green pulsing) -->
<div class="nc-status-dot active"></div>

<!-- Inactive (gray) -->
<div class="nc-status-dot inactive"></div>
```

**Active:**

- Background: Emerald (#00c87b)
- Animation: Pulsing green glow

**Inactive:**

- Background: Pebble (#8a8d90)

---

### List Items

#### Standard List Item (`.nc-list-item`)

Clickable list item with hover effect.

```html
<div class="nc-list-item">
  <p>Item content</p>
</div>
```

**Styles:**

- Background: Frost with 10% opacity
- Border: Frost with 30% opacity
- Hover: Slides 4px to the right

#### Shop Item Variant (`.nc-shop-item`)

Slightly more subtle list item for shop/product listings.

```html
<div class="nc-shop-item">
  <p>Shop name</p>
  <span>$1.95m revenue</span>
</div>
```

**Styles:**

- Background: Frost with 8% opacity
- Border: Frost with 25% opacity
- Hover: Slides 2px to the right

---

### Badges

#### Version Badge (`.nc-badge`)

Small badge for version numbers or labels.

```html
<span class="nc-badge">v1.0.0</span>
```

**Styles:**

- Background: Frost (#7abcff)
- Color: White
- Border: Ocean with 40% opacity
- Padding: 4px 16px

---

## Typography

#### Gradient Title (`.nc-title-gradient`)

Gradient text for main titles.

```html
<h1 class="nc-title-gradient">myExtension</h1>
```

**Styles:**

- Font size: 20px
- Font weight: 200 (extra light)
- Background: Frost to ocean gradient
- Text fill: Transparent (shows gradient)

---

## Animations

### Pulse Animation

Used for status indicators. Automatically applied to `.nc-status-dot.active`.

```css
@keyframes pulse {
  0% {
    box-shadow: 0 0 0 0 rgba(0, 200, 123, 0.5);
  }
  70% {
    box-shadow: 0 0 0 10px rgba(0, 200, 123, 0);
  }
  100% {
    box-shadow: 0 0 0 0 rgba(0, 200, 123, 0);
  }
}
```

**Usage:**

```css
animation: pulse 2s infinite;
```

### Pulse Live Green

Alternative pulse for live indicators.

```css
animation: pulseLiveGRN 2s infinite;
```

---

## Scrollbar

Custom scrollbar styling that matches the theme:

```css
/* Track */
background: linear-gradient(to bottom, #fff, rgba(122, 188, 255, 0.5));

/* Thumb */
background: linear-gradient(
  to bottom,
  rgba(122, 188, 255, 0.5),
  rgba(0, 107, 200, 0.6)
);
border-radius: 4px;
```

---

## Utility Classes

### Text Colors

```html
<span class="nc-text-ocean">Ocean blue text</span>
<span class="nc-text-pebble">Muted gray text</span>
<span class="nc-text-ink">Dark text</span>
<span class="nc-text-snow">White text</span>
```

### Background Colors

```html
<div class="nc-bg-frost">Frost background</div>
<div class="nc-bg-fog">Off-white background</div>
<div class="nc-bg-ash">Light gray background</div>
```

---

## Tailwind CSS Integration

If using Tailwind CSS v4, add these colors to your `@theme`:

```css
@theme {
  --color-nc-frost: #7abcff;
  --color-nc-ocean: #006bc8;
  --color-nc-sapphire: #004e93;
  --color-nc-midnight: #000e19;
  --color-nc-snow: #ffffff;
  --color-nc-fog: #fafafa;
  --color-nc-ash: #f5f5f5;
  --color-nc-pebble: #8a8d90;
  --color-nc-ink: #0a0a0a;
  --color-nc-sky: #deeffe;
  --color-nc-emerald: #00c87b;
  --color-nc-forest: #007447;
  --color-nc-sandy: #f7c77a;
  --color-nc-danger: #ef4444;
}
```

Then use in your HTML:

```html
<p class="text-nc-ocean">Ocean blue text</p>
<div class="bg-nc-frost">Frost background</div>
<button class="bg-nc-emerald text-nc-snow">Green button</button>
```

---

## React/JSX Usage

### Using CSS Classes

```jsx
import "./nimbus-extension.css";

function Popup() {
  const [isActive, setIsActive] = useState(true);

  return (
    <div className="nc-popup">
      <h1 className="nc-title-gradient">myExtension</h1>

      <div className="nc-glass-card" style={{ padding: "12px" }}>
        <div style={{ display: "flex", alignItems: "center", gap: "8px" }}>
          <div
            className={`nc-status-dot ${isActive ? "active" : "inactive"}`}
          />
          <span className="nc-text-ocean">
            {isActive ? "Enabled" : "Disabled"}
          </span>
          <button
            className={isActive ? "nc-toggle-on" : "nc-toggle-off"}
            onClick={() => setIsActive(!isActive)}
          >
            {isActive ? "ON" : "OFF"}
          </button>
        </div>
      </div>

      <div className="nc-shop-item">
        <p className="nc-text-ink">Shop Name</p>
        <span className="nc-text-pebble">$1.95m revenue</span>
      </div>

      <span className="nc-badge">v1.0.0</span>
    </div>
  );
}
```

### Inline Style Objects

```jsx
const styles = {
  popup: {
    width: "420px",
    background: "linear-gradient(to bottom, #ffffff, rgba(122, 188, 255, 0.5))",
    border: "1px solid #7abcff",
    padding: "24px",
  },
  glassCard: {
    background: "rgba(250, 250, 250, 0.7)",
    backdropFilter: "blur(12px)",
    border: "1px solid rgba(122, 188, 255, 0.5)",
    borderRadius: "6px",
    boxShadow: "0 10px 15px -3px rgba(122, 188, 255, 0.4)",
  },
  gradientTitle: {
    fontSize: "20px",
    fontWeight: 200,
    background: "linear-gradient(to right, #7abcff, #006bc8)",
    WebkitBackgroundClip: "text",
    WebkitTextFillColor: "transparent",
    margin: 0,
  },
};
```

---

## Design Guidelines

### Spacing

| Size | Value  | Usage                      |
| ---- | ------ | -------------------------- |
| XS   | `4px`  | Icon padding, small gaps   |
| SM   | `8px`  | Button padding, item gaps  |
| MD   | `12px` | Card padding, section gaps |
| LG   | `16px` | Tab padding                |
| XL   | `20px` | Section margins            |
| 2XL  | `24px` | Container padding          |

### Font Sizes

| Size | Value  | Usage              |
| ---- | ------ | ------------------ |
| XS   | `11px` | Badges, timestamps |
| SM   | `12px` | Body text, buttons |
| MD   | `13px` | Tab labels         |
| LG   | `14px` | Emphasized text    |
| XL   | `20px` | Main titles        |

### Border Radius

Use `6px` consistently for all elements (buttons, cards, badges).

### Widths

| Context   | Width                       |
| --------- | --------------------------- |
| Popup     | `420px`                     |
| Sidepanel | `100%` (max-width: `448px`) |

---

## File Structure

```
nimbus-style/
├── nimbus-extension.css   # Complete CSS file
└── README.md              # This documentation
```

---

## Credits

Based on [nimbus.css](https://github.com/rheav/nimbus.css) by @rheav

---

## License

MIT License - Feel free to use in your projects!
