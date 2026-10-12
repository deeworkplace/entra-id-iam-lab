# Lab 08: Sign-in Logs and Audit Logs

## Objective

Learn how to review Microsoft Entra audit logs, identify who initiated an operation, examine the affected target, and interpret recorded changes to user and group resources.

## Scenario

An IAM administrator investigates Microsoft Entra activity to understand which operations occurred, whether they succeeded, who initiated them, and what properties were affected.

## Environment

- Microsoft Entra admin center
- Audit logs
- Date range: Last 7 days
- Test account: MFA Test User

## Tasks Performed

1. Opened Microsoft Entra admin center and navigated to Identity, Monitoring & health, and Audit logs.
2. Reviewed a successful group-data retrieval event.
3. Examined the event's activity, category, status, actor, target, and modified properties.
4. Reviewed a successful Add user event.
5. Compared the two events to understand the difference between a retrieval operation and a recorded user-management operation.

## Event 1: Group Data Retrieval

**Event details**

- Activity: `GroupsODataV4_Get`
- Category: GroupManagement
- Status: Success
- Status reason: OK
- Initiated by: Application
- App ID: Not displayed
- Target type: Other
- Target display name: Unknown
- Modified properties: None displayed

**Analysis**

The activity name suggests a request to retrieve group data. The event completed successfully, but the available details did not identify a specific application or target resource.

No modified properties were displayed. The event does not establish that a group was created, modified, or deleted.

## Event 2: Add User

**Event details**

- Activity: `Add user`
- Category: UserManagement
- Date: October 11, 2026, at 3:00 PM
- Status: Success
- Initiated by: User
- Actor: Global Administrator account
- Target: MFA Test User

**Modified properties**

- `AccountEnabled`: New value `true`
- `DisplayName`: New value `MFA Test User`
- `MailNickname`: New value `mfa.test.user`
- `StsRefreshTokensValidFrom`: Recorded as `2026-10-11T19:00:21Z`

**Analysis**

The audit log records a successful Add user operation initiated by the Global Administrator account. The target matches MFA Test User, and the modified properties record the account's enabled state, display name, mail nickname, and refresh-token validity timestamp.

This event provides more specific evidence of a user-management operation than the group-data retrieval event because it includes identifiable target information and recorded property values.

## Key Learnings

- Audit logs help administrators investigate identity-related activity.
- The activity name describes the operation recorded in the event.
- The actor identifies the user or application recorded as initiating the operation.
- The target identifies the affected resource when that information is available.
- Modified properties help show which values were recorded as changing.
- A successful status means the logged operation succeeded, but context is still needed to understand why it occurred.
- An empty modified-properties section does not automatically indicate a problem.
- Audit records should be interpreted using the activity, actor, target, status, and property details together.

## Skills Practiced

- Navigating Microsoft Entra audit logs
- Identifying user-management and group-management activities
- Reviewing actor and target information
- Interpreting old and new property values
- Distinguishing retrieval operations from recorded identity changes
- Applying audit-log evidence to IAM investigations
