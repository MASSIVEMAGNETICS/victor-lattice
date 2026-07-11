# Victor Living Lattice v2.0

**A production reference architecture for sovereign, graph-native, self-evolving AI.**

Victor Living Lattice is not another chatbot wrapper. It is a local-first cognitive runtime where models are replaceable workers and the durable intelligence lives in a signed event history, temporal relationship graph, capability contracts, policy gates, and verified evolution pipeline.

The architecture preserves the original Victor Lattice invariants:

1. **Identity** - what must persist.
2. **Relationship** - what connects facts, agents, goals, and evidence.
3. **Transformation** - what may change, under which contract.
4. **Verification** - how every consequential claim or mutation is checked.

## What works now

The v0.1 reference runtime requires no cloud service and no language model. It provides:

- Ed25519 sovereign identity and signatures
- append-only, hash-chained SQLite event ledger
- deterministic chain verification and replay primitives
- temporal property graph for memories and relationships
- capability registry with typed metadata and risk levels
- immune policy gate with explicit approval requirements
- bounded evolution gate for candidate changes
- CLI commands for initialization, memory, search, status, and verification
- offline tests, Windows one-click setup, and GitHub Actions CI

## Install

### Windows one-click

Double-click:

```text
scripts\run_windows.bat
```

The launcher creates a virtual environment, installs the package, runs the test suite, initializes a local lattice under `.victor`, and opens the demonstration CLI.

### Cross-platform

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate
# Linux/macOS: source .venv/bin/activate
python -m pip install -e ".[dev]"
victor-lattice --home .victor init
victor-lattice --home .victor remember "The graph is the durable mind; models are replaceable workers."
victor-lattice --home .victor search "durable mind"
victor-lattice --home .victor verify
```

## Architecture

```text
Human Steward / Applications
            |
      Trust + Policy Gate
            |
  Cognitive Runtime / Planner
     |         |          |
Capabilities  Model Mesh  Evolution Lab
     |         |          |
     +---- Signed Event Bus ----+
                  |
     Temporal Connectome + Ledger
                  |
         Heartwood Invariants
```

The reference implementation deliberately proves the non-negotiable substrate before adding an LLM. Model adapters, multimodal perception, federation, and autonomous research workers are roadmap layers, not hidden dependencies.

## Documents

- [Production white paper](docs/WHITEPAPER.md)
- [Architecture specification](docs/ARCHITECTURE.md)
- [Implementation roadmap](docs/ROADMAP.md)
- [Threat model](docs/THREAT_MODEL.md)

## Development

```bash
python -m pip install -e ".[dev]"
pytest -q
ruff check .
mypy src
```

## Status

- **v0.1**: executable sovereign substrate
- **v0.2**: model adapters, planner, richer retrieval, dashboard
- **v0.3**: sandboxed skill synthesis and evaluation
- **v1.0**: hardened local personal intelligence runtime

## License

Apache-2.0. See [LICENSE](LICENSE).
