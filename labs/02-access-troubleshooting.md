## Lab 02: Access Troubleshooting

## Objective

Practice investigating a user access issue in Microsoft Entra ID by reviewing group membership, identifying a missing group, and verifying a membership change.

## Scenario

NorthStar Technology receives a helpdesk ticket from Alex Employee, who reports being unable to. access an internal company application.

For this simulated exercise, the application is assumged to require membership in the App-Internal-Users security group.

## Tasks

1. Review the user's account status and user type.
2. Inspect the user's existing group memberships.
3. Identify the missing application access group in the simulated scenario.
4. Create the required security group.
5. Add the user to the group.
6. Verify the updated group membership.

## Skills Demonstrated

- Microsoft Entra ID
- Identity and access management (IAM)
- Security group administration
- Access troubleshooting
- User provisioning
- Verification and documentation

## Environment

- Microsoft Entra ID test tenant
- Fictional organization: NorthStar Technology
- Test user: Alex Employee
- Simulated helpdesk ticket: #1002

## Actions Performed

1. Reviewed Alex Employee's account in Microsoft Entra ID.
2. Confirmed that the account was enabled and the user type was Member.
3. Reviewed the user's group memberships.
4. Searched for the simulated application access group, App-Internal-Users, and confirmed it did not exist.
5. Created the App-Internal-Users security group with Assigned membership.
6. Added Alex Employee to App-Internal-Users.

## Verification Results

- Confirmed that Alex Employee remained a member of IT-Helpdesk.
- Confirmed that Alex Employee appeared in the App-Internal-Users group membership list.
- Confirmed that both groups appeared under Alex Employee's group memberships.

## Results

Successfully created the simulated application access group, assigned Alex Employee to it, and verified the updated group membership.

The group membership change was verified, but access to an actual application was not tested. Therefore, successful application access has not been confirmed.

## Lessons Learned

- Review account status and group membership before changing access.
- Confirmed the required group or permissions before assigning access in a real environment.
- Verify changes after modifying group membership.
- Document what was tested and avoid claiming an issue is fully resolved without validating application access.
