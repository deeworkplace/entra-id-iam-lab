# Lab 04: Role-Based Access Control (RBAC)

## Objective

Review Microsoft Entra ID administrative roles, compare their permissions, and examine how role assignments support least-privilege access.

## Environment

- Platform: Microsoft Entra admin center
- Tenant: Practice tenant

## Tasks Performed

1. Opened **Identity > Roles & admins**.
2. Reviewed the Helpdesk Administrator role and its assignment page.
3. Reviewed the User Administrator role and its assignment page.
4. Reviewed the Global Administrator role and its assignment page.
5. Compared the responsibilities and permission levels of the three roles.
6. Reviewed the meaning of privileged role classifications.

## Role Comparison

### Helpdesk Administrator

- Can reset passwords for certain non-administrator users and perform other support-related tasks, subject to role restrictions.
- Can manage support requests and access service health information.
- Has a narrower set of administrative permissions than the User Administrator and Global Administrator roles.

### User Administrator

- Can create and manage users and groups, subject to the role's permission boundaries.
- Can perform certain user and group administration tasks and manage support requests.
- Has restrictions on actions involving some privileged accounts and administrative roles.

### Global Administrator

- Has broad administrative permissions across Microsoft Entra ID and many connected Microsoft services.
- Can manage administrator roles and perform sensitive account management tasks.
- Has substantially broader permissions than the other two roles reviewed.

## Key Concepts

### Role-Based Access Control

Microsoft Entra ID uses directory roles to grant administrative permissions. Each role provides a defined set of permissions for specific management tasks.

### Privileged Roles

Roles identified as privileged can provide permissions that have a significant impact on accounts, access, or organizational security. These assignments require careful control and regular review.

### Principle of Least Privilege

Accounts should have only the permissions needed to perform their assigned responsibilities. Administrative roles should be limited to authorized users who need those permissions.

### Security Groups and Directory Roles

Security groups organize users and can be used to manage access to resources. Directory roles provide administrative permissions within Microsoft Entra ID. Adding a user to a security group does not automatically grant that user a directory role.

## Observations and Verification

- Reviewed the descriptions and assignment pages for Helpdesk Administrator, User Administrator, and Global Administrator.
- Confirmed that the lab account was assigned the Global Administrator role.
- No assignments for Helpdesk Administrator or User Administrator were found during the review.
- No role assignments were changed.

## Security Considerations

- Keep privileged role assignments limited to users who require them.
- Match administrative permissions to job responsibilities.
- Review role assignments periodically and remove access that is no longer needed.
- Use a less privileged account for routine work when possible.

## Conclusion

The review showed how Microsoft Entra directory roles provide different levels of administrative access. Helpdesk Administrator focuses on support tasks, User Administrator covers broader user and group management, and Global Administrator has extensive administrative permissions.

Understanding these differences helps identify excessive privileges and apply least-privilege principles when managing identities and administrative access.
