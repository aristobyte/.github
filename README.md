# Organisation Repo `.github`

This repository hosts the shared GitHub configuration for the **AristoByteUI** organization.  
Everything here is designed to be copied into the org-level repository: `aristobyte-ui/.github`.

### ✨ What You Get

| Category           | Included Files                                                       | Purpose                            |
| ------------------ | -------------------------------------------------------------------- | ---------------------------------- |
| Org profile        | `profile/README.md`                                                  | Organization landing page          |
| Community health   | `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, `SUPPORT.md` | Standards and contributor guidance |
| Templates          | `.github/ISSUE_TEMPLATE/*`, `.github/PULL_REQUEST_TEMPLATE.md`       | Consistent intake                  |
| Dependabot         | `.github/dependabot.yml`                                             | Automated dependency updates       |
| Label automation   | `.github/labeler.yml` + workflow                                     | PR labeling                        |
| Release automation | `.github/release-drafter.yml` + workflow                             | Release notes                      |
| Reusable CI        | `.github/workflows/*.yml`                                            | Shared CI pipelines                |
| Funding            | `.github/FUNDING.yml`                                                | Sponsorship links                  |

---

### 🧩 How To Use

Copy everything inside `GITHUB_COMMON_REPO_ROOT` into:

```
https://github.com/aristobyte-ui/.github
```

GitHub will automatically apply:

- Community health files
- Issue & PR templates
- Organization profile README
- Default workflows

### 🔁 Reusable Workflows

Workflows inside `.github/workflows` are reusable via `workflow_call`.

Example usage:

```yaml
name: CI

on:
  pull_request:
  push:
    branches: [master]

jobs:
  ci:
    uses: aristobyte-ui/.github/.github/workflows/ci.yml@master
    with:
      node_version_file: .nvmrc
      run_lint: true
      run_tests: true
      run_build: true
```
