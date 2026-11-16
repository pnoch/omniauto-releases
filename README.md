# OmniAuto releases

Landing and test-build download page for OmniAuto. The application source lives
in a separate private repository.

## Website

The page is in `docs/` and is served by GitHub Pages at
<https://omniauto.siamcreations.app/> (custom domain) and
<https://pnoch.github.io/omniauto-releases/> (project URL until the custom
domain is live).

- **Custom domain:** `docs/CNAME` contains
  `omniauto.siamcreations.app`. The IONOS zone uses a `CNAME` record for
  `omniauto` pointing to `pnoch.github.io`; the old MX/SPF, autodiscover and
  DKIM records at the app subdomain were removed. If a CNAME cannot be used,
  GitHub Pages' A/AAAA addresses are:
  - `185.199.108.153`, `185.199.109.153`, `185.199.110.153`,
    `185.199.111.153`
  - `2606:50c0:8000::153`, `2606:50c0:8001::153`,
    `2606:50c0:8002::153`, `2606:50c0:8003::153`
- **Pages source:** `main` / `docs`, with HTTPS enforced after DNS verifies.
- **Android download:** the page reads the rolling `android-latest` release in
  this repository through the GitHub API and links the first `.apk` asset.
  Publish a new test build by replacing that release's asset (or deleting and
  recreating the tag). Name the asset
  `omniauto-<version>-debug-test-<hash>.apk`; the page shows the version and
  size automatically.
- **Current build:** `omniauto-0.3-debug-test-3b03c17c.apk`, SHA-256
  `3b03c17c29611b0724bdc86f29ffc2e424da4f10270e7f18dc15781cf00271a2`.
  This is a debug-signed test build, not a production release.

## Updating screenshots

Replace `docs/screenshots/player-fullscreen.png` (wide 1280×720) and
`docs/screenshots/player-sheet.png` (phone portrait) with fresh captures. Keep
the cluster image at `docs/screenshots/cluster-cue.png`.

## Updating the page

Edit `docs/index.html` for copy or the current SHA-256 line, then push to
`main`. GitHub Pages rebuilds from `docs/`.

## DNS / HTTPS

After the `omniauto` CNAME is live, GitHub Pages verifies the domain and issues
the certificate. In the repository's **Settings → Pages**, confirm the custom
domain is `omniauto.siamcreations.app` and enable **Enforce HTTPS**. The project
URL remains available until then.
