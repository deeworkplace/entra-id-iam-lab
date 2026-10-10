## Lab 03: User Offboarding and Access Removal

## Objective

Practice the user offboarding process in Microsoft Entra ID by disabling a user account, removing security group memberships, and verifying the changes.

## Scenario

NorthStar Technology is processing an employee offboarding request. As part of this simulated exercise, Alex Employee's account must be disabled and the user's group memberships removed.

## Tasks

1. Review the user's account status and group memberships.
2. Disable the. user account.
3. Remove the user from assigned security groups.
4. Verify the account status and group membership changes.

## Skills Demonstrated

- Microsoft Entra ID
- Identity and access management (IAM)
- User offboarding
- Account lifecycle management
- Security group administration
- Access removal and verification
- Technical documentation

## Environment
- Microsoft Entra ID test tenant
- Fictional organization: NorthStar Technology
- Test user: Alex Employee

## Actions Performed
1. Reviewed Alex Employee's account in Microsoft Entra ID.
2. Confirmed that the account was enabled and the user type was Member before offboarding.
3. Reviewed the user's group memberships.
4. Disabled Alex Employee's account.
5. Removed Alex Employee from the IT-Helpdesk security group.
6. Removed Alex Employee from the App-Internal-Users security group.
7. Refreshed the account's Groups page to verity the changes.

## Verification Results
- Confirmed that the account status showed Disabled.
- Confirmed that the Groups page no longer listed IT-Helpdesk or App-Internal-Users for Alex Employee.
- Confirmed that the user's group membership list was empty.

## Results
Successfully simulated the offboarding process by disabling Alex Employee's account, removing the user's group memberships, and verifying the resulting account status and group membership changes.

Existing sessions and access to connected applications were not independently tested. Additional session revocation and application-specific offboarding steps may be required in a real environment.

## Lessons Learned
- Review account status and group memberships before making changes.
- Follow an authorized offboarding request and organizational procedures.
- Disable accounts and remove access according to the organization's offboarding policy.
- Verify changes after performing account and group membership updates.
- Document what was verified and identify any access that was not independently tested.
