# Bannerlator — D2Android integration

This repository is the working fork for integrating the D2Android touch-control experience into Bannerlator.

## Current target

- Host application: Bannerlator (this repository).
- Initial game target: Diablo II 1.13c, subject to binary compatibility verification.
- Game executables and DLLs: supplied by the repository owner later; never committed by automation unless explicitly requested.
- Build environment: GitHub Actions hosted Linux runners; no local Android/Termux compilation required.

## Porting plan

1. Inspect Bannerlator's Android app structure, native Wine/Box components, input overlay, and build pipeline.
2. Map D2Android's touch controls and game integration points onto Bannerlator without replacing unrelated Bannerlator functionality.
3. Add a dedicated Diablo II profile and configurable touch layout.
4. When owner-provided EXE/DLL files arrive, inspect PE architecture, imports, exports, version metadata, and runtime assumptions. Do not redistribute proprietary game binaries.
5. Implement compatibility changes and Chinese UI/localization while keeping game assets external.
6. Build debug APKs with GitHub Actions and publish test artifacts for device testing.

## Compatibility gate

D2Android sources currently identified during initial reconnaissance describe Diablo II 1.13d. The requested 1.13c target is not assumed compatible. Confirm the exact executable/DLL versions and runtime behavior before declaring support.

## Repository rules

- Work on `d2android-port`; do not force-push or rewrite `main`.
- Keep changes in small, reviewable commits.
- Never add proprietary game EXE/DLL/data files to public Git history.
- Do not claim a build or runtime test passed until CI/device evidence exists.

## Status

- [x] GitHub connection verified.
- [x] Dedicated development branch created.
- [ ] Source-tree and build-system audit.
- [ ] D2Android control-system port.
- [ ] 1.13c binary compatibility analysis (awaiting owner-provided files).
- [ ] Chinese localization.
- [ ] GitHub Actions APK build and device validation.
