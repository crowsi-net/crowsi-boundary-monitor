# crowsi-boundary-monitor

Assess isolation boundaries from a supplied environment observation.

## What you can do

- Evaluate Linux, container, WSL, Incus or cloud boundary metadata.
- Review coverage and missing boundary evidence.

## Current scope

Collectors supply sanitized observations. The monitor evaluates them without provisioning or changing a boundary.

Package distribution is not activated by this documentation. Use the checked-in source and the declared dependency versions; published availability must be verified separately.

## Getting started

Install Rust 1.97 or newer and make the declared dependencies available. Use the configured private registry when a dependency is not distributed publicly. Run from this repository:

```sh
cargo test --locked
```

## Documentation and source

[Usage guide](docs/getting-started.md)

[Examples](examples) · [Schemas](schemas) · [Implementation and public interfaces](src) · [Verification cases](tests) · [Contributing](CONTRIBUTING.md) · [Security reporting](SECURITY.md) · [License](LICENSE) · [Attribution notices](NOTICE)
