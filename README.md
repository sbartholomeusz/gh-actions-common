# gh-actions-common

![Banner](/docs/git-repo-banner.png?raw=true "")

## Overview
Collection of common reusable GitHub Action workflows:

| Workflow | Purpose |
|--|--|
| `.github/workflows/dotnet-build` | Builds dotnet code and uploads build artifacts. |
| `.github/workflows/dotnet-test` | Runs dotnet tests. |
| `.github/workflows/dotnet-code-ql` | Runs automated dotnet code quality checks. |
| `.github/workflows/dotnet-release.yml` | Create GitHub Release. |
| `.github/workflows/npm-build.yml` | Builds npm code. |
| `.github/workflows/npm-test.yml` | Runs npm tests. |
| `.github/workflows/javascript-code-ql.yml` | Runs automated javascript code quality checks. |
| `.github/workflows/typescript-code-ql.yml` | Runs automated typescript code quality checks. |

## Usage Notes
### dotnet-build
```yaml
uses: sbartholomeusz/gh-actions-common/.github/workflows/dotnet-build.yml@v1
with:
  # Required dotnet version
  dotnet_version: '7.0.x'
  # Path to project 
  project_path: './src/my-project.csproj'
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
  path: './src/my-solution.sln'
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
  path: './src'
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

### npm-build
```yaml
uses: sbartholomeusz/gh-actions-common/.github/workflows/npm-build.yml@v1
with:
  # Required node version
  node_version: '16'
  # Path to source code
  path: './src'
  # Operating system platform - defaults to 'ubuntu-latest'
  # See https://docs.github.com/en/actions/using-jobs/choosing-the-runner-for-a-job#choosing-github-hosted-runners.
  os_platform: 'ubuntu-latest'
```

### npm-test
```yaml
uses: sbartholomeusz/gh-actions-common/.github/workflows/npm-test.yml@v1
with:
  # Required node version
  node_version: '16'
  # Path to source code
  path: './src'
  # Operating system platform - defaults to 'ubuntu-latest'
  # See https://docs.github.com/en/actions/using-jobs/choosing-the-runner-for-a-job#choosing-github-hosted-runners.
  os_platform: 'ubuntu-latest'
```

### javascript-code-ql
```yaml
uses: sbartholomeusz/gh-actions-common/.github/workflows/javascript-code-ql.yml@v1
with:
  # Path to source code
  path: './src'
  # Operating system platform - defaults to 'ubuntu-latest'
  # See https://docs.github.com/en/actions/using-jobs/choosing-the-runner-for-a-job#choosing-github-hosted-runners.
  os_platform: 'ubuntu-latest'
```

### typescript-code-ql
```yaml
uses: sbartholomeusz/gh-actions-common/.github/workflows/typescript-code-ql.yml@v1
with:
  # Path to source code
  path: './src'
  # Operating system platform - defaults to 'ubuntu-latest'
  # See https://docs.github.com/en/actions/using-jobs/choosing-the-runner-for-a-job#choosing-github-hosted-runners.
  os_platform: 'ubuntu-latest'
```