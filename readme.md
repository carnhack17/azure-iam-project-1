# azure-iam-project-1
First training project

# Azure IAM Project 1 – Fundamentals

## Objective
Implement basic Identity and Access Management (IAM) using Azure Entra ID and Azure RBAC.

## Scope
Azure subscription – development environment.

## Resources Used
- Resource Group: rg-bluepay-dev
- (Optional) Storage Account or Azure Virtual Desktop resources

## Identity
- Entra ID Group: grp-iam-users-lab-01
- User assigned to the group

## Access Control
- Role Assigned: Reader (or Desktop Virtualization User if Azure Virtual Desktop was used)
- Scope: Resource Group (rg-bluepay-dev)

## Least Privilege Validation
- Role assigned at Resource Group scope only
- Group-based RBAC instead of direct user assignment
- Testing denied actions: create, delete, modify resources
- Verified no permissions at subscription level

## Result
Only users belonging to the Entra ID group can access the resources in the development resource group according to the assigned role.

## Key Concepts Learned
- Azure Entra ID vs Azure RBAC
- Role assignment at resource group scope
- Least privilege principle
- Group-based access management

## IAM Architecture Diagram (ASCII)

           ┌───────────────────┐
           │ rg-bluepay-dev    │
           │  Resource Group   │
           └───────────────────┘
                    ▲
                    │ RBAC
        ┌───────────┼────────────┐
        │           │            │
   ┌─────────┐ ┌─────────────┐ ┌──────────┐
   │ Admins  │ │ Employees   │ │ Vendors  │
   │ Owner   │ │ Reader      │ │ No Access│
   └─────────┘ └─────────────┘ └──────────┘
        ▲           ▲
        │           │
 ┌────────────┐ ┌──────────────┐
 │ alice.admin│ │ bob.employee │
 └────────────┘ └──────────────┘
