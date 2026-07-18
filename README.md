# Terraform: Migration & Drift Detection

Infrastructure-as-Code project focused on two core Terraform skills: migrating existing infrastructure into Terraform management, and detecting configuration drift between declared state and real-world infrastructure.

## What this project covers

- **Migration to Terraform** — bringing infrastructure that wasn't originally provisioned by Terraform under its management, without recreating resources from scratch.
- **Drift Detection** — identifying when the real state of infrastructure has diverged from what's declared in the Terraform configuration (e.g., a manual change made outside of Terraform), using `terraform plan` and state inspection.

## Repo structure

**Project files:**
- `main.tf` — core resource definitions
- `backend.tf` — Terraform backend configuration
- `statefile_scenarios.md` — notes and worked examples on state file behavior, including drift scenarios
- `provisioners.md` — notes on Terraform provisioners
- `modules.md` — notes on structuring Terraform modules
- `app.py` — supporting script used alongside the Terraform workflow

**Learning notes** (numbered files, `01-` through `09-`):
Reference notes written while learning core Terraform concepts — fundamentals, providers, installation, variables, conditional expressions, and built-in functions. Kept here for personal reference alongside the project files above.

## Getting Started

```bash
git clone https://github.com/Maneeshpuli/Terraforms.git
cd Terraforms

terraform init
terraform plan
```

> **Note:** Variable values are expected in a `terraform.tfvars` file, which is gitignored and not included in this repo. Copy `terraform.tfvars.example` (if provided) and fill in your own values before running.

## Prerequisites

- Terraform >= 1.x
- Cloud provider credentials configured (see `main.tf` / `backend.tf` for the target provider)

## What I learned building this

- How to import existing infrastructure into Terraform state without recreating it
- How `terraform plan` surfaces drift between configuration and real infrastructure
- How state file behavior changes across different real-world scenarios (see `statefile_scenarios.md`)

## Notes

- State files (`*.tfstate`) and variable files (`*.tfvars`) are gitignored — see `.gitignore`.
