# LeorpioMD

LeorpioMD is a modern Markdown parser and styler inspired by Material Design 3. Built on top of the powerful `markdown-it` engine, it provides a beautiful, responsive, and feature-rich environment for rendering Markdown content with Material Design aesthetics.

## Features

- **Material Design 3 Styling**: Built-in support for Material 3 colors, typography, and elevation.
- **Auto Dark Mode**: Responds to system color scheme preferences and supports manual overrides.
- **Color Preview Plugin**: Automatically renders CSS color strings (Hex, RGB, HSL, etc.) as live colored chips.
- **Interactive Buttons**: Custom syntax for creating stylised buttons with JavaScript actions.
- **Flexible Alignment**: Easy-to-use syntax for left, center, right, and justify text alignment.
- **Elegant Code Blocks**: VSCode-inspired code blocks with Mac-style window controls.
- **Link Security**: Automatically adds `target="_blank"` and `rel="noopener"` to external links.

## Installation

Since LeorpioMD is a lightweight library, you can include it directly in your project.

### Via ESM (Modern Browsers/Bundlers)

```javascript
import { parseMarkdown } from './leorpiomd.esm.js';
import './leorpiomd.css';

const html = parseMarkdown('# Hello LeorpioMD');
document.getElementById('content').innerHTML = html;
```

### Via UMD (Legacy/Direct Browser Script)

```html
<link rel="stylesheet" href="leorpiomd.css">
<script src="leorpiomd.umd.js"></script>
<script>
  const html = LeorpioMD.parseMarkdown('# Hello LeorpioMD');
  document.getElementById('content').innerHTML = html;
</script>
```

## Custom Syntax

LeorpioMD extends standard Markdown with several useful plugins:

### Text Alignment
Use the following markers to align your text. Always close the alignment block with `%/%`.

- `%<% Left Aligned %/%`
- `%_% Center Aligned %/%`
- `%>% Right Aligned %/%`
- `%-% Justified Text %/%`

### Interactive Buttons
Create buttons using the `={ label | action }=` syntax.

```markdown
={ Click Me | alert('Hello!') }=
```

### Color Chips
Any valid CSS color will be rendered as a chip:

- `#6750a4`
- `rgb(103, 80, 164)`
- `hsl(260, 31%, 42%)`

## Styling and Customization

LeorpioMD uses CSS variables for easy customization. You can override these in your own stylesheet:

```css
:root {
  --md-primary: #6750a4;
  --md-bg: #fdfcff;
  --md-radius: 14px;
}
```

To manually force dark mode, add `data-theme="dark"` to your `<html>` or a parent container.

## API Reference

### `parseMarkdown(input: string): string`
Renders a Markdown string into HTML.

### `md`
The underlying `markdown-it` instance, allowing you to add further plugins or customize settings.

## License

MIT (Assumed based on open-source nature)
