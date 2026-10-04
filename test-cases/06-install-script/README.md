# Test Case 06: Install Script

## What is being tested?
Detection of suspicious install scripts.

## Why does this case exist?
To verify that SupplyGuard analyzes package metadata (including lifecycle scripts like `postinstall`) for suspicious patterns like `curl`, `wget`, `bash`, or `eval`.

## What should SupplyGuard detect?
SupplyGuard should flag the `postinstall` script in the root (or in a dependency if we had a fixture) as containing suspicious network/shell execution patterns.

## Expected result
High confidence warning for suspicious `install-script`.

