# Deferred Work Log

- 2026-04-27: `nightly.yml` keeps `actions/checkout` credentials persisted for
  the private `ontypehq/OnType` checkout because the source repo currently has
  an orphan `design/flag-icons` gitlink without `.gitmodules`, which makes
  checkout's credential cleanup fail via `git submodule foreach`. Clean up the
  orphan gitlink in `OnType`, then restore `persist-credentials: false`.
