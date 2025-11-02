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
<link rel="stylesheet" href="nimbus.css">
```

Or via CDN (jsDelivr):
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/rheav/nimbus.css@latest/nimbus.min.css">
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

<!-- Shiny Card with animated effect -->
<div class="nc-card nc-card-shiny">
  <h3>Shiny Card</h3>
  <p>Hover for shine animation</p>
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
  <label>Name: <input type="text"></label>
  <label>Email: <input type="email"></label>
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
<aside>
  This content floats to the right with styling.
</aside>
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
  padding: var(--nc-space-lg);  /* 1.5rem */
  margin-bottom: var(--nc-space-xl);  /* 2rem */
}

.my-header {
  margin: var(--nc-space-2xl) 0;  /* 3rem top/bottom */
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
<button class="nc-btn nc-btn-primary nc-rounded-lg">Large rounded button</button>
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
  --nc-font-family: 'Your Font', sans-serif;
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

## License

MIT - Free for personal and commercial use.
