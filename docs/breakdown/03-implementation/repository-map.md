---
id: INFO-019
type: info
title: Repository Map
summary: Navigational trees for the test suite and the documentation set.
date: 2026-06-10
status: current
---

# Repository Map

Navigational trees for tests and docs. The annotated package map lives in
INFO-011, the public surface in INFO-012, and the test strategy in TEST-001.

## Test Structure

```
tests/
├── conftest.py                    # Shared fixtures and level markers
├── fixtures/                      # Committed SSP/FMU fixtures
├── support/                       # Fixture guard and fixture builders
├── ssp1/
│   ├── archive/                   # Deterministic archive tests
│   ├── codec/                     # XML round-trip tests
│   ├── facade/                    # Public API tests
│   ├── operations/                # Flatten and FMU-iteration tests
│   ├── orchestration/             # Archive-aware workflow tests
│   └── validation/                # SSD and SRMD validation tests
├── ssp2/
│   └── facade/                    # SSP2 SSV tests
├── common/                       # Common layer tests (reference discovery, etc.)
├── fmi2/
│   ├── archive/                   # FMU workflow tests
│   ├── codec/                     # ModelDescription codec tests
│   ├── facade/                    # ModelDescription facade tests
│   └── operations/                # Unit-converter tests
├── fmi3/
│   └── facade/                    # FMI3 model-description tests
├── ls_ref/
│   ├── codec/                     # LS-REF codec tests
│   └── facade/                    # LS-REF facade tests
├── operations/                    # Connection-graph tests
├── tools/                         # Schema target, validation, routing tests
└── test_*.py                      # Level-marker, layout, and fixture-policy checks
```

### Documentation Structure

```
docs/
├── index.md                    # Documentation router
├── getting_started.md          # Installation + first workflow
├── command_reference.md        # Dev commands (no CLI exists)
├── user/
│   └── python_api.md           # Python API examples
└── dev/
    ├── repo_map.md             # Codebase orientation
    ├── code_disposition.md     # Layer-to-file map
    ├── architecture.md         # Internal layer boundaries
    ├── repo_status.md          # Implementation reality
    ├── guidelines.md           # Code/doc conventions
    └── requirements.md         # Behavioral requirements
```

