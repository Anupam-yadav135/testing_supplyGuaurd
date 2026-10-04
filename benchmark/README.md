# Reproducing Benchmarks

## Setup
```bash
git clone <repo>
cd testing_supplyGuaurd
```

Ensure you have npm, OSV-Scanner, and SupplyGuard installed.

## Running Tests
Run SupplyGuard:
```bash
supplyguard scan ./test-cases/01-known-vulnerability
```

Run npm audit:
```bash
cd test-cases/01-known-vulnerability
npm audit
```

Run OSV-Scanner:
```bash
osv-scanner --lockfile test-cases/01-known-vulnerability/package-lock.json
```

Results should be recorded in `benchmark/results/` for validation.

