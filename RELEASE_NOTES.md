# Typed Intent Routing Playground 1.0.7

## Included

- macOS Apple Silicon desktop playground;
- manual typed decision inspection;
- multi-turn history and state replay;
- E2E functional test surface;
- API URL configuration for local or authorized remote backends;
- integrated voice test surface with focused test-user mode;
- voice pipeline visibility for Deepgram Flux → Typed API → Cartesia Sonic 3.6;
- provider-neutral speech markup preview and transcript comparison helpers;
- SHA-256 checksums.

## Typed-only entry point

The browser and Tauri transports now use the Rust typed playground shell for
single-turn decisions, complete multi-turn replay, API smoke, IR evaluation
and Agent Chat. Retired Python/lab routes are not shipped in the built client.

## Voice UX

The voice surface is an operator/tester client for an already-running voice
gateway. The focused path hides provider controls and uses the recommended
Deepgram Flux + Cartesia combination. The advanced preview reuses a small
SSML vocabulary for local text inspection only; it does not send SSML or
credentials to the gateway.

## Distribution

The public release includes the Apple Silicon DMG, portable application ZIP,
and matching checksums. Previous releases remain available as archived
versions.

## Boundary

This release contains the desktop client only. It does not include the
decision API, semantic provider, model weights, retrieval data or credentials.

## Verification

The artifacts were built on macOS Apple Silicon. Verify the downloaded file
against `SHA256SUMS` before opening it. The app, frontend, voice UX tests and
Tauri bridge check passed before packaging.
