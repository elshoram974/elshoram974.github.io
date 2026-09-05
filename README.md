# elshoram974.github.io

GitHub Pages user site for **MRE Code**. The root is a hub, so more apps can be added
next to MRE CashBook without disturbing anything already published.

## Layout

| Path | Purpose |
| --- | --- |
| `index.html` | Site root — MRE Code hub. Lists the apps and links to each app's pages. |
| `mre_cashbook_home.html` | **MRE CashBook landing page.** Canonical URL for the app: features, screenshots, FAQ, store links. |
| `mre_cashbook_privacy.html` | MRE CashBook Google API data disclosure: the `drive.appdata` scope and the Limited Use commitment. |
| `privacy_mre_cashbook/` | MRE CashBook privacy policy in 9 languages, plus the legacy copy of the landing page. See below. |
| `assets/` | Shared images — app icon, Open Graph image, store screenshots. |
| `google8a31eb1a392dc463.html` | Google Search Console ownership verification. Do not delete or rename. |
| `robots.txt` | Root robots file — the only one crawlers read for this domain. |
| `sitemap.xml` | Root sitemap covering every public page. |

Naming convention for future apps: prefix root-level pages with the app name,
e.g. `mre_cashbook_home.html`, `mre_cashbook_privacy.html`.

## Why `privacy_mre_cashbook/` is a folder here

The published apps ship these exact URLs, so they must keep resolving:

- `https://elshoram974.github.io/privacy_mre_cashbook/` — privacy policy, 9 languages
- `https://elshoram974.github.io/privacy_mre_cashbook/home.html` — landing page
- `https://elshoram974.github.io/privacy_mre_cashbook/assets/...` — images

Serving that content from a folder of the same name inside this user site reproduces
every URL byte for byte, so the standalone `privacy_mre_cashbook` repository can be
retired without breaking a single live link.

`privacy_mre_cashbook/home.html` is kept as-is except for its `<link rel="canonical">`,
which now points at `/mre_cashbook_home.html`. The page still works for anyone opening
the old link from inside the app, while search engines credit the root landing page.
Its `assets/` copy stays in place because those image URLs are already indexed.

## Editing

- The privacy policy (`privacy_mre_cashbook/index.html`) is also rendered inside the app,
  which is why it carries its own theme and language switcher. Keep it self-contained.
- After changing any URL, resubmit `sitemap.xml` in Google Search Console.

## Deploying

Pushing to `main` publishes the site. **One caveat:** GitHub Pages gives a project site
precedence over a same-named folder in the user site. Pages must be disabled on (or the
repository deleted from) `elshoram974/privacy_mre_cashbook` before the `privacy_mre_cashbook/`
folder here starts serving.

## Download MRE CashBook

- Google Play — <https://play.google.com/store/apps/details?id=net.mrecode.mrecashbook>
- App Store — <https://apps.apple.com/app/id6760567168>
- Huawei AppGallery — <https://appgallery.huawei.com/app/C117118621>
