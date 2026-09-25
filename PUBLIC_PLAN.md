# Public delivery plan

This repository is the neutral distribution surface for the optional desktop
playground. It is intentionally separate from the production decision service.

## Boundaries

```text
operator / evaluator → desktop playground → authorized typed API
production agent     → authorized typed API → TypedDecision + Transition
```

The desktop client is useful for manual history replay, typed-decision
inspection, functional cases, digressions, resumes, multi-intent examples and
guardrail previews. It is not a production dependency and it does not execute
business tools.

The public repository contains only neutral documentation, release notes,
checksums and installer assets. It must never contain source code, model
weights, credentials, private endpoints, customer data or reviewed training
corpora.

## Release gates

Before publishing a new installer:

1. Run the Rust workspace tests, API smoke test and web build in the private
   runtime workspace.
2. Build the macOS Apple Silicon application with the neutral product name and
   bundle identifier.
3. Inspect `Info.plist`, visible labels and bundled public resources.
4. Produce a DMG, application ZIP and `SHA256SUMS` from the same build.
5. Publish an immutable GitHub Release; never replace an existing asset.
6. Verify every link anonymously from a clean browser or `curl`.
7. Update this page and the download links only after the release assets are
   available.

## Verification

```bash
curl -fsSL https://github.com/gregoriomomm/typed-routing-playground/releases/download/v1.0.4/SHA256SUMS
curl -IL https://github.com/gregoriomomm/typed-routing-playground/releases/download/v1.0.4/typed-intent-routing-playground-1.0.4-macos-arm64.dmg
```

The checksum file is the source of truth for the published artifacts. If a
release is defective, keep it immutable, mark it superseded and publish a new
version. The download page can then be moved to the last verified release.

## Limitations

Runtime fixture coverage and semantic provider quality are separate gates. A
passing local fixture replay does not claim perfect accuracy on unseen language
or a new provider checkpoint.
