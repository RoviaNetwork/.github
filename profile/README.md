# RoviaNetwork

Rovia is a pre-alpha, iOS-first, privacy-first network client built around an
engine-independent canonical core: explainable routing, deterministic
failover, working subscription import, and (pending) one real tunnel engine.

## Status (2026-09-29)

- Works: subscription add/refresh over URL, clipboard, paste and
  `rovia://import` deep links; honest accepted/rejected counts; Keychain
  secrets; file store with last-good rollback; TCP latency probing;
  search/favorites; Xray config compilation with secret placeholders.
- Stub: tunnel runtime (`prepare`/`start` — no LibXray artifact built yet,
  no device verification).
- Not production-ready: no verified tunnel on device, no macOS client.

## Repositories

- [RoviaNetwork/rovia](https://github.com/RoviaNetwork/rovia) — iOS app,
  Apple platform integration, UI, release pipeline. Consumes `rovia-core`
  as a pinned SPM dependency (exact version), never as a checkout.
- [RoviaNetwork/rovia-core](https://github.com/RoviaNetwork/rovia-core) —
  canonical core: config models, subscription parsing/fetch/import/store,
  routing evaluation, engine contracts. No UI, no network in tests.
- [RoviaNetwork/rovia-engine](https://github.com/RoviaNetwork/rovia-engine) —
  engine integration: Xray/sing-box adapters, config compilation, artifact
  builds. Pinned to `rovia-core`. Production choice: Xray via libXray.
- `.github` (this repo) — organization profile and shared templates.

Dependency direction: `rovia` → `rovia-core` ← `rovia-engine`. No cycles.

## Supported platforms

iOS 17+ (Xcode 26.3, Swift 6.2). macOS client does not exist yet;
iOS Simulator is not a substitute for device tunnel verification.
