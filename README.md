<p align="center">
  <a href="https://getontype.app">
    <img src="https://github.com/ontypehq/.github/raw/main/assets/hero-banner.webp" alt="OnType — Speak, and it types." width="720" />
  </a>
</p>

<p align="center">
  <strong>The fastest way to input text on macOS.</strong><br>
  Hold a key, say what you mean, and watch it appear — anywhere, instantly.
</p>

<p align="center">
  <a href="https://github.com/ontypehq/ontype-releases/releases/latest"><img src="https://img.shields.io/github/v/release/ontypehq/ontype-releases?label=download&style=flat-square" alt="Latest Release" /></a>
  <a href="https://github.com/ontypehq/ontype-releases/issues"><img src="https://img.shields.io/github/issues/ontypehq/ontype-releases?style=flat-square" alt="Issues" /></a>
  <a href="https://getontype.app"><img src="https://img.shields.io/badge/website-getontype.app-blue?style=flat-square" alt="Website" /></a>
</p>

---

## Download

Grab the latest `.dmg` from [**Releases**](https://github.com/ontypehq/ontype-releases/releases/latest).

**Requirements:** macOS 15+ (Sequoia), Apple Silicon (M1 or later).

Nightly builds are published as the rolling
[nightly prerelease](https://github.com/ontypehq/ontype-releases/releases/tag/nightly).

## CI

This public repository hosts the macOS nightly build workflow so GitHub-hosted
macOS minutes are available to the release pipeline. The workflow checks out the
private source repositories at build time:

- `ontypehq/OnType`
- `ontypehq/libfst`
- `ontypehq/itn`

Required repository secrets:

- `ONTYPE_SOURCE_TOKEN`: token with read access to the private source repos.
- `NOTARY_KEY_P8_BASE64`: base64-encoded App Store Connect API key file
  (`AuthKey_UPM4638DP7.p8` locally).
- OnType release env copied from the private app repo `.env`: `ONTYPE_AUTH_BASE_URL`,
  `ONTYPE_AUTH_BASE_URL_DEV`, `ONTYPE_AUTH_BASE_URL_PROD`, `CONVEX_URL_DEV`,
  `CONVEX_URL_PROD`, `DEVELOPER_ID_CERT_BASE64`, `P12_PASSWORD`,
  `KEYCHAIN_PASSWORD`, `APPLE_ID`, `APPLE_ID_PWD`, `APPLE_TEAM_ID`,
  `NOTARY_KEY_ID`, `NOTARY_ISSUER_ID`, `CF_ACCOUNT_ID`, `CF_R2_BUCKET`,
  `CF_R2_ACCESS_KEY_ID`, `CF_R2_SECRET_ACCESS_KEY`, `CF_R2_ENDPOINT`,
  `CF_ASSETS_BASE_URL`, `SPARKLE_ED_PRIVATE_KEY`, `SENTRY_ORG`,
  `SENTRY_PROJECT`, `SENTRY_AUTH_TOKEN`, and `SENTRY_TRACES_SAMPLE_RATE`.

Nightly builds intentionally do not run `bun run app:release --publish`; they
produce notarized DMGs and attach them to GitHub Releases only. Sparkle/R2
publishing should stay on a separate, explicitly approved workflow.

## How it works

**Hold** your hotkey → **Speak** naturally → **Release** to type. That's it.

OnType runs on-device AI to transcribe your voice in real time. Your audio never leaves your Mac.

## Features

- **On-device ASR** — Powered by [MLX](https://github.com/ml-explore/mlx) on Apple Silicon. No cloud, no latency, no subscriptions.
- **Works everywhere** — Any text field in any app. Xcode, Slack, Notes, browsers, terminals.
- **AI rewriting** — Optionally clean up grammar, formatting, or tone after transcription.
- **Privacy by default** — 100% offline capable. Zero telemetry. Your voice data stays on your machine.

## Feedback

Found a bug or have a feature request? [Open an issue](https://github.com/ontypehq/ontype-releases/issues/new/choose).

## Links

- [Website](https://getontype.app)
- [Changelog](https://github.com/ontypehq/ontype-releases/releases)
