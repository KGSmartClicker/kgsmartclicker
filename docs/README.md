# KG Smart Clicker — Landing Page

A premium, dark-mode landing page for KG Smart Clicker. Built with pure HTML, CSS, and vanilla JavaScript — no frameworks or libraries (except Google Fonts).

## Hosting on GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Source**, select **Deploy from a branch**.
4. Choose **main** branch and **/docs** folder.
5. Click **Save**. Your site will be live at `https://<username>.github.io/<repo>/`.

Alternatively, deploy from the root by copying the contents of `docs/` to the repo root.

## Replacing the Formspree Endpoint

1. Sign up at [formspree.io](https://formspree.io).
2. Create a new form and copy your form ID (e.g. `xwkgjzpl`).
3. In `index.html`, find:
   ```html
   action="https://formspree.io/f/your-form-id"
   ```
4. Replace `your-form-id` with your actual form ID.
5. In `script.js`, remove the `e.preventDefault()` block inside the submit handler (see the comment in the code) so the form posts to Formspree.

## Changing Colors

All colors are defined as CSS custom properties at the top of `style.css`:

```css
:root {
  --purple-400: #a78bfa;
  --purple-500: #8b5cf6;
  --purple-600: #7c3aed;
  --blue-400: #60a5fa;
  --blue-500: #3b82f6;
  --bg-primary: #0a0a0f;
  --bg-secondary: #12121a;
  /* ... */
}
```

Change these values to update the entire color scheme.

## Replacing Screenshots

The screenshots section uses CSS-drawn mockups by default. To use real screenshots:

1. Add your images to the `images/` folder.
2. In `index.html`, replace the `.screenshot-body` content inside each `.slide` with:
   ```html
   <img src="images/screenshot-1.png" alt="Dashboard view" loading="lazy" width="800" height="500">
   ```
3. Adjust the `.screenshot-body` styles in `style.css` if needed.

## Customizing Text

All text content is in `index.html`. Key sections to edit:

- **Hero**: headline, subheading, badge text, stats
- **Features**: card titles and descriptions
- **How It Works**: step titles and descriptions
- **FAQ**: question/answer pairs (inside `<details>` elements)
- **Form**: labels, placeholders, button text
- **Footer**: tagline, links, copyright year

## Adding a Favicon

Replace `images/favicon.svg` with your own favicon. For full browser support, also add:

- `images/favicon.ico` (32x32)
- `images/apple-touch-icon.png` (180x180)

Update the `<link>` tags in `index.html` accordingly.

## Open Graph Image

Replace `images/og-image.png` with a 1200x630 image for social media sharing. Update the URL in the `<meta>` tags in `index.html`.

## Performance Notes

- No external dependencies (except Google Fonts)
- CSS animations use `transform` and `opacity` for GPU acceleration
- Images use `loading="lazy"` when applicable
- `prefers-reduced-motion` is respected
- Semantic HTML with proper ARIA attributes

## Browser Support

Modern browsers (Chrome, Firefox, Safari, Edge). Glassmorphism (`backdrop-filter`) has broad support but gracefully degrades in older browsers.
