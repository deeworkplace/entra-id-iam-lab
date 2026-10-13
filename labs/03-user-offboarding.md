# Lab 03: User Offboarding and Access Removal 

## Objective

Practice offboarding a user in Microsoft Entra ID by disabling the account, removing security group memberships, and verifying the changes.

## Scenario

NorthStar Technology is processing an employee offboarding request. For this exercise, Alex Employee's account must be disabled and the user's existing security group memberships removed.

## Environment

- Platform: Microsoft Entra ID
- Tenant: Test tenant
- Organization: NorthStar Technology (fictional)
- Test user: Alex Employee

## Tasks

1. Review the user's account status and group memberships.
2. Disable the user account.
3. Remove the user from assigned security groups.
4. Verify the account status and group membership changes.

## Actions Performed

1. Reviewed Alex Employee's account in Microsoft Entra ID.
2. Confirmed that the account was enabled and the user type was Member before offboarding.
3. Reviewed the user's existing group memberships.
4. Disabled the Alex Employee account.
5. Removed Alex Employee from the `IT-Helpdesk` security group.
6. Removed Alex Employee from the `App-Internal-Users` security group.
7. Refreshed the account's Groups page to check the updated membership.

## Verification Results

- Account status: Disabled
- `IT-Helpdesk` membership: Removed
- `App-Internal-Users` membership: Removed
- Remaining group memberships: None listed

## Results

Alex Employee's account was disabled, and both security group memberships were removed. The account status and updated group membership list were checked in Microsoft Entra ID.

Existing sign-in sessions and access to connected applications were not independently tested. In a real offboarding process, additional steps may be needed to revoke active sessions, review application access, and complete any organization-specific offboarding requirements.

## Lessons Learned

- Review account status and existing group memberships before making changes.
- Follow the approved offboarding request and applicable organizational procedures.
- Disable the account and remove access according to the offboarding requirements.
- Verify the account status and group memberships after making changes.
- Record any access or sessions that were not independently tested.
