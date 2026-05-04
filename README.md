# whtnxt-diagrams

Public host for `.drawio` source files used in Whtnxt internal documentation. Files in this repo are served as raw URLs and rendered inline via the self-hosted Drawio instance at `https://drawio.whtnxt.io`, embedded into Outline docs and wiki references.

## Why this repo exists

Outline's Drawio integration needs `.drawio` files to be reachable over HTTP to render inline. The Whtnxt vault is local-only by design (most pages are private synthesis). This repo holds only the diagrams that need public hosting — nothing else from the vault leaks here.

## Layout

```
<venture-or-context>/
  <diagram-name>.drawio
```

Example: `whtnxt-aaas/owner-flow.drawio`

## Embed pattern

Render any diagram inline by pasting this URL on its own line in an Outline doc:

```
https://drawio.whtnxt.io/?lightbox=1&edit=_blank&layers=1&nav=1&url=https://raw.githubusercontent.com/pbmagnet4/whtnxt-diagrams/main/<path>.drawio
```

Outline's diagrams integration detects the drawio.whtnxt.io host and renders as an interactive iframe.

## Authoring workflow

Source of truth lives in the [Whtnxt Agent Vault](file:///Users/echalupa/Documents/Whtnxt%20Agent%20Vault/) under `Ventures/<name>/`. Files are copied here on publish. Treat this repo as a publishing target, not the editing surface.

The `/drawio` skill in the Whtnxt Agent workspace handles: render → push to this repo → return the embed URL → optionally inject into a target Outline doc.
