# Crowsi Boundary Monitor

Provider-neutral network isolation evaluation for Coela and Ecosystem Control.
It accepts bounded metadata from Linux, Incus, WSL, container, or cloud
adapters and emits `crowsi://network/boundary-snapshot/v1`.

The monitor does not open sockets, inspect packet content, read credentials, or
change firewall and routing state. `sample` and `evaluate` are local-only.

```bash
cargo run -- sample
cargo run -- evaluate examples/boundary-input.sample.json
cargo run -- coverage-sample
cargo run -- coverage-unconfigured
cargo run -- evaluate-coverage examples/control-coverage.sample.json
cargo test
```

An environment is healthy only when its observed isolation mode matches the
declared expectation and its management endpoint is not exposed. Unknown
provider state remains unknown instead of being treated as healthy.

Incus-specific inventory collection belongs to `incus-isolation-adapter`.
Crowsi owns the common boundary vocabulary, cross-environment evaluation, and
security dashboard contract.

The v2 control-coverage view proves whether every declared asset has current
observation, management authority, a ready enforcer, an out-of-band lifeline,
all quarantine/revocation/verification/recovery actions, and a current drill.
Unknown, stale, unmanaged, and partial assets never become `controlled`.

`coverage-sample` and `evaluate-coverage` are deterministic contract and
simulation tools. Their unsigned input is not production evidence and is not
accepted by the standard Coela refresh path as proof of `controlled` state.
Production promotion requires a separate role-scoped signature verifier for
the authority, sensor, enforcer, lifeline, and drill attestations.
