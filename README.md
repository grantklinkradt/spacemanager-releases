# Space Manager — release feed

This repository exists for one reason: to host `latest.json`, the file Space
Manager reads once per launch to find out whether a newer version exists.

It is public **only** so that copies of the app can reach the file. The app's
source lives elsewhere and is not published here.

## Why not a custom domain

The obvious host, `spacemanager.app`, is registered to someone else. An update
feed on a domain you do not control means whoever does control it can decide
what your users are told to download — so the feed lives here, on an account
this project owns, until a domain is genuinely bought.

## What the app does with this file

It compares `version` against its own. If this file names a newer version, the
app shows a quiet banner with a link. **It never downloads or installs
anything** — clicking the link opens the page in the browser, so macOS does the
verifying. `download_url` and `notes_url` must be `https` with a real host or
the app ignores the entry entirely.

## Releasing

1. Attach the notarized DMG to a GitHub Release in this repository.
2. Bump `version` here to match, and update `notes`.

Nothing else reads this file.
