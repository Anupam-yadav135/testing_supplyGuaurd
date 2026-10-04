# Test Case 05: Typosquat / Suspicious Package

## What is being tested?
Detection of potential typosquatting or suspicious package names.

## Why does this case exist?
To verify SupplyGuard's heuristic engine for identifying packages that mimic popular libraries (e.g., `lodas` vs `lodash`).

## What should SupplyGuard detect?
It should flag `lodas` as a suspicious package due to name similarity/edit distance. 

## Expected result
SupplyGuard outputs a warning about suspicious package characteristics without definitively claiming it is malware.

