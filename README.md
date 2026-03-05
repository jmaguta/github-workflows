# github-workflows

Centralised GitHub Actions reusable workflows for jmaguta Terraform IaC repos.

## Usage

### PR Checks (fmt, validate, checkov)

```yaml
jobs:
  checks:
    uses: jmaguta/github-workflows/.github/workflows/terraform-pr-checks.yaml@main
    with:
      checkov_soft_fail: true   # set false to enforce
```

### Semantic Release

```yaml
jobs:
  release:
    uses: jmaguta/github-workflows/.github/workflows/terraform-release.yaml@main
    secrets: inherit
```

## Inputs

| Workflow | Input | Default | Description |
|---|---|---|---|
| terraform-pr-checks | `terraform_version` | `~> 1.14` | Version constraint |
| terraform-pr-checks | `working_directory` | `.` | Root of Terraform files |
| terraform-pr-checks | `checkov_soft_fail` | `true` | Report-only vs enforce |
