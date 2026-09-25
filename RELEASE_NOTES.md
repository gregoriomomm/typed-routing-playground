# Typed Intent Routing Playground 1.0.5

## Included

- macOS Apple Silicon desktop playground;
- manual typed decision inspection;
- multi-turn history and state replay;
- E2E functional test surface;
- API URL configuration for local or authorized remote backends;
- SHA-256 checksums.

## Typed-only entry point

The browser and Tauri transports now use the Rust typed playground shell for
single-turn decisions, complete multi-turn replay, API smoke, IR evaluation
and Agent Chat. Retired Python/lab routes are not shipped in the built client.

## Distribution

The public release includes the Apple Silicon DMG, portable application ZIP,
and matching checksums. Previous releases remain available as archived
versions.

## Boundary

This release contains the desktop client only. It does not include the
decision API, semantic provider, model weights, retrieval data or credentials.

## Verification

The artifacts were built on macOS Apple Silicon. Verify the downloaded file
against `SHA256SUMS` before opening it.
