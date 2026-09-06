# elshoram974.github.io

GitHub Pages user site for **MRE Code**. The root is a hub, so more apps can be added
next to MRE CashBook without disturbing anything already published.

## Layout

| Path                                            | Serves                                 | Purpose                                                                                            |
| ----------------------------------------------- | -------------------------------------- | -------------------------------------------------------------------------------------------------- |
| `index.html`                                    | `/`                                    | MRE Code hub. Lists the apps and links to each app's pages.                                        |
| `mre_cashbook_home/index.html`                  | `/mre_cashbook_home/`                  | **MRE CashBook landing page.** Canonical URL for the app: features, screenshots, FAQ, store links. |
| `mre_cashbook_privacy_not_important/index.html` | `/mre_cashbook_privacy_not_important/` | MRE CashBook Google API data disclosure: the `drive.appdata` scope and the Limited Use commitment. |
| `privacy_mre_cashbook/`                         | `/privacy_mre_cashbook/`               | MRE CashBook privacy policy in 9 languages, plus the legacy copy of the landing page. See below.   |
| `404.html`                                      | any missing URL                        | Not-found page. GitHub Pages serves it automatically.                                              |
| `assets/`                                       | `/assets/`                             | Shared images — Open Graph image and store screenshots.                                            |
| `google8a31eb1a392dc463.html`                   | —                                      | Google Search Console ownership verification. Do not delete or rename.                             |
| `robots.txt`                                    | `/robots.txt`                          | Root robots file — the only one crawlers read for this domain.                                     |
| `sitemap.xml`                                   | `/sitemap.xml`                         | Root sitemap covering every public page.                                                           |

Pages live in a folder as `index.html` so the URL is a clean `/name/` with no `.html`.
GitHub Pages resolves `/name/` to `/name/index.html` automatically.

`mre_cashbook_home.html` and `mre_cashbook_privacy_not_important.html` remain at the root as `noindex`
redirect stubs, because those flat URLs were briefly published. They can be deleted once
Search Console shows no traffic on them.

**Adding an app:** create `<app_name>/index.html`, link it from the hub, and add it to
`sitemap.xml`.

## Why `privacy_mre_cashbook/` is a folder here

The published apps ship these exact URLs, so they must keep resolving:

- `https://elshoram974.github.io/privacy_mre_cashbook/` — privacy policy, 9 languages
- `https://elshoram974.github.io/privacy_mre_cashbook/home.html` — landing page
- `https://elshoram974.github.io/privacy_mre_cashbook/assets/...` — images

Serving that content from a folder of the same name inside this user site reproduces
every URL byte for byte, so the standalone `privacy_mre_cashbook` repository can be
retired without breaking a single live link.

`privacy_mre_cashbook/home.html` is kept as-is except for its `<link rel="canonical">`,
which now points at `/mre_cashbook_home/`. The page still works for anyone opening the
old link from inside the app, while search engines credit the current landing page.
Its `assets/` copy stays in place because those image URLs are already indexed.

## Editing the privacy policy

`privacy_mre_cashbook/index.html` is also rendered **inside the app**, which is why it
carries its own theme handling and language switcher. Keep it self-contained, and note
that it detects the app through the `MRECashBookApp` user agent to hide the logo, the
language picker and the site link row. Anything added to that page must stay behind the
same check if it should not appear in the app.

## Deploying

Pushing to `main` publishes the site. **One caveat:** GitHub Pages gives a project site
precedence over a same-named folder in the user site. Pages must be disabled on (or the
repository deleted from) `elshoram974/privacy_mre_cashbook` before the `privacy_mre_cashbook/`
folder here starts serving. To check which source is live:

```bash
curl -s https://elshoram974.github.io/privacy_mre_cashbook/ | grep site-links
```

Output means this repository is serving it; no output means the old repository still is.

After any URL change, resubmit `sitemap.xml` in Google Search Console.

## Download MRE CashBook

- Google Play — <https://play.google.com/store/apps/details?id=net.mrecode.mrecashbook>
- App Store — <https://apps.apple.com/app/id6760567168>
- Huawei AppGallery — <https://appgallery.huawei.com/app/C117118621>
