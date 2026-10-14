# Lab 06: Groups and Access Management

## Objective

Practice managing security group membership in Microsoft Entra ID and verifying changes from both the group and user account views. Review how group membership differs from administrative role assignments.

## Scenario

NorthStar Technology uses security groups to organize users and manage access. This exercise focuses on reviewing an existing group, adding and removing a test user, and checking how membership changes appear in Microsoft Entra ID.

## Environment

- Platform: Microsoft Entra ID
- Tenant: Free test tenant
- Security group: `IT-Helpdesk`
- Test account: MFA Test User

## Tasks Performed

### 1. Review Security Group Properties

Located the existing `IT-Helpdesk` security group in the Microsoft Entra admin center.

The group properties showed:

- Group type: Security
- Membership type: Assigned
- Initial member count: 0

Assigned membership allows administrators to manage group membership manually by adding or removing users.

### 2. Add a Test User

Added MFA Test User to the `IT-Helpdesk` security group.

After refreshing the Members page, the test account appeared in the group's membership list.

### 3. Verify Membership from the User Account

Opened the MFA Test User account and checked its Groups page.

The `IT-Helpdesk` group appeared in the user's group list, confirming the membership change from both the group and user account views.

### 4. Remove the Test User

Removed MFA Test User from the `IT-Helpdesk` group.

After refreshing the Members page, the user was no longer listed. The group returned to zero members and retained its Assigned membership type.

The removal affected the user's membership in this group. The user account and its registered authentication method remained in place.

### 5. Review Administrative Roles

Opened the group's Roles and administrators page and reviewed the information about administrative role assignments.

Directory roles grant administrative permissions, while ordinary security group membership organizes users and may be used to manage access to resources. No administrative roles were assigned during this exercise.

## Verification Results

- Confirmed the group type was Security.
- Confirmed the membership type was Assigned.
- Verified that MFA Test User appeared in the group membership list after being added.
- Verified that `IT-Helpdesk` appeared on the user's Groups page.
- Confirmed that the user no longer appeared in the group after removal.
- Confirmed that the group returned to zero members.
- No administrative roles were assigned.

## Results

MFA Test User was added to and removed from the `IT-Helpdesk` security group. The membership change was verified from both the group and user account views.

The group retained its original configuration, and the test account remained in place with its authentication method unchanged. The review of the Roles and administrators page also reinforced the distinction between group membership and directory role assignments.

## Key Learnings

Assigned membership gives administrators direct control over which users belong to a security group. Checking membership from both the group and user account pages provides a useful way to verify changes.

Group membership does not automatically grant permissions in every situation. Access depends on how the group is used by an application, resource, or access policy.

Directory roles are separate from ordinary group membership and can grant privileged administrative permissions. Keeping these distinctions clear helps prevent unnecessary access and supports the principle of least privilege.
