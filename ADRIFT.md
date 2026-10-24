# Adrift Browser core fork

This repository is the Adrift Browser patch set. It is a fork of
[Helium](https://github.com/imputnet/helium) and keeps the upstream patch
series, build tooling, licenses, and authorship notices.

- Adrift wrapper: https://github.com/eliamarinen/adrift-macos
- Adrift core: https://github.com/eliamarinen/Adrift
- Upstream wrapper: https://github.com/imputnet/helium-macos
- Upstream core: https://github.com/imputnet/helium

The Chromium revision is the same gitlink used by the macOS wrapper. Adrift
does not maintain or redistribute a modified Chromium archive; changes are
expressed as patch-series entries against that revision.

## Adrift patch series

The Adrift entries are applied after the Helium series:

1. `patches/adrift/core/branding.patch` — product/bundle identity, crash
   product name, credits, and third-party notice.
2. `patches/adrift/core/layout-defaults.patch` — vertical-only initial layout,
   minimal URL, frameless mode with pinned sidebar/top bar.
3. `patches/adrift/core/vertical-only.patch` — normalizes existing profiles to
   vertical layout and removes layout-switching surfaces.
4. `patches/adrift/core/identity-endpoints.patch` — `adrift://` WebUI alias,
   Adrift update feed and issue routing, and disabled official-build crash
   uploads.

The platform-specific identity patch lives in the wrapper at
`patches/adrift/macos/identity.patch`.

## Build-time name substitution

`utils/name_substitution.py` now maps Chrome/Chromium/Helium display strings to
Adrift and rewrites the internal WebUI alias to `adrift://`. The
`Helium services` label is intentionally left attributed to Helium while the
feature backend still points at the upstream service origin. This is a
pre-beta blocker recorded in the wrapper's `docs/adrift-status.md`.

## License

Adrift changes are GPL-3.0. Upstream Helium, ungoogled-chromium, and Chromium
licenses and notices are retained; see `LICENSE` and
`LICENSE.ungoogled_chromium`.
