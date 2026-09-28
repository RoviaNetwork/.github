# RoviaNetwork

Rovia is a pre-alpha, iOS-first, privacy-first network client built around an
engine-independent canonical core: explainable routing, deterministic
failover, offline subscription inspection.

## Status (2026-09-28, verified on HEAD `606c6b5`)

- Works: offline parsing of `vless://`, `trojan://`, `ss://` share links;
  redacted local inspection; routing explanation; Swift + Python CI.
- Stub: tunnel engines (`xray`, `sing-box` return `notIncludedInBuild`);
  the app boots on `StaticFixtureProvider` + `UnavailableTunnelController`;
  no subscription download yet — that is the current priority.
- Not production-ready: no verified tunnel on device, no macOS client.

## Repositories

- [RoviaNetwork/rovia](https://github.com/RoviaNetwork/rovia) — monorepo:
  iOS app, canonical core packages, engine adapters, CI and docs.
  Split into `rovia-core` / `rovia-engine` follows after the working
  subscription flow lands (transfer history is preserved; premature splits
  would only multiply integration risk).
- `.github` (this repo) — organization profile and shared templates.

## Supported platforms

iOS 17+ (Xcode 26.3, Swift 6.2). macOS client does not exist yet;
iOS Simulator is not a substitute for device tunnel verification.
