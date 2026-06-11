<!-- PRINTED ON BUSINESS CARDS — do not remove or rename /andrew, /ben, /andrew.vcf, /ben.vcf. -->

# octl.ai

The octl landing page — a static site (plain HTML, no build step) served from
this repo. `index.html` is the homepage; `creature-feature.html` is linked from
it. The custom domain is set via `CNAME` (`octl.ai`).

## Business card QR pages

Personal contact pages for the cofounders' business-card QR codes.

> **PRINTED ON BUSINESS CARDS — do not remove or rename `/andrew`, `/ben`,
> `/andrew.vcf`, `/ben.vcf`.** The printed QR codes encode
> `https://octl.ai/andrew` and `https://octl.ai/ben`. Renaming or deleting any
> of these paths breaks every card already in the wild.

### Routes

| Path                     | File                  | Purpose                                  |
| ------------------------ | --------------------- | ---------------------------------------- |
| `/andrew`, `/andrew/`    | `andrew/index.html`   | Andrew Yi's contact page                 |
| `/ben`, `/ben/`          | `ben/index.html`      | Ben (Benjamin) Yi's contact page         |
| `/andrew.vcf`            | `andrew.vcf`          | Andrew's vCard (Save contact button)     |
| `/ben.vcf`               | `ben.vcf`             | Ben's vCard (Save contact button)        |

Both the slashless (`/andrew`) and trailing-slash (`/andrew/`) forms resolve:
the pages live at `andrew/index.html` / `ben/index.html`, and the host serves
`index.html` for the directory (GitHub Pages 301-redirects `/andrew` →
`/andrew/`).

### Editing contact details

- **Page content** (name, title, links) — edit `andrew/index.html` /
  `ben/index.html`. The outbound LinkedIn and GitHub links carry
  `?utm_source=business_card&utm_medium=qr&utm_content=andrew|ben`; the
  `mailto:` link and the `.vcf` download do **not**.
- **Saved contact card** — edit `andrew.vcf` / `ben.vcf` (vCard 3.0). Keep these
  in sync with the page. vCard URLs intentionally omit UTM params.
- The pages reuse the homepage's design tokens (deep-ocean background, Fraunces
  + Martian Mono fonts, `#f2d8ba` accent) inline; there is no shared stylesheet.

### Serving `.vcf` with the right MIME type

Where the host allows header config, serve `*.vcf` as `text/vcard`. GitHub Pages
does not allow custom headers, so the `.vcf` extension is relied on instead —
iOS and Android both import the files correctly from the extension.
