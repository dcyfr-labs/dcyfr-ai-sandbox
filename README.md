# DCYFR AI Sandbox

<!-- README-META
  tlp_clearance: GREEN
  status: active
  name: dcyfr-ai-sandbox
  description: Sandbox and examples for DCYFR AI harness experimentation
  last_validated: 2026-07-11
-->

> **🔒 INTERNAL TESTING INFRASTRUCTURE (Not for Public Use)**  
> This is internal experimentation infrastructure for the DCYFR workspace.  
> **Status:** Never published to npm (marked `"private": true`)  
> **Purpose:** Scratch space for exercising `@dcyfr/ai` — examples and integration test scaffolding  
> **Not suitable for:** Production use, external projects, public consumption

[![CI](https://github.com/dcyfr-labs/dcyfr-ai-sandbox/actions/workflows/ci.yml/badge.svg)](https://github.com/dcyfr-labs/dcyfr-ai-sandbox/actions/workflows/ci.yml)
[![Private](https://img.shields.io/badge/Status-Internal%20Only-red?style=flat-square)](https://github.com/dcyfr-labs/dcyfr-ai-sandbox)

Version: 1.0.1 (internal)

## About DCYFR

`@dcyfr/ai-sandbox` is maintained by **DCYFR Labs** as part of the DCYFR internal experimentation portfolio.

- **DCYFR** is a registered trademark of DCYFR Labs.
- Primary domain: [www.dcyfr.ai](https://www.dcyfr.ai)
- Licensing details: [LICENSE](./LICENSE)

---

## Overview

A minimal sandbox for experimenting with the [`@dcyfr/ai`](https://github.com/dcyfr-labs/dcyfr-ai) framework. It currently contains:

- **Examples** (`examples/`) — three small runnable scripts (one exercises the framework; two are placeholder stubs, see below)
- **Integration test scaffolding** (`tests/`) — a single placeholder suite, ready to grow real framework tests
- **Docs** — [docs/GETTING-STARTED.md](./docs/GETTING-STARTED.md) quick-start guide

This is early-stage scaffolding: most of the intended content (real integration tests, plugin experiments, benchmarks) does not exist yet.

---

## Quick Start

### Installation

```bash
cd dcyfr-ai-sandbox
npm install
```

Requires Node `>=24.13.0` and npm `>=11.6.2` (see `engines` in `package.json`).

### Run Tests

```bash
npm run test:run       # Run all tests once
npm test               # Watch mode
npm run test:coverage  # With coverage
npm run typecheck      # Type checking
npm run lint           # ESLint
```

### Run Examples

```bash
npm run example:basic     # PluginLoader instantiation via @dcyfr/ai
npm run example:plugins   # Placeholder stub (prints outline)
npm run example:agents    # Placeholder stub (prints outline)

npm run examples:compile  # Syntax-check all examples (node --check)
npm run examples:check    # Run all examples
npm run examples:test     # Compile + run
```

---

## Structure

```
dcyfr-ai-sandbox/
├── examples/
│   ├── README.md            # Example index
│   ├── basic-usage.js       # Creates a PluginLoader from @dcyfr/ai
│   ├── plugin-system.js     # Stub — prints a plugin-workflow outline ("Coming soon")
│   └── agent-patterns.js    # Stub — prints an agent-pattern outline ("Coming soon")
├── tests/
│   └── integration/
│       └── framework.test.ts  # Placeholder suite (3 trivial assertions)
├── docs/
│   └── GETTING-STARTED.md
├── .github/workflows/       # CI, CodeQL, Semgrep, SonarCloud, release, dependabot auto-merge
├── .dcyfr.yaml               # DCYFR AI config (validation + agents disabled for this repo)
├── package.json
├── tsconfig.json
├── vitest.config.ts
└── README.md
```

There is no `src/` directory. `vitest.config.ts` declares `@` / `@tests` aliases, but only `tests/` currently exists.

---

## Test Status

Honest accounting: the only test file is `tests/integration/framework.test.ts`, a placeholder suite of three trivial `expect(true).toBe(true)` assertions. No real framework behavior is exercised yet, and no coverage target is claimed.

---

## Examples

Standardized example index: [examples/README.md](./examples/README.md)

| File | Status | What it does |
| --- | --- | --- |
| `basic-usage.js` | Runnable | Imports `PluginLoader` from `@dcyfr/ai`, instantiates it with telemetry enabled, and logs success |
| `plugin-system.js` | Stub | Prints an outline of the intended plugin workflow, then "Coming soon!" |
| `agent-patterns.js` | Stub | Prints an outline of the intended agent lifecycle demo, then "Coming soon!" |

All three are plain JavaScript (`node examples/<file>.js`); none accept arguments.

---

## Dependencies

- **[@dcyfr/ai](https://github.com/dcyfr-labs/dcyfr-ai)** `^3.0.3` — core AI framework (the only runtime dependency)
- **vitest** — test runner (dev)
- **typescript** / **eslint** — type checking and linting (dev)
- **@changesets/cli** — version tracking (dev)

---

## CI

Workflows in `.github/workflows/`:

| Workflow | Purpose |
| --- | --- |
| `ci.yml` | Lint, typecheck, and test (with coverage) on Node 24.13.0. Jobs currently run `continue-on-error` while the repo migration settles. |
| `codeql.yml` | CodeQL static analysis |
| `semgrep.yml` | Semgrep scanning |
| `sonarcloud.yml` | SonarCloud analysis |
| `release.yml` | Changesets-driven release automation (tags only — the package is private and never published to npm) |
| `dependabot-auto-merge.yml` | Auto-merge for Dependabot PRs |

---

## Development

### Adding Tests

1. Create a `*.test.ts` file under `tests/` (vitest picks up `tests/**/*.test.ts` and `tests/**/*.spec.ts`)
2. Run `npm run test:run` to validate

### Adding Examples

1. Create the example file in `examples/`
2. Add a run script to `package.json` and a row to [examples/README.md](./examples/README.md)
3. Verify with `npm run examples:test`

---

## Versioning

This package uses [Changesets](https://github.com/changesets/changesets) for version tracking:

```bash
npm run changeset
```

Versions are tracked via git tags. This is a private sandbox package and is not published to npm.

---

## License

MIT — see [LICENSE](./LICENSE).

**Trademark:** "DCYFR" is a trademark of DCYFR Labs.

---

## Related Projects

- [@dcyfr/ai](https://github.com/dcyfr-labs/dcyfr-ai) — Core AI framework
- [@dcyfr/workspace-agents](https://github.com/dcyfr-labs/dcyfr-workspace-agents) — Validation plugins
- [dcyfr-labs](https://github.com/dcyfr-labs/dcyfr-labs) — Main application

---

**Part of the DCYFR Workspace**  
Managed by workspace AI for experimentation and development
