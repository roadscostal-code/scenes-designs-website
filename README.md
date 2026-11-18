# SCENES DESIGNS | Interior & Architect — Website

Premium, responsive single-page website for SCENES DESIGNS, Virar West, Maharashtra.

Built with **React 19 · Vite · Tailwind CSS v4 · Framer Motion · Lucide React**.

## Requirements

- Node.js **18.18+** (Node 20 LTS recommended)
- npm

## Getting started

```bash
npm install
npm run dev        # http://localhost:5173
```

Production build:

```bash
npm run build      # outputs to /dist
npm run preview    # serves the production build locally
```

Deploy the `dist/` folder to any static host (Vercel, Netlify, Hostinger, cPanel, etc.).

## Project structure

```
scenes-designs/
├── public/
│   ├── images/          # All photography (WebP) + og-image.jpg
│   └── favicon/
├── src/
│   ├── components/      # Reusable UI: Navbar, Button, Lightbox, Loader, Footer, Reveal…
│   ├── sections/        # Page sections: Hero, About, Services, Projects, Process…
│   ├── pages/           # Home.jsx composes all sections
│   ├── hooks/           # useActiveSection, useScrolledPast, useLockBodyScroll
│   ├── data/            # ALL editable content lives here
│   ├── utils/           # WhatsApp / phone / email link helpers
│   ├── App.jsx
│   ├── main.jsx
│   └── index.css        # Tailwind + brand colour tokens
├── index.html           # SEO, Open Graph and structured data
├── vite.config.js
└── package.json
```

## Editing content

| What | File |
| --- | --- |
| Phone, email, address, map, WhatsApp number | `src/data/siteConfig.js` |
| Services (title, image, description, details) | `src/data/services.js` |
| Portfolio images & categories | `src/data/projects.js` |
| Process steps, Why Choose Us, Testimonials, form dropdowns | `src/data/content.js` |
| Navigation links | `src/data/navigation.js` |
| Colours & fonts | `src/index.css` (`@theme` block) |

### Replacing images

The images currently in `public/images/` are **representative visuals**, not completed SCENES DESIGNS projects.
Put real photographs in `public/images/` (WebP or JPG, ~1600px wide is ideal), update the paths in
`src/data/projects.js` / `services.js`, and set `showRepresentativeImageNote: false` in `siteConfig.js`.

### Testimonials

`src/data/content.js` contains **clearly marked sample placeholders** (`isSample: true`). Replace them with
genuine, client-approved reviews and set `isSample: false` — the "Sample content" badge then disappears automatically.

### Statistics / counters

Animated counters are hidden by default. Add only **verified** figures to `verifiedStats` in
`src/data/siteConfig.js`, e.g. `{ value: 120, suffix: '+', label: 'Projects Completed' }`.

## Contact form & WhatsApp

No paid API or backend is required.

- **Default (no backend):** the form validates inputs, then opens WhatsApp with the enquiry pre-filled. The
  visitor taps *Send* in WhatsApp. An "Or send by email instead" link opens the visitor's email app pre-filled.
  Limitation: the enquiry is only delivered once the visitor sends it from WhatsApp/email.
- **Optional backend:** create a free form endpoint (e.g. [Formspree](https://formspree.io)) and add it to a `.env` file:

```bash
VITE_FORM_ENDPOINT=https://formspree.io/f/your-id
```

The form will then POST JSON directly and show a success message.

### Changing the WhatsApp number

The default is `917276946251` (+91 72769 46251). Confirm this is the WhatsApp-enabled line. To change it,
edit `whatsappNumber` in `src/data/siteConfig.js` or set it in `.env`:

```bash
VITE_WHATSAPP_NUMBER=918779653223
```

See `.env.example`.

## SEO

- Title, meta description, Open Graph & Twitter cards, canonical URL and `InteriorDesigner` JSON-LD in `index.html`.
  Update the canonical/`og:url` if your domain differs from `https://scenesdesigns.in/`.
- Semantic HTML (`header`, `nav`, `main`, `section`, `address`, `footer`), labelled forms, keyboard-accessible
  lightbox and carousel, skip link, and reduced-motion support.
- All images are compressed WebP and lazy-loaded below the fold.
