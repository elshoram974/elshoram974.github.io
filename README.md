# elshoram974.github.io

GitHub Pages user site for **MRE Code**.

## Structure

| Path | Purpose |
| --- | --- |
| `index.html` | Site root. App overview, Google Drive OAuth scope justification, and privacy summary (the page Google review reads). |
| `mre_cashbook_home.html` | Legacy URL, kept alive — redirects to `privacy_mre_cashbook/home.html`. |
| `google8a31eb1a392dc463.html` | Google Search Console ownership verification. Do not delete or rename. |
| `robots.txt` | Root robots file — the only one crawlers read for this domain. |
| `sitemap.xml` | Root sitemap covering all public pages. |
| `privacy_mre_cashbook/` | The full MRE CashBook site, moved here from the standalone `privacy_mre_cashbook` repository. |

## Why `privacy_mre_cashbook/` is a folder

The published apps ship these exact URLs, so they must keep working:

- `https://elshoram974.github.io/privacy_mre_cashbook/` — privacy policy (9 languages)
- `https://elshoram974.github.io/privacy_mre_cashbook/home.html` — app home page
- `https://elshoram974.github.io/privacy_mre_cashbook/assets/...` — images

Serving that content from a folder of the same name inside this user site reproduces
every URL byte for byte, so the old repository can be retired without breaking any
live link.

> **Important:** GitHub Pages gives a project site precedence over a same-named folder
> in the user site. Pages must be disabled on (or the repository deleted from)
> `elshoram974/privacy_mre_cashbook` before the folder here starts serving.
