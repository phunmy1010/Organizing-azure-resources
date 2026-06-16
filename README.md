# Azure Resource Management Lab

## Overview

This project demonstrates the implementation of Azure Resource Management best practices, including resource organization, naming conventions, tagging, Role-Based Access Control (RBAC), and resource lifecycle management.

The environment was created within a single Azure Subscription and organized using Resource Groups to represent different environments.

---

# Naming Convention

A consistent naming convention was used to improve resource identification, management, and scalability.

## Resource Groups

Format:

`phun-3mtt-[environment]-eastus`

Examples:

* `phun-3mtt-dev-eastus`
* `phun-3mtt-prod-eastus`
* `phun-3mtt-temp-eastus`

### Naming Components

| Component   | Description                        |
| ----------- | ---------------------------------- |
| phun        | Project/Application Identifier     |
| 3mtt        | Program/Lab Identifier             |
| environment | Environment Type (dev, prod, temp) |
| eastus      | Azure Region                       |

---

# Resource Organization Strategy

Resources were grouped according to their intended environment.

## Development Environment

**Resource Group:** `phun-3mtt-dev-eastus`

Purpose:

* Testing
* Development activities
* Validation of configurations

Resources:

* Azure Storage Account

---

## Production Environment

**Resource Group:** `phun-3mtt-prod-eastus`

Purpose:

* Simulated production workloads
* Secure resource management

Resources:

* Azure Storage Account

---

## Temporary Environment

**Resource Group:** `phun-3mtt-temp-eastus`

Purpose:

* Temporary testing environment
* Demonstration of lifecycle management

Resources:

* Azure Storage Account

Note: This Resource Group was later deleted to demonstrate resource lifecycle management and cleanup.

---

# Resources Deployed

The following Azure resources were deployed:

| Resource Type   | Environment |
| --------------- | ----------- |
| Storage Account | Development |
| Storage Account | Production  |
| Storage Account | Temporary   |

Storage Accounts were configured using:

* Standard Performance Tier
* Locally Redundant Storage (LRS)
* East US Region
* Azure Blob Storage

This configuration was selected to minimize cost while meeting the requirements of the lab.

---

# Tagging Strategy

Tags were implemented to support governance, cost allocation, reporting, and automation.

## Resource Group Tags

### Development

| Tag         | Value       |
| ----------- | ----------- |
| environment | development |
| owner       | TeamA       |
| project     | Phun        |
| costcenter  | Dev         |

### Production

| Tag         | Value      |
| ----------- | ---------- |
| environment | production |
| owner       | TeamB      |
| project     | Phun       |
| costcenter  | Prod       |

### Temporary

| Tag         | Value     |
| ----------- | --------- |
| environment | temporary |
| owner       | TeamA     |
| project     | Phun      |
| costcenter  | Test      |

## Storage Account Tags

| Tag         | Value   |
| ----------- | ------- |
| application | storage |
| project     | Phun    |

---

# Role-Based Access Control (RBAC)

RBAC was implemented at the Resource Group level to simulate a multi-team environment and enforce the principle of least privilege.

## Assigned Roles

| Resource Group        | Role Assigned |
| --------------------- | ------------- |
| phun-3mtt-dev-eastus  | Reader        |
| phun-3mtt-prod-eastus | Contributor   |
| phun-3mtt-temp-eastus | Reader        |

## Rationale

### Reader Role

The Reader role allows users to view resources and configurations without making changes. This is suitable for monitoring and auditing purposes.

### Contributor Role

The Contributor role allows users to create, modify, and manage resources while preventing them from granting permissions to others. This role is appropriate for production resource management.

---

# Resource Lifecycle Management

Lifecycle management was tested through the deletion of the temporary environment.

## Action Performed

Deleted Resource Group:

`phun-3mtt-temp-eastus`

## Purpose

This demonstrated:

* Bulk deletion of resources
* Environment cleanup procedures
* Cost optimization practices
* Resource lifecycle management

After deletion, only the Development and Production environments remained active.

---

# Screenshots

The repository includes screenshots showing:

1. Created Resource Groups
2. Deployed Storage Accounts
3. Applied Tags
4. RBAC Role Assignments
5. Resource Groups before deletion
6. Resource Groups after deletion

---

# Conclusion

This lab successfully demonstrated Azure Resource Management concepts, including resource organization, deployment, tagging, RBAC implementation, and lifecycle management. The use of consistent naming conventions and governance practices provides a scalable foundation for managing cloud resources in Azure.
