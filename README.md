# gh-actions-common

## Overview
Collection of common reusable GitHub Action workflows:

| Workflow | Purpose |
|--|--|
| `.github/workflows/dotnet-build` | Builds dotnet code and uploads build artifacts. |
| `.github/workflows/dotnet-test` | Runs dotnet tests. |
| `.github/workflows/dotnet-code-ql` | Runs automated dotnet code quality checks. |
| `.github/workflows/dotnet-test` | Runs automated dotnet code quality checks. |

## Usage Notes
### dotnet-build
```yaml
uses: sbartholomeusz/gh-actions-common/.github/workflows/dotnet-build.yml@v1
with:
  # Required dotnet version
  dotnet_version: '7.0.x'
  # Path to project 
  project_path: 'src/my-project.csproj'
  # Operating system platform - defaults to 'ubuntu-latest'
  # See https://docs.github.com/en/actions/using-jobs/choosing-the-runner-for-a-job#choosing-github-hosted-runners.
  os_platform: 'ubuntu-latest'
  # Name of the uploaded build artifact
  app_artifact_name: 'app-package'
```

### dotnet-test
```yaml
uses: sbartholomeusz/gh-actions-common/.github/workflows/dotnet-test.yml@v1
with:
  # Required dotnet version
  dotnet_version: '7.0.x'
  # Path to solution or project
  path: 'src/my-solution.sln'
  # Operating system platform - defaults to 'ubuntu-latest'
  # See https://docs.github.com/en/actions/using-jobs/choosing-the-runner-for-a-job#choosing-github-hosted-runners.
  os_platform: 'ubuntu-latest'
```

### dotnet-code-ql
```yaml
permissions:
  actions: read
  contents: read
  security-events: write
uses: sbartholomeusz/gh-actions-common/.github/workflows/dotnet-code-ql.yml@v1
with:
  # Required dotnet version
  dotnet_version: '7.0.x'
  # Path to the source code
  path: 'src'
  # Operating system platform - defaults to 'ubuntu-latest'
  # See https://docs.github.com/en/actions/using-jobs/choosing-the-runner-for-a-job#choosing-github-hosted-runners.
  os_platform: 'ubuntu-latest'
```

### dotnet-release
```yaml
permissions:
  contents: write
uses: sbartholomeusz/gh-actions-common/.github/workflows/dotnet-release.yml@v1
```