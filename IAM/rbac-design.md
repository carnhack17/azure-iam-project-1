# RBAC Design

## Role Assignments

| Group | Role | Scope |
|-------|------|-------|
| Admins | Owner | Resource Group (rg-bluepay-dev) |
| Employees | Reader | Resource Group (rg-bluepay-dev) |
| Vendors | No Access | N/A |

## Justification
- Admins require full control to manage resources.
- Employees only need read access.
- Vendors are restricted by default.

## Least Privilege
- Roles assigned at the lowest scope possible.
- Users only have permissions required for their job.
