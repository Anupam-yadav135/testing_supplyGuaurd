# Test Case 07: Unmaintained Package

## What is being tested?
Detection of unmaintained or deprecated packages.

## Why does this case exist?
To verify SupplyGuard's ability to identify packages that have not been updated in years (e.g., `>5 years old`).

## What should SupplyGuard detect?
SupplyGuard should identify the package as old/unmaintained, applying appropriate weighting without falsely classifying it as malicious.

## Expected result
Package age warning, `old ≠ malicious`.

