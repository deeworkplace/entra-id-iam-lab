# Lab 04: Role-Based Access Control (RBAC)

## Objective

Understand how Role-Based Access Control (RBAC) works in Microsoft Entra ID, compare administrative roles, and identify the importance of privileged access and least privilege.

## Environment

Microsoft Entra admin center using a practice tenant.

## Tasks Performed

1. Navigated to Identity → Roles & admins.
2. Reviewed the Helpdesk Administrator role description and assignment page.
3. Reviewed the User Administrator role description and assignment page.
4. Reviewed the Global Administrator role description and assignment page.
5. Compared the permissions and responsibilities of the three roles.
6. Reviewed the significance of roles marked as privileged.

## Role Comparison

### Helpdesk Administrator

- Can reset passwords for specified non-administrator users and certain limited administrative roles.
- Can invalidate refresh tokens, manage service requests, and monitor service health.
- Has more limited permissions than User Administrator and Global Administrator.

### User Administrator

- Can create and manage users and groups.
- Can manage support tickets and monitor service health.
- Has restrictions on password resets and other administrative actions.

### Global Administrator

- Has broad administrative permissions across Microsoft Entra ID and connected services.
- Can reset passwords for users, including administrators.
- Can assign other administrator roles.
- Has a significantly broader level of access than the other two roles reviewed.

## Key Concepts

### Role-Based Access Control (RBAC)

RBAC grants permissions through assigned roles. In Microsoft Entra ID, directory roles provide administrative permissions for specific tasks.

### Privileged Access

A role marked as privileged includes one or more permissions that can have a significant impact on users, accounts, or organizational security.

### Principle of Least Privilege

Users should receive only the permissions necessary to perform their job responsibilities. More powerful roles should be restricted to authorized individuals who need them.

### Security Groups vs. Directory Roles

Security groups organize users and can be used to manage access to resources. Directory roles grant administrative permissions in Microsoft Entra ID. Membership in a security group does not automatically grant directory role privileges.

## Observations and Verification

- Reviewed the descriptions of Helpdesk Administrator, User Administrator, and Global Administrator.
- Confirmed that the lab account is assigned the Global Administrator role.
- Found no role assignments for Helpdesk Administrator or User Administrator during the review.
- Made no changes to role assignments during this lab.

## Security Considerations

- Limit the number of accounts assigned privileged roles.
- Assign roles according to job responsibilities.
- Review role assignments regularly.
- Avoid using highly privileged accounts for routine tasks when a less privileged account is sufficient.

## Conclusion

This lab demonstrated how Microsoft Entra directory roles provide different levels of administrative access. Reviewing
