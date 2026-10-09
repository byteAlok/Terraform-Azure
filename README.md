# 🚀 Terraform with Microsoft Azure

![Terraform](https://img.shields.io/badge/Terraform-IaC-844FBA?logo=terraform&logoColor=white)
![Azure](https://img.shields.io/badge/Microsoft_Azure-Cloud-0078D4?logo=microsoftazure&logoColor=white)
![HCL](https://img.shields.io/badge/Language-HCL-blue)
![Status](https://img.shields.io/badge/Learning-In_Progress-blue)

A hands-on learning repository dedicated to **Terraform and Infrastructure as Code (IaC) on Microsoft Azure**. This repository contains configuration files, essential commands, learning notes, and practical examples for provisioning and managing Azure infrastructure using Terraform.

## 📌 About This Repository

The goal of this repository is to learn how Terraform automates cloud infrastructure on Microsoft Azure using declarative configuration files written in HashiCorp Configuration Language (HCL).

Topics, code examples, and practical exercises will be added progressively as I learn and practice Terraform with Azure.

## 🎯 Learning Objectives

- 🚀 Understand Infrastructure as Code (IaC).
- 🧩 Learn HCL syntax and Terraform configuration.
- ⚙️ Work with providers, resources, and data sources.
- 🔄 Understand the Terraform workflow: Init, Plan, Apply, and Destroy.
- ☁️ Provision and manage Azure resources using Terraform.
- 🔐 Configure Azure authentication and access securely.
- 📦 Understand Terraform state and reusable modules.
- 🛠️ Automate cloud infrastructure through hands-on exercises.

## 🧰 Tech Stack

| Technology | Purpose |
|---|---|
| Terraform | Infrastructure provisioning and automation |
| Microsoft Azure | Cloud infrastructure provider |
| HCL | Terraform configuration language |
| Azure CLI | Azure command-line interaction |
| Git & GitHub | Version control and documentation |
| Visual Studio Code | Code editor |

## 📚 Topics Covered

### 1. Terraform Fundamentals
- Introduction to Terraform and IaC
- Terraform architecture and workflow
- Installation and configuration
- HCL syntax and configuration blocks
- Providers, resources, and data sources
- Input variables and output values
- Local values and expressions
- Resource dependencies

### 2. Essential Terraform Commands

- `terraform -version` — Check the installed version
- `terraform init` — Initialize the working directory
- `terraform fmt` — Format configuration files
- `terraform validate` — Validate configuration syntax
- `terraform plan` — Preview infrastructure changes
- `terraform apply` — Apply configuration changes
- `terraform destroy` — Destroy managed resources
- `terraform state list` — List resources tracked in state

### 3. Terraform with Microsoft Azure

- Configure the Azure Resource Manager provider (`azurerm`)
- Authenticate using Azure CLI or an appropriate identity
- Configure Azure subscriptions and regions
- Create and manage Azure resources
- Understand resource groups
- Work with resource dependencies
- Reference existing Azure resources
- Use variables and outputs for reusable configurations

### 4. Azure Infrastructure Practice

Practical exercises may include:

- 🖥️ Azure Virtual Machines — Compute resources
- 💾 Azure Storage Accounts — Cloud storage
- 🌐 Azure Virtual Networks (VNet) — Network infrastructure
- 🔒 Network Security Groups (NSG) — Network traffic control
- 🔑 Azure Role-Based Access Control (RBAC) — Access management
- ⚖️ Azure Load Balancer — Traffic distribution
- 📊 Azure Monitor — Infrastructure monitoring

*These are planned learning areas. Resources will be added as the exercises are completed.*

### 5. State Management & Reusability

- Terraform state fundamentals
- Local and remote state management
- Azure Storage Account for remote state
- Blob storage configuration for Terraform state
- State locking and concurrent operations
- Input variables and output values
- Reusable Terraform modules
- Environment-specific configurations

## 📂 Repository Structure

```text
Terraform-Azure/
│
├── README.md
├── basics/
│   ├── provider.tf
│   ├── variables.tf
│   └── outputs.tf
│
├── resource-group/
│   └── main.tf
│
├── virtual-machine/
│   ├── main.tf
│   ├── variables.tf
│   └── outputs.tf
│
├── storage-account/
│   └── main.tf
│
├── virtual-network/
│   └── main.tf
│
└── modules/
```

*This is a suggested structure. Directories and files will be created as the repository grows.*

## ⚙️ Getting Started

### Prerequisites

Install the following tools:

- [Terraform CLI](https://developer.hashicorp.com/terraform/install)
- [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)
- [Microsoft Azure Account](https://azure.microsoft.com/)
- [Visual Studio Code](https://code.visualstudio.com/)

### Step 1: Sign in to Azure

Authenticate through the Azure CLI:

```bash
az login
```

Check the active subscription:

```bash
az account show
```

List available subscriptions:

```bash
az account list --output table
```

Select the appropriate subscription:

```bash
az account set --subscription "<SUBSCRIPTION_ID>"
```

### Step 2: Create a Terraform Configuration

Create a file named `main.tf`:

```hcl
terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "~> 4.0"
    }
  }
}

provider "azurerm" {
  features {}
  resource_provider_registrations = "none"
}

resource "azurerm_resource_group" "example" {
  name     = "rg-terraform-learning"
  location = "Central India"
}
```

This configuration declares the Azure provider and an Azure Resource Group. The provider version constraint should be adjusted when required by your project.

### Step 3: Initialize Terraform

```bash
terraform init
```

### Step 4: Format and Validate

```bash
terraform fmt
terraform validate
```

### Step 5: Preview and Apply Changes

```bash
terraform plan
terraform apply
```

Review the proposed changes before confirming. Ensure that the selected Azure subscription is correct.

### Step 6: Clean Up Resources

When you no longer need the resources created by the configuration:

```bash
terraform destroy
```

Review the destruction plan carefully before confirming.

## 🔐 Security Best Practices

- Never commit client secrets, access tokens, passwords, or credentials.
- Prefer managed identities or workload identity federation where appropriate.
- Use Azure RBAC and least-privilege permissions.
- Add sensitive local files and Terraform state files to `.gitignore`.
- Treat state files and saved plan files as potentially sensitive.
- Protect remote state storage with appropriate access controls.
- Review Terraform plans before applying or destroying resources.
- Monitor Azure resource usage and remove unused resources to avoid unnecessary charges.

## 🗓️ Learning Progress

- [x] Create the Terraform-Azure repository
- [ ] Terraform installation and setup
- [ ] HCL fundamentals
- [ ] Essential Terraform commands
- [ ] Azure CLI authentication
- [ ] Azure provider configuration
- [ ] Resource Group provisioning
- [ ] Virtual Machines and Storage Accounts
- [ ] Virtual Networks and NSGs
- [ ] Variables and outputs
- [ ] Remote state management
- [ ] Reusable Terraform modules
- [ ] Advanced Terraform practices

*Progress will be updated as each topic is completed.*

## 🌐 Related Repositories

- ☁️ **Terraform-AWS** — Terraform with Amazon Web Services
- 🔷 **Terraform-Azure** — Terraform with Microsoft Azure
- 🌎 **Terraform-GCP** — Terraform with Google Cloud Platform

Each repository focuses on its respective cloud provider, including provider-specific configurations, infrastructure examples, and learning notes.

## 👨‍💻 Author

**Alok Maurya**  
Full Stack Engineer | Cloud & DevOps Learner

- GitHub: [@byteAlok](https://github.com/byteAlok)

---

⭐ If you find this repository useful, consider giving it a star.

**Learning by building. Automating Azure infrastructure with Terraform.**
