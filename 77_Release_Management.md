# 77. Release Management

## 1. Versioning Scheme
Releases follow **Semantic Versioning (MAJOR.MINOR.PATCH)**:
* **MAJOR:** Significant architectural changes, core schema overhauls, or breaking API modifications.
* **MINOR:** New functional modules or major enhancements (e.g., adding a new AI forecasting tool).
* **PATCH:** Bug fixes, security patches, and minor UI tweaks.

## 2. Deployment Pipeline
* Code committed to `develop` branch -> Automated testing (pytest) -> Staging environment deployment -> Client sign-off -> Merge to `main` -> Production release via CI/CD.