# Test Case 04: Dev Dependency

## What is being tested?
Differentiation between runtime (`dependencies`) and development (`devDependencies`) dependencies.

## Why does this case exist?
To ensure SupplyGuard correctly applies risk reduction for development-only dependencies and flags them appropriately (`dev = true`).

## What should SupplyGuard detect?
The vulnerability in `lodash` should be detected but clearly marked as a dev dependency with a corresponding adjustment in attack path risk.

## Expected result
`lodash` is vulnerable, but `dev = true`.

