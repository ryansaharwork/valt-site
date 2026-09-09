# valt-site

The public website for **Valt**, an iOS game logging app. It is a handful of
static HTML files published with GitHub Pages at <https://thevalt.app>.

There is no build step, no framework, and no JavaScript. What is in this
repository is exactly what gets served.

## URLs must not change

These pages are linked from **inside the iOS app** and from the **App Store
Connect** listing. Apple's review process checks the privacy policy URL, and
builds already in the App Store point at these paths.

A filename here is a published URL. Once a page is live:

- Do not rename it.
- Do not move it into a subdirectory.
- Do not delete it.

To retire a page, replace its contents. Keep the path alive.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Landing page, links to everything else |
| `privacy.html` | Privacy policy, referenced by the app and App Store Connect |
| `style.css` | Shared stylesheet for every page |
| `CNAME` | Custom domain for GitHub Pages |
| `.nojekyll` | Serves the directory as-is, skipping Jekyll |

## Adding a page

Copy the shell from `index.html`, change the `<title>` and the content, and add
a link to it from the list on the index. One file per page, at the repository
root, and the filename is the URL. Keep the `<link rel="stylesheet">` relative
so the site works at a custom domain, at a `github.io` project path, and when
opened straight from disk.

Pages must stay self-contained. No analytics, no web fonts, no CDN, no external
images, nothing loaded from a third party domain. The only subresource any page
requests is `style.css`.

## Custom domain

`CNAME` contains the domain and the repository's Pages setting contains the same
domain. They are one knob in two places. Editing this file without updating the
repository setting, or the reverse, takes the site down.
