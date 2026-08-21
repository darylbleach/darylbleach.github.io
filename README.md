# darylbleach.github.io

Public site for Daryl Bleach's indie app portfolio.

## What's here

- `/` — portfolio homepage (Marketing URL for App Store / AdMob)
- `/app-ads.txt` — AdMob seller authorization
- `/<app>/privacy/` — privacy policy for each app
- `/<app>/support/` — support & FAQ for each app

Privacy and support pages are copied from each app's `www/privacy.html` and
`www/support.html` in the [apps](https://github.com/darylbleach/apps) monorepo.
When those files change, re-copy them here (or re-run the sync) before
shipping a listing update.

## Sync from the apps monorepo

From a machine that has both repos checked out:

```bash
APPS=/path/to/apps
PAGES=/path/to/darylbleach.github.io
for app in ante bento-merge bento-organiser bento-sort contour coop-escape \
  daily-vault digital-declutter fpl-assistant grid-zen hidden-rule \
  little-allotment outguess-ai pour-perfect rank-five reverse-tycoon scraps \
  spend-lens sub-track tessera; do
  mkdir -p "$PAGES/$app/privacy" "$PAGES/$app/support"
  cp "$APPS/$app/www/privacy.html" "$PAGES/$app/privacy/index.html"
  cp "$APPS/$app/www/support.html" "$PAGES/$app/support/index.html"
done
```

## URL pattern for App Store Connect

```
https://darylbleach.github.io/<app-folder>/privacy/
https://darylbleach.github.io/<app-folder>/support/
```

Example: Tessera privacy → `https://darylbleach.github.io/tessera/privacy/`
