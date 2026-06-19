# straiker-webflow-embeds

Hosted CSS/JS for **Straiker**'s Webflow homepage section embeds, served via [jsDelivr](https://www.jsdelivr.com/).
Generated and maintained from Absurdity's internal Webflow workspace — **that workspace is the source of truth; do not hand-edit these files**, regenerate and re-push.

## Section 2 — Attack Surface

| File | Purpose |
|------|---------|
| `section-attack-surface.css` | Styles for the scroll-scrubbed attack-surface animation. Inherits the live site's `--fonts--*` tokens (Pressio / Inter / Roboto Mono / VT323) — loads no fonts of its own. |
| `section-attack-surface.js` | The animation engine (mounts into `#straiker-attack-surface`, self-contained window-scroll scrub). |

### Usage (Webflow)

A small **loader** embed (one Webflow Code Embed) references these via jsDelivr, **pinned to a commit** for an immutable URL, with **Subresource Integrity (SRI)** so the browser rejects any altered content:

```html
<link rel="stylesheet"
      href="https://cdn.jsdelivr.net/gh/absurdity-studio/straiker-webflow-embeds@<commit>/section-attack-surface.css"
      integrity="sha384-…" crossorigin="anonymous">
<!-- markup div + a lazy-loader that injects the JS as the section approaches the viewport -->
```

Pinning to a commit (not `@main`) means an update is an explicit version bump — nothing changes on the live site until the loader's URL + SRI hash are updated.
