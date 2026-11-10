# JLBS Software website

Static company site for [jlbsoftware.com.br](https://jlbsoftware.com.br). Hand-written HTML and CSS, no build step and no JavaScript (JSON-LD on the home pages only).

## Local preview

From the repository root:

```bash
python3 -m http.server
```

Then open `http://127.0.0.1:8000/`.

## Structure

| Path | Page |
|---|---|
| `/` | Home (pt-BR) |
| `/en/` | Home (English) |
| `/privacidade` | Privacy policy (pt-BR) |
| `/seguranca` | Security summary (pt-BR) |
| `/404.html` | Not-found page |
| `/assets/style.css` | Stylesheet |
| `/og-image.png` | Open Graph image (1200×630) |
| `/.well-known/security.txt` | Vulnerability disclosure contact |

Internal links are root-absolute and omit `.html` (`/privacidade`, `/en/`, `/#produto`). Assets also use root-absolute paths so `404.html` still loads CSS when GitHub Pages serves it from an unknown URL.

## GitHub Pages

The site is meant to be served from the repository root on GitHub Pages, with the custom domain in `CNAME` (`jlbsoftware.com.br`). `.nojekyll` is present so GitHub Pages does not run Jekyll and will serve `/.well-known/`.

## Cloudflare `_headers`

`_headers` is the Cloudflare Pages security-headers file (HSTS, nosniff, Referrer-Policy, Permissions-Policy, CSP). GitHub Pages ignores it. The same CSP is also set as a `<meta http-equiv>` tag on every page.
