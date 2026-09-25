# Typed Intent Routing Playground

Public distribution page for the macOS ARM64 evaluation client.

This repository contains only public documentation and release assets. The
decision API is deployed separately and must be supplied by the operator.

## Install

1. Download the Apple Silicon DMG from the [latest release](https://github.com/gregoriomomm/typed-routing-playground/releases/latest).
2. Verify the SHA-256 value from `SHA256SUMS`.
3. Open the DMG and move **Typed Intent Routing Playground.app** to Applications.
4. Start the Rust typed API or obtain an authorized HTTPS endpoint.
5. Configure the API URL in the playground and run the health check.

The app is a text-only operator/playground client. It does not contain model
weights, credentials, a provider runtime, a retrieval database or the backend
service. Do not put API keys in a URL or commit them to this repository.

## What the client tests

The playground sends the current utterance, complete redacted history and state
to the typed decision API. The API returns a typed decision, transition and
next state. The playground does not execute customer business tools.

For bulk regression, use the Rust evaluator in the private runtime workspace;
the public download is for manual testing and operator review.
