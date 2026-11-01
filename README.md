# Azure Fullstack Infrastructure (Terraform)

This repository contains Terraform code to provision a fullstack website infrastructure on Microsoft Azure with frontend and backend services.

## Architecture Overview
- **Resource Group:** Azure Resource Group (`rg-antigravity-demo`)
- **App Service Plan:** Linux Service Plan (Free Tier `F1`)
- **Backend Service:** Azure Linux Web App running Node.js 20 LTS with CORS pre-configured.
- **Frontend Service:** Azure Linux Web App running Node.js 20 LTS with Backend API endpoints mapped.
- **Random String Generator:** Generates unique naming suffixes for Azure DNS hostnames.

## Project Structure
```text
├── main.tf          # Core infrastructure resources (RG, App Service Plan, Web Apps)
├── variables.tf     # Configurable input variables (SKU, region, node version)
├── outputs.tf       # Exported resource IDs and application endpoints
├── .gitignore       # Git ignore rules for Terraform states and temporary files
└── README.md        # Project documentation
```

## How to Deploy

### Prerequisites
1. [Terraform CLI](https://developer.hashicorp.com/terraform/install) (>= 1.0)
2. [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)

### Steps
1. Authenticate to Azure:
   ```bash
   az login
   ```

2. Initialize Terraform working directory:
   ```bash
   terraform init
   ```

3. Generate and review execution plan:
   ```bash
   terraform plan
   ```

4. Apply changes to deploy the infrastructure:
   ```bash
   terraform apply
   ```
