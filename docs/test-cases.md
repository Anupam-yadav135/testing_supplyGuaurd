# Test Cases Overview

The following test cases are included in `test-cases/`:

1. **01-known-vulnerability**: Direct dependency with a CVE.
2. **02-transitive-vulnerability**: Vulnerability deep in the dependency tree.
3. **03-multiple-vulnerabilities**: A mix of critical, high, medium, and low vulnerabilities.
4. **04-dev-dependency**: Vulnerability restricted to `devDependencies`.
5. **05-typosquat**: A package that mimics a popular library name.
6. **06-install-script**: A package that executes suspicious commands on install.
7. **07-unmaintained**: An old, unmaintained package.
8. **08-license-risk**: A mix of open-source licenses to check risk evaluation.
9. **09-clean-project**: A completely normal, updated, clean project.
10. **10-mixed-risk**: A realistic project combining various risk factors.
11. **11-large-project**: A project with hundreds of dependencies to test scalability.

