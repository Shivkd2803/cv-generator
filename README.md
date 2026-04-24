# ProCV — Professional Resume Builder

A fully client-side, zero-dependency resume builder with real-time preview, multiple professional templates, AI-powered writing assistance, and one-click PDF export. No sign-up required.

---

## ✨ Features

- **10 Professional Templates** — Executive, Modern, Creative, Minimal, MBZUAI, Harshibar, IEEE, Bold Dark, Elegant, and more
- **Live Preview** — CV renders instantly as you type
- **AI Enhancement** — AI-powered summary writing via the Anthropic API
- **PDF Export** — Print-optimized A4 export via a dedicated print view (`print.html`)
- **Dark / Light Editor** — Toggle between dark and light UI modes
- **Custom Accent Colors** — Choose from preset swatches or a custom color picker
- **Font Selection** — Switch between 12+ Google Fonts (DM Sans, Playfair Display, Merriweather, IBM Plex Sans, and more)
- **Photo Upload** — Optional profile photo with toggle per template
- **Draft Auto-Save** — Work is automatically saved to `localStorage` and restored on reload
- **Template Filtering** — Browse templates by category (Tech, Academic, Business, Creative, Healthcare, Law, Marketing)
- **No Backend Required** — Runs entirely in the browser; no server, no database, no account

### Supported CV Sections

- Personal Info (name, title, email, phone, location, nationality)
- Professional Summary
- Work Experience
- Education (with GPA)
- Projects (with links)
- Publications (with authors & venue)
- Skills (with optional proficiency levels)
- Certifications
- Languages
- Social / Website Links
- Profile Photo

---

## 🗂️ File Structure

```
├── index.html       # Landing page — hero, template gallery, how-it-works
├── builder.html     # Main resume editor with live preview panel
├── print.html       # Print/PDF helper — receives data and renders for printing
└── template.html    # (Reserved / additional template assets)
```

---

## 🚀 Getting Started

No build step or package manager needed.

**Option 1 — Open directly in a browser:**

```bash
# Clone the repo
git clone https://github.com/your-username/procv.git
cd procv

# Open index.html in your browser
open index.html
```

**Option 2 — Serve locally (recommended to avoid CORS issues with fonts/assets):**

```bash
# Python 3
python -m http.server 8080

# Node.js (npx)
npx serve .
```

Then visit `http://localhost:8080`.

---

## 🤖 AI Enhancement

The summary AI feature calls the **Anthropic Claude API** from the browser. To enable it:

1. Obtain an API key from [console.anthropic.com](https://console.anthropic.com)
2. In `builder.html`, locate the AI handler function and set your key — or proxy the request through a lightweight backend to keep the key server-side

> ⚠️ **Do not commit API keys to version control.** For production use, route AI requests through a server-side proxy.

---

## 🖨️ Exporting to PDF

1. Click **Download PDF** in the builder toolbar
2. A new tab opens with `print.html`, rendering your CV at A4 size
3. In the browser print dialog:
   - Set **Destination** → `Save as PDF`
   - Set **Margins** → `None`
   - Enable **Background graphics** for colored templates

---

## 🧩 Templates

| Template | Style | Best For |
|---|---|---|
| Executive | Single column, accent header bar | Corporate, Finance |
| Modern | Dark sidebar, skill bars | Tech, Product |
| Creative | Gradient accent strip | Design, Marketing |
| Minimal | Clean typographic | Any field |
| MBZUAI | Institutional dark header | Academia, Research |
| Harshibar | Ruled classic layout | Engineering, Academia |
| IEEE | Two-column conference format | Research, Publishing |
| Bold Dark | High-contrast dark header | Creative, Media |
| Elegant | Centered gold-accent | Finance, Law, Consulting |

---

## 🛠️ Customization

All styling is self-contained within each HTML file using CSS custom properties. Key variables in `builder.html`:

```css
:root {
  --accent: #E8472A;   /* Primary accent color */
  --bg: #0D0F14;       /* Editor background */
  --surface: #161820;  /* Panel surface */
}
```

To add a new template:

1. Add a renderer block inside the `renderCV()` function in `builder.html`
2. Add a corresponding thumbnail card in the template grid
3. Add a preview card in `index.html` with the correct `data-tags` attribute

---

## 🌐 Browser Support

Tested in modern evergreen browsers:

- Chrome / Edge 90+
- Firefox 88+
- Safari 14+

PDF export relies on the browser's native print-to-PDF feature.

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

## 🙏 Acknowledgements

- Fonts via [Google Fonts](https://fonts.google.com)
- PDF rendering via native browser print API
- AI summaries powered by [Anthropic Claude](https://www.anthropic.com)

