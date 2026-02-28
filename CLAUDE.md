# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Repo Is

Single-page marketing site for **SIA KLBTransport** — moving, furniture delivery, waste removal, and loader services in Riga and Latvia.
- Language: Latvian (`lang="lv"`), with LV/RU/EN switcher
- Stack: single HTML file + inline CSS + inline JS. No framework, no build step.
- Hosted on GitHub Pages via Actions workflow (`.github/workflows/deploy-pages.yml`)
- No custom domain (no CNAME file)

## Section Map

The site is a single-page app using anchor navigation. All sections live in `index.html`:

| Anchor | Section | Content |
|---|---|---|
| `#hero` | Hero | Headline, callback widget, CTA buttons |
| `#values` | Values | Company value propositions |
| `#svc` | Pakalpojumi (Services) | 10 service cards with CTAs |
| `#flow` | Flow | How-it-works steps |
| `#about` | Par mums (About) | Company info, call button |
| `#proof` | Proof | Scanned testimonial images |
| `#widgets` | Widgets | Cost calculator / estimation tools |
| `#why` | Priekšrocības (Why us) | Advantage cards |
| `#contact` | Kontakti (Contact) | Contact form (`sendForm()`), phone, email, address, map |
| `#testimonials` | Testimonials | Client reviews |
| `#partners` | Partners | Partner logos |
| (footer) | Footer | Company details, reg. nr., links |
| (map) | Google Maps | Embedded iframe (Dzelzavas iela 72, Rīga) |

## i18n (3 Languages)

Language switching is handled client-side via `data-lang` attributes on elements. Buttons in the header toggle between LV, RU, and EN. All translatable elements have IDs and `data-lang` values set via inline JS.

When adding or editing text content:
- Update text for **all 3 languages** (LV, RU, EN) in the JS translation object
- Every translatable element needs a unique `id` attribute

## Contact & Forms

- **Phone:** +371 26 414 900, +371 26 179 179
- **Email:** info@klbtransport.lv
- **Address:** Dzelzavas iela 72, Rīga, LV-1082
- **Company:** SIA KLBTransport, Reģ. nr. LV40103710874
- **Bank:** LV71HABA0551037116856
- **Contact form:** Uses `sendForm()` function (inline JS) — no Formspree
- **Hero callback widget:** Quick phone number form in hero section

## Deployment

- Push to `main` triggers `.github/workflows/deploy-pages.yml`
- Uploads entire repo root as Pages artifact — no build step
- Manual deploy available via `workflow_dispatch`

## Do Not Touch (Without Explicit Request)

- `.github/workflows/deploy-pages.yml` — deployment pipeline
- `img/` files — referenced throughout the page
- Company registration, bank, and contact details — legal information
- Google Maps embed URL
