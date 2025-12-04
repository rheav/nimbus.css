# ☁️ Nimbus.css

**A lightweight, opinionated CSS library for modern web interfaces.**

Nimbus is NOT a utility framework like Tailwind or Bootstrap. Instead, it provides:

- Beautiful semantic components with consistent styling
- Opinionated defaults for spacing, typography, and colors
- Frosted glass effects and metallic gradients
- Automatic dark mode support
- Styled semantic HTML elements (blockquote, details, progress, etc.)
- Zero configuration needed - just use semantic HTML

Write CSS the traditional way, but with better defaults.

## Philosophy

- **Component-first**, not utility-first
- **Opinionated** defaults that look good out of the box
- **Lightweight** - no bloat, no utility classes
- **Semantic** - Use meaningful class names, not `.p-4` or `.grid-cols-3`
- **Customizable** via CSS custom properties

## Installation

Include the CSS file in your HTML:

```html
<link rel="stylesheet" href="nimbus.css" />
```

Or via CDN (jsDelivr):

```html
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/gh/rheav/nimbus.css@latest/nimbus.min.css"
/>
```

## Usage

All components use the `nc-` prefix. Write semantic HTML, apply component classes:

### Buttons

```html
<!-- Primary Button -->
<button class="nc-btn nc-btn-primary">Primary</button>

<!-- Secondary Button -->
<button class="nc-btn nc-btn-secondary">Secondary</button>

<!-- Button Sizes -->
<button class="nc-btn nc-btn-primary nc-btn-sm">Small</button>
<button class="nc-btn nc-btn-primary">Default</button>
<button class="nc-btn nc-btn-primary nc-btn-lg">Large</button>

<!-- Loading State -->
<button class="nc-btn nc-btn-primary nc-btn-loading">Loading</button>
```

### Cards

```html
<!-- Default Frosted Card -->
<div class="nc-card">
  <h3>Card Title</h3>
  <p>Card content</p>
</div>

<!-- Solid Card -->
<div class="nc-card nc-card-solid">
  <h3>Solid Card</h3>
</div>

<!-- Gradient Card -->
<div class="nc-card nc-card-gradient">
  <h3>Gradient Card</h3>
</div>
```

### Complete Card Example

A comprehensive card example combining multiple components:

```html
<div class="nc-card">
  <!-- Image placeholder -->
  <div class="nc-card-image nc-card-image-gradient">🌊 nimbus</div>

  <!-- Tags/Chips -->
  <div class="nc-mb-sm">
    <span class="nc-chip nc-chip-primary">design system</span>
    <span class="nc-chip nc-chip-success">new</span>
    <span class="nc-chip nc-chip-default">v1.0</span>
  </div>

  <!-- Title -->
  <h3 class="nc-card-title">nimbus library</h3>

  <!-- Description -->
  <p class="nc-card-text nc-text-sm">
    a minimal, lightweight CSS library with a modern frosted glass design
    aesthetic. Perfect for building beautiful interfaces quickly.
  </p>

  <!-- Meta info -->
  <div class="nc-card-meta">
    <span>👤 12 contributors</span>
    <span>⭐ 234 stars</span>
  </div>

  <!-- Action buttons -->
  <div class="nc-card-actions">
    <button class="nc-btn nc-btn-primary">get started</button>
    <button class="nc-btn nc-btn-outline">documentation</button>
  </div>
</div>
```

### Forms

```html
<div class="nc-input-group">
  <label class="nc-input-label">Email</label>
  <input type="email" class="nc-input" placeholder="you@example.com" />
</div>

<div class="nc-input-group">
  <label class="nc-input-label">Message</label>
  <textarea class="nc-textarea nc-input" placeholder="Your message"></textarea>
</div>

<!-- Input with error state -->
<div class="nc-input-group nc-input-error">
  <label class="nc-input-label">Email</label>
  <input type="email" class="nc-input" value="invalid" />
  <span class="nc-input-hint">Please enter a valid email</span>
</div>

<!-- Input with success state -->
<div class="nc-input-group nc-input-success">
  <label class="nc-input-label">Username</label>
  <input type="text" class="nc-input" value="johndoe" />
  <span class="nc-input-hint">Username is available</span>
</div>
```

### Switch / Toggle

```html
<label class="nc-switch">
  <input type="checkbox" />
  <span class="nc-switch-track">
    <span class="nc-switch-thumb"></span>
  </span>
  <span class="nc-switch-label">Enable notifications</span>
</label>
```

### Dialog / Modal

```html
<!-- Trigger: add nc-dialog-open class to overlay via JS -->
<div class="nc-dialog-overlay nc-dialog-open">
  <div class="nc-dialog">
    <div class="nc-dialog-header">
      <h3 class="nc-dialog-title">Dialog Title</h3>
      <button class="nc-dialog-close">&times;</button>
    </div>
    <div class="nc-dialog-body">
      <p>Dialog content goes here.</p>
    </div>
    <div class="nc-dialog-footer">
      <button class="nc-btn nc-btn-secondary">Cancel</button>
      <button class="nc-btn nc-btn-primary">Confirm</button>
    </div>
  </div>
</div>

<!-- Dialog sizes: nc-dialog-sm, nc-dialog-lg, nc-dialog-xl -->
```

### Avatar

```html
<!-- Basic avatar with initials -->
<span class="nc-avatar">JD</span>

<!-- Avatar with image -->
<span class="nc-avatar">
  <img src="user.jpg" alt="User" />
</span>

<!-- Avatar sizes: nc-avatar-xs, nc-avatar-sm, nc-avatar-lg, nc-avatar-xl -->
<span class="nc-avatar nc-avatar-lg">LG</span>

<!-- Avatar with status indicator -->
<span class="nc-avatar-wrapper">
  <span class="nc-avatar">JD</span>
  <span class="nc-avatar-status nc-avatar-status-online"></span>
</span>
<!-- Status: nc-avatar-status-online, nc-avatar-status-busy, nc-avatar-status-away -->

<!-- Avatar group (stacked) -->
<div class="nc-avatar-group">
  <span class="nc-avatar">A</span>
  <span class="nc-avatar">B</span>
  <span class="nc-avatar">+3</span>
</div>
```

### Skeleton / Loading

```html
<!-- Text skeleton -->
<div class="nc-skeleton nc-skeleton-text"></div>

<!-- Heading skeleton -->
<div class="nc-skeleton nc-skeleton-heading"></div>

<!-- Avatar skeleton -->
<div class="nc-skeleton nc-skeleton-avatar"></div>

<!-- Button skeleton -->
<div class="nc-skeleton nc-skeleton-button"></div>

<!-- Image skeleton -->
<div class="nc-skeleton nc-skeleton-image"></div>

<!-- Card skeleton container -->
<div class="nc-skeleton-card">
  <div class="nc-skeleton nc-skeleton-heading"></div>
  <div class="nc-skeleton nc-skeleton-text"></div>
  <div class="nc-skeleton nc-skeleton-text"></div>
</div>
```

### Toast / Notifications

```html
<!-- Toast container (fixed position) -->
<div class="nc-toast-container nc-toast-container-top-right">
  <!-- Toast variants: nc-toast-success, nc-toast-error, nc-toast-warning, nc-toast-info -->
  <div class="nc-toast nc-toast-success">
    <span class="nc-toast-icon">✓</span>
    <div class="nc-toast-content">
      <div class="nc-toast-title">Success!</div>
      <div class="nc-toast-message">Your changes have been saved.</div>
    </div>
    <button class="nc-toast-close">&times;</button>
  </div>
</div>

<!-- Container positions:
  nc-toast-container-top-right
  nc-toast-container-top-left
  nc-toast-container-top-center
  nc-toast-container-bottom-right
  nc-toast-container-bottom-left
  nc-toast-container-bottom-center
-->
```

### Badges

```html
<span class="nc-badge nc-badge-primary">Primary</span>
<span class="nc-badge nc-badge-success">Success</span>
<span class="nc-badge nc-badge-warning">Warning</span>
<span class="nc-badge nc-badge-danger">Danger</span>
```

### Alerts

```html
<div class="nc-alert nc-alert-info">
  <div class="nc-alert-title">Information</div>
  This is an info message
</div>
```

### Tables

```html
<div class="nc-table-wrapper">
  <table class="nc-table">
    <thead>
      <tr>
        <th>Name</th>
        <th>Status</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Item 1</td>
        <td>Active</td>
      </tr>
    </tbody>
  </table>
</div>
```

### Tabs

```html
<div class="nc-tabs">
  <button class="nc-tab active">Tab 1</button>
  <button class="nc-tab">Tab 2</button>
  <button class="nc-tab">Tab 3</button>
</div>
```

### Tip Boxes

Modern shiny tip boxes with beautiful gradient that transitions from light frost blue to dark semi-transparent blue.

```html
<!-- Default tip with silver-ish gradient -->
<div class="nc-tip">
  💡 <strong>Pro Tip:</strong> Your helpful message here.
</div>

<!-- Ocean variant -->
<div class="nc-tip nc-tip-ocean">
  🌊 <strong>Note:</strong> Ocean gradient variant.
</div>

<!-- Emerald variant -->
<div class="nc-tip nc-tip-emerald">
  ✓ <strong>Success:</strong> Confirmation message.
</div>
```

### Silver Gradient Components

Beautiful metallic components with silver-ish gradient (from #7abcff to rgba(0, 78, 147, 0.5)). All silver components maintain the same metallic finish for consistency - never pastel.

```html
<!-- Silver Button -->
<button class="nc-btn nc-btn-silver">Silver Button</button>

<!-- Silver Card -->
<div class="nc-card-silver">
  <h3>Silver Card</h3>
  <p>Content with metallic gradient background</p>
</div>

<!-- Silver Badge -->
<span class="nc-badge nc-badge-silver">Silver</span>

<!-- Silver Chip/Tag -->
<span class="nc-chip nc-chip-silver">#metallic</span>

<!-- Silver Alert -->
<div class="nc-alert nc-alert-silver">
  <div class="nc-alert-title">✨ Silver Alert</div>
  Beautiful gradient with silver-ish finish.
</div>
```

### Background Gradients

Apply gradient backgrounds to any element with these utility classes. All include a metallic shine overlay.

```html
<!-- Silver metallic gradient -->
<section class="nc-bg-silver">Silver section</section>

<!-- Ocean gradient (frost to ocean blue) -->
<div class="nc-bg-ocean">Ocean content</div>

<!-- Frosted glass effect -->
<div class="nc-bg-frost">Frosted glass</div>

<!-- Dark gradient -->
<header class="nc-bg-midnight">Dark header</header>

<!-- Status gradients -->
<div class="nc-bg-success">Success</div>
<div class="nc-bg-danger">Danger</div>
<div class="nc-bg-warning">Warning</div>

<!-- Sky gradient (ideal for hero sections) -->
<section class="nc-bg-sky">Hero section</section>
```

Available classes:

| Class            | Description                        |
| ---------------- | ---------------------------------- |
| `nc-bg-silver`   | Metallic blue-silver gradient      |
| `nc-bg-ocean`    | Frost to ocean blue gradient       |
| `nc-bg-frost`    | Light frosted glass with blur      |
| `nc-bg-midnight` | Dark gradient (auto light text)    |
| `nc-bg-success`  | Green gradient                     |
| `nc-bg-danger`   | Red gradient                       |
| `nc-bg-warning`  | Amber gradient                     |
| `nc-bg-sky`      | Sky gradient with radial highlight |
| `nc-gradient-bg` | White to frost vertical gradient   |
| `nc-bg-fog`      | Solid off-white background         |
| `nc-bg-ash`      | Solid light gray background        |
| `nc-bg-snow`     | Solid white background             |

### Glass Card

Frosted glass card with blur effect:

```html
<div class="nc-glass-card" style="padding: 1rem">
  <p>Frosted glass content</p>
</div>
```

### Tab Buttons

Segmented tab navigation:

```html
<div style="display: flex">
  <button class="nc-tab-active" style="border-radius: 6px 0 0 6px">
    Active
  </button>
  <button class="nc-tab-inactive" style="border-radius: 0 6px 6px 0">
    Inactive
  </button>
</div>
```

### Toggle Buttons

ON/OFF toggle buttons:

```html
<button class="nc-toggle-on">ON</button>
<button class="nc-toggle-off">OFF</button>
```

### Icon Buttons

Small icon buttons with hover effects:

```html
<button class="nc-icon-btn">⭐</button>
<button class="nc-icon-btn-active">⭐</button>
<!-- Yellow/active state -->
```

### List Items

Clickable list items with hover slide effect:

```html
<div class="nc-list-item">Standard list item</div>
<div class="nc-list-item-subtle">Subtle variant</div>
```

### Text Utilities

```html
<span class="nc-text-ocean">Ocean blue text</span>
<span class="nc-text-frost">Frost blue text</span>
<span class="nc-text-pebble">Muted gray text</span>
<span class="nc-text-ink">Dark text</span>
<span class="nc-text-snow">White text</span>
<span class="nc-text-midnight">Near-black text</span>
```

### Text Effects

#### Gradient Text

```html
<!-- Gradient Title -->
<h1 class="nc-title-gradient">Gradient Title</h1>

<!-- Gradient Spans -->
<span class="nc-text-gradient">frost to ocean gradient</span>
<span class="nc-text-gradient-ocean">ocean to sapphire</span>
<span class="nc-text-gradient-emerald">emerald gradient</span>
<span class="nc-text-gradient-sunset">sunset gradient</span>
<span class="nc-text-gradient-silver">silver metallic</span>
<span class="nc-text-gradient-animated">animated gradient</span>
```

#### Text Glow

```html
<span class="nc-text-glow">frost glow effect</span>
<span class="nc-text-glow-ocean">ocean glow effect</span>
<span class="nc-text-glow-emerald">emerald glow effect</span>
```

#### Text Highlights

```html
<span class="nc-text-highlight">frost highlight</span>
<span class="nc-text-highlight-ocean">ocean highlight</span>
<span class="nc-text-highlight-emerald">emerald highlight</span>
<span class="nc-text-highlight-sandy">sandy highlight</span>
```

#### Underline Effects

```html
<span class="nc-text-underline">hover for animated underline</span>
<span class="nc-text-underline-static">static gradient underline</span>
```

### Custom Scrollbar

Apply themed scrollbar to any scrollable element:

```html
<div class="nc-scrollbar" style="overflow-y: auto; max-height: 300px">
  <!-- Scrollable content -->
</div>
```

### Pulse Animations

```html
<!-- Green pulse (for status indicators) -->
<span class="nc-pulse" style="..."></span>

<!-- Frost blue pulse -->
<span class="nc-pulse-frost" style="..."></span>
```

## Semantic HTML Elements

Nimbus automatically styles semantic HTML elements - no classes needed!

### Blockquote

```html
<blockquote>
  "The best way to predict the future is to invent it."
  <footer>— Alan Kay</footer>
</blockquote>
```

### Details/Summary (Collapsible)

```html
<details>
  <summary>Click to expand</summary>
  <p>Hidden content that appears when opened.</p>
</details>
```

### Progress Bar

```html
<progress value="70" max="100"></progress>
```

### Fieldset (Form Grouping)

```html
<fieldset>
  <legend>Personal Information</legend>
  <label>Name: <input type="text" /></label>
  <label>Email: <input type="email" /></label>
</fieldset>
```

### Inline Semantic Elements

```html
<!-- Highlight -->
<mark>highlighted text</mark>

<!-- Keyboard shortcut -->
Press <kbd>Ctrl</kbd> + <kbd>C</kbd> to copy

<!-- Sample output -->
<samp>Error: File not found</samp>

<!-- Time/date -->
<time datetime="2025-11-02">November 2, 2025</time>
```

### Aside (Sidebar Content)

```html
<aside>This content floats to the right with styling.</aside>
```

### Definition Lists

```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>

  <dt>CSS</dt>
  <dd>Cascading Style Sheets</dd>
</dl>
```

## Dark Mode

Nimbus automatically adapts to your system's dark mode preference using `prefers-color-scheme`. No configuration needed!

All colors, backgrounds, and borders adjust automatically.

## Working with Spacing & Layout

**Nimbus does NOT provide utility classes like `.p-4` or `.mt-3`.**

Instead, use CSS custom properties for consistent spacing:

```css
/* Use CSS custom properties in your own styles */
.my-section {
  padding: var(--nc-space-lg); /* 1.5rem */
  margin-bottom: var(--nc-space-xl); /* 2rem */
}

.my-header {
  margin: var(--nc-space-2xl) 0; /* 3rem top/bottom */
}
```

### Available Spacing Variables

- `--nc-space-xs`: 0.5rem
- `--nc-space-sm`: 0.75rem
- `--nc-space-md`: 1rem
- `--nc-space-lg`: 1.5rem
- `--nc-space-xl`: 2rem
- `--nc-space-2xl`: 3rem

### Layout with CSS Grid & Flexbox

Write layout the normal way:

```css
/* Grid example */
.my-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: var(--nc-space-lg);
}

/* Flexbox example */
.my-flex {
  display: flex;
  gap: var(--nc-space-md);
  align-items: center;
}
```

## Border Radius Options

Minimal approach with only two border radius options:

- **`nc-rounded-sm`**: Small radius (0.375rem)
- **`nc-rounded-lg`**: Large radius (0.75rem)

Apply to any component:

```html
<div class="nc-card nc-rounded-sm">Small rounded corners</div>
<button class="nc-btn nc-btn-primary nc-rounded-lg">
  Large rounded button
</button>
```

## Customization

Override CSS custom properties to customize the design system:

```css
:root {
  /* Colors */
  --nc-ocean: #0066cc;
  --nc-frost: #90c0e0;

  /* Spacing */
  --nc-space-lg: 2rem;

  /* Typography */
  --nc-font-family: "Your Font", sans-serif;
  --nc-line-height: 1.7;
}
```

## What Nimbus is NOT

❌ Not a utility framework (no `.p-4`, `.grid-cols-3`, `.flex`)  
❌ Not a CSS reset (it's opinionated styling)  
❌ Not a complete design system (it's a starting point)

## What Nimbus IS

✅ Beautiful component styling out of the box  
✅ Consistent spacing and typography defaults  
✅ CSS custom properties for easy customization  
✅ Write regular CSS, just with better defaults  
✅ Lightweight and focused

## Development

Run the demo pages locally:

```bash
npm start
```

Then open:

- `http://localhost:8080/index.html` - Component documentation
- `http://localhost:8080/example-landing.html` - Example landing page

## License

MIT - Free for personal and commercial use.
