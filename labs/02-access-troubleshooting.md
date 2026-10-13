# Lab 02: Access Troubleshooting 

## Objective 
 
Investigate a simulated user access issue in Microsoft Entra ID by reviewing account details and group memberships, identifying a missing security group, and verifying the membership change.

## Scenario

NorthStar Technology receives helpdesk ticket #1002 from Alex Employee, who reports being unable to access an internal company application.

For this exercise, the application is assumed to require membership in the `App-Internal-Users` security group. The application itself is not connected to the test environment, so access will be assessed by checking the user's group membership.

## Environment

- Platform: Microsoft Entra ID
- Tenant: Test tenant
- Organization: NorthStar Technology (fictional)
- Test user: Alex Employee
- Helpdesk ticket: #1002

## Tasks

1. Review the user's account status and user type.
2. Check the user's existing group memberships.
3. Determine whether the required security group exists.
4. Create the group if it is missing.
5. Add the user to the group.
6. Verify the updated membership.

## Actions Performed

1. Reviewed Alex Employee's account in Microsoft Entra ID.
2. Confirmed that the account was enabled and the user type was Member.
3. Reviewed the user's existing group memberships.
4. Searched for `App-Internal-Users` and confirmed that the group did not exist.
5. Created the `App-Internal-Users` security group using Assigned membership.
6. Added Alex Employee to the new group.

## Verification Results

- Alex Employee remained a member of `IT-Helpdesk`.
- Alex Employee appeared in the `App-Internal-Users` group membership list.
- Both groups appeared under Alex Employee's group memberships.

## Results

The missing `App-Internal-Users` security group was created, and Alex Employee was added to it. The updated membership was verified in Microsoft Entra ID.

Because the internal application was not connected to the test environment, application access could not be tested. The group membership change was confirmed, but successful access to the application remains unverified.

## Lessons Learned

- Check account status and existing group memberships before making access changes.
- Confirm the required group or permissions before assigning access in a real environment.
- Verify group membership after making changes.
- Distinguish between confirming an identity configuration change and confirming that the user can access the application.
