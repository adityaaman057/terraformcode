# 🚀 Terraform Commands

A quick reference for the most commonly used **Terraform commands** when initializing, planning, deploying, and destroying infrastructure.

---

## 🛠️ 1. `terraform init`

Initializes the Terraform working directory.

It performs tasks such as:

* ⚙️ Configuring the Terraform backend
* 📦 Downloading required providers
* 🧩 Downloading Terraform modules
* 📁 Creating the necessary Terraform working files

```bash
terraform init
```

---

## 🔍 2. `terraform plan`

Generates an execution plan and shows what Terraform intends to change **before actually making any changes**.

```bash
terraform plan
```

This is useful for reviewing:

* ➕ Resources that will be created
* 🔄 Resources that will be modified
* ➖ Resources that will be destroyed

---

## 🚀 3. `terraform apply`

Applies the Terraform configuration and provisions or updates the infrastructure.

```bash
terraform apply
```

Terraform will normally ask for confirmation before making the changes.

To automatically approve the changes:

```bash
terraform apply -auto-approve
```

> ⚠️ Use `-auto-approve` carefully, especially in production environments.

---

## 🗑️ 4. `terraform destroy`

Removes the infrastructure resources managed by the current Terraform configuration.

```bash
terraform destroy
```

To skip the confirmation prompt:

```bash
terraform destroy -auto-approve
```

> ⚠️ **Warning:** `terraform destroy` can permanently delete infrastructure and data. Always review the planned changes before confirming.

---

## 🔄 Typical Terraform Workflow

```text
        ┌─────────────────┐
        │  Write Terraform │
        │  Configuration   │
        └────────┬────────┘
                 │
                 ▼
        ┌─────────────────┐
        │ terraform init  │
        └────────┬────────┘
                 │
                 ▼
        ┌─────────────────┐
        │ terraform plan  │
        └────────┬────────┘
                 │
                 ▼
        ┌─────────────────┐
        │ terraform apply │
        └────────┬────────┘
                 │
                 ▼
        ┌─────────────────┐
        │ Infrastructure   │
        │    Deployed      │
        └─────────────────┘
                 │
                 │ When no longer needed
                 ▼
        ┌─────────────────┐
        │terraform destroy│
        └─────────────────┘
```
