# OpenMic GitHub Pages identity host

This directory is the root content for the `demonchant.github.io` GitHub Pages user site. It hosts the Digital Asset Links statement at `https://demonchant.github.io/.well-known/assetlinks.json` for the local APK's current debug signing certificate.

## Publish

The `demonchant/demonchant.github.io` repository must exist first. Copy the **contents** of this directory to that repository's root, then enable GitHub Pages from the `main` branch and `/ (root)`. The `.nojekyll` file is required so the `.well-known` directory is served as a static file. Do not publish this folder as a subdirectory under the existing `clockin` project site; Digital Asset Links must resolve at the identity domain root.

After publishing, verify that `https://demonchant.github.io/.well-known/assetlinks.json` returns this JSON directly with HTTP 200, not an HTML page or redirect. The app identity URI is `https://demonchant.github.io`.

## Signing key warning

The fingerprint in `assetlinks.json` matches the current locally installed APK, which is signed with the Android debug key. This is only for MWA development testing. Replace it with the fingerprint of the stable release signing key before distribution, and keep all private keystores and passwords outside Git. A hosted statement cannot authenticate APKs signed by any other certificate unless their fingerprints are explicitly listed.
