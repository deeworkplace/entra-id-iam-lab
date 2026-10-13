# Lab 01: User Management 
 
## Objective

Practice basic user administration in Microsoft Entra ID by reviewing a user account, managing security group membership, and verifying the changes.

## Scenario

NorthStar Technology needs an account for Alex Employee, a new member of the IT helpdesk team. The account must be associated with the appropriate security group, with access kept separate from cloud administration responsibilities.

## Environment

- Platform: Microsoft Entra ID
- Tenant: Test tenant
- Organization: NorthStar Technology (fictional)

## Tasks

1. Locate the Alex Employee account.
2. Review the user's basic account information.
3. Create security groups for helpdesk and cloud administration.
4. Add Alex Employee to the appropriate group.
5. Verify the account details and group membership.
6. Document the changes.

## Actions Performed

- Located the Alex Employee account in Microsoft Entra ID.
- Created the `IT-Helpdesk` security group.
- Created the `IT-Cloud-Admins` security group.
- Added Alex Employee to the `IT-Helpdesk` group.

## Verification Results

- Account status: Enabled
- User type: Member
- `IT-Helpdesk` group membership: Confirmed
- `IT-Cloud-Admins` group membership: Not assigned
- Administrative roles: None assigned
- Additional resource permissions: None assigned

## Results

Alex Employee's account was verified, and the user was added to the IT-Helpdesk security group. The account remained enabled, with no administrative roles or additional resource permissions assigned.

Separate security groups were established for helpdesk and cloud administration to keep group membership organized according to job responsibilities.
