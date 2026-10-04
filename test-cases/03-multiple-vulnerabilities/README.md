# Test Case 03: Multiple Vulnerabilities

## What is being tested?
Detection and aggregation of multiple vulnerabilities of varying severities.

## Why does this case exist?
To test vulnerability enumeration, severity classification (Critical, High, Medium, Low), risk scoring, and remediation ranking.

## What should SupplyGuard detect?
SupplyGuard should report all vulnerabilities across the dependencies and correctly calculate an aggregate risk score.

## Expected result
A mixture of Critical, High, Medium, and Low vulnerabilities corresponding to the included packages.

