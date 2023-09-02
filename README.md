# demo-devops-azure-synapse
This repo contains the instructions to set up a CI/CD workflow for Synapse, showcasing a simple scenario for DevOps with Azure Synapse

## Lab
### Pre-requisites
- Azure Subscription
  - Deploy in a resource group 2 workspaces of Synapse Analytics (dev, uat)
- GitHub account/org with admin priviledges
  - Create a repository for the project
 
### 1. Set up the permissions
- Connect your dev Synapse workspace to your GitHub repo: Synapse Studio > Manage > Git Configuration > follow the steps
- Create a service principal (SP):
  - Navigate to Azure Active Directory > App registrations > create a new app registration for your GitHub repo... Or do it via the AZ CLI
  - Get the following information and add them as repository secrets on your GitHub repo
    - Client ID
    - Client Secret
    - Subscription ID
    - Tenant ID
- Navigate to your UAT Synapse workspace on the Azure portal: Access control > Add role assignment --> Grant your SP contributor RBAC permissions
- Navigate to your UAT Synapse studio: Manage > Access control > Add your SP as Synapse Artifact Publisher or Synapse Administrator
