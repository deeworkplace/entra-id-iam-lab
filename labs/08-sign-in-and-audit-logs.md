# Lab 08: Sign-in Logs and Audit Logs

## Objective

Review Microsoft Entra audit logs, identify the actor and target associated with an operation, and interpret recorded changes to user and group resources.

## Scenario

An IAM administrator reviews Microsoft Entra activity to determine which operations were recorded, whether they succeeded, who initiated them, and what information was available about the affected resources.

## Environment

- Microsoft Entra admin center
- Audit logs
- Date range: Last 7 days
- Test account: MFA Test User

## Tasks Performed

1. Opened the Microsoft Entra admin center and navigated to Identity, Monitoring & health, and Audit logs.
2. Reviewed a successful group-data retrieval event.
3. Examined the event's activity, category, status, initiating actor, target, and modified properties.
4. Reviewed a successful Add user event.
5. Compared the events to distinguish a data-retrieval operation from a user-management operation.

## Event 1: Group Data Retrieval

### Event Details

- Activity: `GroupsODataV4_Get`
- Category: GroupManagement
- Status: Success
- Status reason: OK
- Initiated by: Application
- App ID: Not displayed
- Target type: Other
- Target display name: Unknown
- Modified properties: None displayed

### Analysis

The activity name indicates a request to retrieve group data. The operation completed successfully, but the available event details did not identify a specific application or target resource.

No modified properties were displayed. Based on the available record, there is no evidence that this event created, modified, or deleted a group.

## Event 2: Add User

### Event Details

- Activity: `Add user`
- Category: UserManagement
- Date: October 11, 2026, at 3:00 PM
- Status: Success
- Initiated by: User
- Actor: Global Administrator account
- Target: MFA Test User

### Modified Properties

- `AccountEnabled`: New value `true`
- `DisplayName`: New value `MFA Test User`
- `MailNickname`: New value `mfa.test.user`
- `StsRefreshTokensValidFrom`: Recorded as `2026-10-11T19:00:21Z`

### Analysis

The audit log records a successful Add user operation initiated by the Global Administrator account. The target is MFA Test User, and the event lists the account's enabled state, display name, mail nickname, and refresh-token validity timestamp.

These details help identify the operation and the information recorded in the event. The log does not, by itself, confirm that refresh tokens were revoked.

## Key Learnings

- Audit logs provide evidence for investigating identity-related activity.
- The activity name identifies the operation recorded in an event.
- The initiating actor identifies the user or application associated with the operation.
- Target information helps identify the resource involved.
- Modified properties provide details about values recorded in an event.
- A successful status confirms that the logged operation succeeded, but additional context may be needed to understand why it occurred.
- An empty modified-properties section does not automatically indicate an error.
- Audit records should be interpreted using the activity, actor, target, status, and available property details together.

## Skills Practiced

- Navigating Microsoft Entra audit logs
- Identifying user-management and group-management activities
- Reviewing actor, target, and operation status
- Interpreting recorded property values
- Distinguishing data-retrieval events from user-management events
- Using audit-log evidence to support IAM investigations
