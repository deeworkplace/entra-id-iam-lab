# Lab 06: Groups and Access Management

## Objective

Learn how Microsoft Entra ID security groups are configured and managed, how group membership changes are verified, and how group membership differs from administrative role assignments.

## Scenario

NorthStar Technologies needs a consistent way to organize users and manage access. The IT team uses security groups to organize accounts and must understand how group membership relates to permissions and administrative roles.

## Tasks

### 1. Review Security Group Properties

Located the existing `it helpdesk` security group in the Microsoft Entra admin center.

Reviewed the group's properties and confirmed:

- Group type: Security
- Membership type: Assigned
- Initial member count: 0

Assigned membership allows administrators to manually add and remove group members.

### 2. Add a Test User to the Group

Added the existing MFA Test User account to the `it helpdesk` security group.

Refreshed the Members page and confirmed that the test user appeared in the group membership list.

### 3. Verify Membership from the User Account

Opened the MFA Test User account and reviewed its Groups page.

Confirmed that `it helpdesk` appeared in the user's group list. This verified the membership change from both the group and user perspectives.

### 4. Remove the Test User

Removed MFA Test User from the `it helpdesk` security group.

Refreshed the Members page and confirmed that the user was no longer listed as a member.

The user account and its registered authentication method were not deleted or changed by this operation.

### 5. Review Administrative Roles

Opened the group's Roles and administrators page and reviewed the information about assignable roles and directory-level roles.

Learned that administrative roles grant privileged permissions and are managed differently from ordinary group membership.

No administrative roles were assigned during this exercise.

## Skills Demonstrated

- Reviewing Microsoft Entra security group properties.
- Understanding assigned group membership.
- Adding users to security groups.
- Verifying group membership from both group and user views.
- Removing users from security groups.
- Understanding the difference between group membership and administrative role assignments.
- Verifying changes and cleaning up a test environment.

## Environment

- Microsoft Entra ID free tenant
- Microsoft Entra admin center
- Existing `it helpdesk` security group
- Dedicated MFA Test User account

## Results

Successfully added MFA Test User to the `it helpdesk` security group, verified the membership from both the group and user account pages, and removed the user after testing.

Confirmed that the group returned to zero members and retained its Assigned membership type.

Reviewed the Roles and administrators page to understand the distinction between group membership and administrative role assignments.

## Key Learnings

## Key Learnings

Security groups provide a way to organize users and manage access consistently. With assigned membership, administrators manually control which users belong to the group.

Adding a user to a group does not automatically grant permissions unless that group is connected to an access assignment or permission configuration.

Administrative roles are different from ordinary group membership because they grant privileged permissions. Understanding this distinction helps administrators follow least privilege principles and avoid granting unnecessary access.

During this lab, I added MFA Test User to the `it helpdesk` security group, verified the membership from both the group and user pages, and then removed the user.

I also reviewed the group's Roles and administrators section to understand how administrative roles work. I did not assign any roles to the group during this lab.
