# gentropic.org/security

The GCU **security wing** — what a security reviewer or IT team lands on to evaluate GCU artifacts for use
in a locked-down environment. Served at **https://gentropic.org/security** (GitHub project Pages).

**This repo is itself a hardened static artifact.** `index.html` is switchboard-**LIGHT-only**, static,
**script-free**, with fonts vendored same-origin (no CDN) — it passes the capability declaration it
describes. *View source; that's the point.*

## Layout
- `index.html` — the page (self-contained styling, vendored fonts, no JS).
- `.well-known/security.txt` — RFC 9116 contact + policy. *(Canonical copy belongs at the domain root in
  `gentropic.github.io`; TODO.)*
- `artifacts/<tool>/` — the **blessed-artifacts inventory**: `capability.json` (machine-readable capability
  declaration), `csp.txt` (the CSP the tool runs under), `sbom.json` (CycloneDX). The provenance-governance
  model made literal and versioned with the repo.
- `fonts/` — vendored Barlow + Space Mono (OFL).

## Build-emitted values
Hashes, the SBOM, the pinned CSP, and the release tag are emitted by the **source build** (the `auditable`
repo, for lamina) and slotted in per release — they appear as marked placeholders until then. A Zenodo DOI
(minted separately, when a release is frozen as a citable record) is planned, not yet issued.

## Scope — the inter-trench wall
This wing presents the **GCU-generic** capability + verification story. **No client / employer specifics**
(intake processes, named deployments, COI details) live here — those stay private. The *capability* is
public; a *specific deployment* is not.

Pilot tool: **lamina**. The catalog grows from there — each new tool fills the same artifact template.
