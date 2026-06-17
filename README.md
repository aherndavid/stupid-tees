# stupid-tees.com

Single-page website for [stupid-tees.com](https://www.stupid-tees.com).

## Structure

```
/
├── index.html          ← the whole site lives here
└── assets/
    ├── tee-design-01.png
    ├── tee-design-02.png
    └── ...             ← add your transparent PNGs here
```

## Adding a design

1. Export your design as a **transparent PNG** (no background).
2. Drop it into `/assets/` named `tee-design-XX.png` (e.g. `tee-design-05.png`).
3. In `index.html`, duplicate one of the existing `<div class="product-card">` blocks and update:
   - `src="assets/tee-design-05.png"`
   - `alt="..."` description
   - The product name and price

The images use `mix-blend-mode: multiply` so they sit cleanly on the white background with no visible frame or box.

## Colours

| Token | Hex | Use |
|---|---|---|
| `--navy` | `#1A2744` | All text, borders, buttons |
| `--baby-blue` | `#87CEEB` | Accents, highlights |
| `--blue-light` | `#EBF6FC` | Section backgrounds |

## Deployment (GitHub Pages)

1. Push to `main` branch of `aherndavid/stupid-tees`.
2. In repo Settings → Pages → set source to `main` / `root`.
3. Point `www.stupid-tees.com` DNS to GitHub Pages (CNAME record).

Add a `CNAME` file to the repo root containing:
```
www.stupid-tees.com
```

## Contact form

The form currently simulates a submission (no backend). To wire it up for real, swap the `handleSubmit` function in `index.html` for a POST to [Formspree](https://formspree.io), [Netlify Forms](https://docs.netlify.com/forms/setup/), or your own endpoint.

### Formspree (easiest)

1. Sign up at formspree.io, create a form, get your endpoint.
2. Replace the `<form>` tag:
   ```html
   <form action="https://formspree.io/f/YOUR_ID" method="POST">
   ```
3. Remove the `onsubmit` handler and the JS `handleSubmit` function.
