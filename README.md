# 🌊 CloudUI

A minimal, lightweight CSS library with modern shiny frosted glass design aesthetic. Features gradient backgrounds, colored shadows, glossy effects, and beautiful silver-ish gradients.

## Installation

Include the CSS file in your HTML:

```html
<link rel="stylesheet" href="cloud-ui.css">
```

## Usage

All components use the `ci-` prefix:

### Buttons

```html
<!-- Primary Button -->
<button class="ci-btn ci-btn-primary">Primary</button>

<!-- Secondary Button -->
<button class="ci-btn ci-btn-secondary">Secondary</button>

<!-- Button Sizes -->
<button class="ci-btn ci-btn-primary ci-btn-sm">Small</button>
<button class="ci-btn ci-btn-primary">Default</button>
<button class="ci-btn ci-btn-primary ci-btn-lg">Large</button>
```

### Cards

```html
<!-- Default Frosted Card -->
<div class="ci-card">
  <h3>Card Title</h3>
  <p>Card content</p>
</div>

<!-- Solid Card -->
<div class="ci-card ci-card-solid">
  <h3>Solid Card</h3>
</div>

<!-- Gradient Card -->
<div class="ci-card ci-card-gradient">
  <h3>Gradient Card</h3>
</div>

<!-- Shiny Card with animated effect -->
<div class="ci-card ci-card-shiny">
  <h3>Shiny Card</h3>
  <p>Hover for shine animation</p>
</div>
```

### Forms

```html
<div class="ci-input-group">
  <label class="ci-input-label">Email</label>
  <input type="email" class="ci-input" placeholder="you@example.com" />
</div>

<div class="ci-input-group">
  <label class="ci-input-label">Message</label>
  <textarea class="ci-textarea ci-input" placeholder="Your message"></textarea>
</div>
```

### Badges

```html
<span class="ci-badge ci-badge-primary">Primary</span>
<span class="ci-badge ci-badge-success">Success</span>
<span class="ci-badge ci-badge-warning">Warning</span>
<span class="ci-badge ci-badge-danger">Danger</span>
```

### Alerts

```html
<div class="ci-alert ci-alert-info">
  <div class="ci-alert-title">Information</div>
  This is an info message
</div>
```

### Tables

```html
<div class="ci-table-wrapper">
  <table class="ci-table">
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
<div class="ci-tabs">
  <button class="ci-tab active">Tab 1</button>
  <button class="ci-tab">Tab 2</button>
  <button class="ci-tab">Tab 3</button>
</div>
```

### Tip Boxes

Modern shiny tip boxes with beautiful gradient that transitions from light frost blue to dark semi-transparent blue.

```html
<!-- Default tip with silver-ish gradient -->
<div class="ci-tip">
  💡 <strong>Pro Tip:</strong> Your helpful message here.
</div>

<!-- Ocean variant -->
<div class="ci-tip ci-tip-ocean">
  🌊 <strong>Note:</strong> Ocean gradient variant.
</div>

<!-- Emerald variant -->
<div class="ci-tip ci-tip-emerald">
  ✓ <strong>Success:</strong> Confirmation message.
</div>
```

### Silver Gradient Components

Beautiful metallic components with silver-ish gradient (from #7abcff to rgba(0, 78, 147, 0.5)). All silver components maintain the same metallic finish for consistency - never pastel.

```html
<!-- Silver Button -->
<button class="ci-btn ci-btn-silver">Silver Button</button>

<!-- Silver Card -->
<div class="ci-card-silver">
  <h3>Silver Card</h3>
  <p>Content with metallic gradient background</p>
</div>

<!-- Silver Badge -->
<span class="ci-badge ci-badge-silver">Silver</span>

<!-- Silver Chip/Tag -->
<span class="ci-chip ci-chip-silver">#metallic</span>

<!-- Silver Alert -->
<div class="ci-alert ci-alert-silver">
  <div class="ci-alert-title">✨ Silver Alert</div>
  Beautiful gradient with silver-ish finish.
</div>
```

## Border Radius Options

CloudI uses a minimal approach with only three border radius options:

- **No class**: Sharp corners (no border radius)
- **`ci-rounded-sm`**: Small radius (0.375rem)
- **`ci-rounded-lg`**: Large radius (0.75rem)

Apply to any component:

```html
<div class="ci-card ci-rounded-sm">Small rounded corners</div>
<button class="ci-btn ci-btn-primary ci-rounded-lg">
  Large rounded button
</button>
```

## Customization

Override CSS custom properties to customize colors:

```css
:root {
  --ci-ocean: #0066cc; /* Change primary blue */
  --ci-frost: #90c0e0; /* Change frost color */
}
```

## License

Free for personal and commercial use.
