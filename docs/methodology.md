# Benchmark Methodology

## Overview
This document outlines the methodology used to evaluate SupplyGuard against standard test cases and other supply chain security tools.

## Metrics Calculated
- **True Positive (TP)**: SupplyGuard accurately identifies a known vulnerability or correctly flags a suspicious package based on established heuristics.
- **False Positive (FP)**: SupplyGuard flags a package that has no vulnerabilities or is not considered suspicious/problematic.
- **False Negative (FN)**: SupplyGuard fails to report a documented vulnerability or suspicious package that exists in the test case.
- **True Negative (TN)**: SupplyGuard correctly reports no issues in a completely clean test case.

## Formulas
- **Precision** = TP / (TP + FP)
- **Recall** = TP / (TP + FN)
- **F1 Score** = 2 * (Precision * Recall) / (Precision + Recall)

## Comparison Scope
Comparisons are made against:
- `npm audit`
- OSV-Scanner
- Snyk (where applicable)

We do not penalize a tool for not supporting a feature it was never designed to have. We focus on comparing shared capabilities like known vulnerability detection.

