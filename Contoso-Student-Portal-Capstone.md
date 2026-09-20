# Contoso Student Portal – Azure Foundation
### Capstone Project by Griffin Okondo

## Project Overview

This project is a hands-on Capstone designed to build a secure and well-governed Azure foundation for a fictional institution (Contoso University). The goal was to create a production-ready starting environment for a Student Portal that stores sensitive student documents.

## Business Requirements

- Organize all resources in a dedicated Resource Group
- Store student documents securely with protection against accidental deletion
- Implement network isolation
- Store secrets securely (not in code)
- Follow the principle of Least Privilege
- Enable basic monitoring and backup readiness
- Apply cost control measures (Tags + Budget)
- Make the solution repeatable using Infrastructure as Code (Bicep)

## Solution Architecture

| Component                  | Resource Name              | Purpose |
|---------------------------|----------------------------|-------|
| Resource Group            | rg-contoso-portal          | Logical container for all resources |
| Storage Account           | stgcontoso7854             | Secure storage for student documents |
| Blob Container            | student-documents          | Private container for files |
| Soft Delete               | Enabled (14 days)          | Protection against accidental deletion |
| Key Vault                 | kv-contoso-556             | Secure storage of secrets |
| Virtual Network           | vnet-contoso-portal        | Network isolation |
| Subnet                    | subnet-portal              | Dedicated subnet |
| Network Security Group    | nsg-contoso-portal         | Traffic control (Allow HTTPS) |
| Log Analytics Workspace   | law-contoso-portal         | Monitoring and logging |
| Recovery Services Vault   | rsv-contoso-portal         | Backup readiness |
| Tags                      | Applied                    | Cost tracking and organization |
| Budget                    | Created                    | Cost control and alerts |
| Bicep Template            | main.bicep                 | Infrastructure as Code |

## Key Skills Demonstrated

- Azure Resource Organization
- Secure Storage design (Soft Delete + Private Container)
- Secret Management with Azure Key Vault
- Network Security (VNet, Subnet, NSG)
- Identity & Access Management (RBAC)
- Monitoring readiness
- Backup readiness
- Cost Management (Tags + Budgets)
- Infrastructure as Code using Bicep
- Well-Architected Framework principles

## How to Redeploy (Bicep)

```bash
az group create --name rg-contoso-portal --location eastus

az deployment group create \
  --resource-group rg-contoso-portal \
  --template-file main.bicep \
  --name contoso-portal-deployment
