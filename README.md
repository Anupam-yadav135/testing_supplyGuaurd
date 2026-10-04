# SupplyGuard Testing & Benchmark Repository

This repository is a **dedicated testing and benchmark corpus for SupplyGuard**. 
It is intentionally designed to contain controlled dependency scenarios, including known vulnerabilities, transitive risks, license issues, and suspicious packages.

> **⚠️ WARNING**: This is a benchmark and validation corpus. It contains intentionally vulnerable dependencies and suspicious package configurations for testing purposes. **Do not use this repository as a production application.** Do not execute unknown scripts or run install commands outside of an isolated test environment unless explicitly instructed to do so for benchmarking.

## 1. What this repository is
This repository provides a standardized set of test cases to evaluate the reliability, accuracy, and performance of SupplyGuard. It isolates specific supply chain risks into reproducible fixtures.

## 2. Why it exists
To provide objective evidence of SupplyGuard's capabilities, including true positive, false positive, false negative, and true negative rates. It also serves as a baseline for comparing SupplyGuard with other established supply chain security tools like npm audit, OSV-Scanner, and Snyk.

## 3. What is being tested
- Known vulnerabilities (CVE/GHSA detection)
- Transitive dependencies and attack path reconstruction
- Development vs. Runtime dependency risk differentiation
- Suspicious package heuristics (typosquatting, unmaintained packages, suspicious install scripts)
- License risk and conflict detection
- Remediation proposal accuracy
- Performance and scalability on large dependency graphs

## 4. Test-case structure
Each test case is located in its own isolated directory under `test-cases/`. Each directory contains a `README.md` explaining the purpose, expected outcome, and setup, along with the relevant dependency manifests (e.g., `package.json`, `package-lock.json`).

## 5. How to reproduce tests
1. Clone this repository: `git clone <repo_url> && cd testing_supplyGuaurd`
2. Do not blindly run `npm install` across all directories. Follow instructions in individual test cases if lockfile generation is needed. Most test cases already contain pre-generated lockfiles for consistency.
3. Run SupplyGuard against a specific test case:
   ```bash
   supplyguard scan ./test-cases/01-known-vulnerability
   ```

## 6. How expected results are determined
Expected results are documented in the `expected/` directory and within each test case's README. They are derived from known public advisories (OSV, NVD) and manually verified dependency graphs.

## 7. How comparison is performed
Tools are run against the exact same lockfiles in the `test-cases/` directories. Results are collected in `benchmark/results/` and compared based on their ability to detect the documented conditions.

## 8. Precision/recall methodology
We calculate:
- **True Positive (TP)**: SupplyGuard correctly identifies a documented condition.
- **False Positive (FP)**: SupplyGuard reports a condition that does not exist (measured against the clean baseline).
- **False Negative (FN)**: SupplyGuard misses a documented condition.
- **True Negative (TN)**: SupplyGuard correctly reports no issues on clean projects.

`Precision = TP / (TP + FP)`
`Recall = TP / (TP + FN)`
`F1 = 2 * (Precision * Recall) / (Precision + Recall)`

## 9. Attack-path validation
For transitive vulnerabilities, we verify if SupplyGuard correctly reconstructs the exact dependency chain from the root application to the vulnerable package.

## 10. Remediation validation
We verify if the suggested fixed versions are actually free of the vulnerability according to OSV data, and whether the proposed upgrade path breaks direct dependencies.

## 11. Performance testing
The `11-large-project` test case is used to measure analysis time, API request efficiency, and graph processing speed.

## 12. Limitations
- These results represent performance on this specific benchmark corpus and may not perfectly translate to all real-world production environments.
- Python testing is currently limited to `requirements.txt` with exact pins.

## 13. Safety considerations
- We do not use real, active malware. Suspicious packages are simulated using safe fixtures or metadata heuristics.
- No actual malicious code is intended to be executed during these tests.
