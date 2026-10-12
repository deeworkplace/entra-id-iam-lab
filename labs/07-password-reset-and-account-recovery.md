# Lab 07: Password Reset and Account Recovery

## Objective

Practice Microsoft Entra ID password reset concepts, review registered authentication methods, and investigate sign-in events related to account access problems.

## Scenario

A user experiences sign-in difficulties. As an IAM administrator, I review the available account information and sign-in logs to identify potential causes before making changes.

## Tasks Completed

### 1. Review Administrator-Initiated Password Reset

Used the Microsoft Entra admin center to initiate a password reset for the test user.

Entra ID generated a temporary password and indicated that the user must change it at the next sign-in.

Learned how administrators can initiate password resets and require users to establish a new password when signing in.

### 2. Review Self-Service Password Reset

Opened the Self-service password reset settings in Microsoft Entra ID.

The policy options displayed were None, Selected, and All. No option appeared selected, and the Save and Discard buttons were disabled.

An attempt to access the password reset policy returned the error:

`Read password reset policy forbidden`

The saved SSPR configuration could not be verified. No settings were changed.

### 3. Review Registered Authentication Methods

Opened the authentication methods for MFA Test User.

Observed the following registered method:

- Authentication method: Microsoft Authenticator
- Display name: iPhone 12
- Phone application version: 6.8.56

This confirmed that Microsoft Entra ID listed Microsoft Authenticator as a registered authentication method for the test user.

### 4. Investigate a Failed Sign-In

Reviewed a failed sign-in event in the user's sign-in logs.

- Status: Failure
- Sign-in error code: 50126
- Failure reason: Error validating credentials due to invalid username or password

Learned that error 50126 indicates that the submitted credentials were not accepted. The log alone did not establish whether the username or password was entered incorrectly.

### 5. Review an Interrupted Sign-In

Reviewed a separate sign-in event with the status Interrupted.

The authentication details showed:

- Authentication step: Password
- Authentication method: Password in the cloud
- Succeeded: True
- Result detail: Correct password

No sign-in error code or failure reason was available in the event details. The password step succeeded, but the overall sign-in was interrupted. The exact cause could not be determined from the available information.

### 6. Review a Successful Sign-In

Reviewed another sign-in event with the status Success.

The event did not provide authentication details that identified the authentication steps used.

Learned that a successful sign-in does not necessarily provide enough information to establish whether a fresh MFA challenge occurred.

## Skills Demonstrated

- Reviewing administrator-initiated password reset behavior
- Understanding self-service password reset concepts
- Reviewing registered Microsoft Authenticator methods
- Investigating failed sign-ins using error codes and failure reasons
- Distinguishing failed, interrupted, and successful sign-in events
- Recognizing when available evidence is insufficient to identify a root cause
- Avoiding unnecessary account and authentication changes during troubleshooting

## Environment

- Microsoft Entra ID
- Entra admin center
- Test account: MFA Test User
- Microsoft Authenticator
- Sign-in logs

## Results

Reviewed password reset concepts, confirmed the test user's registered Microsoft Authenticator method, and investigated multiple sign-in events.

The investigation identified an invalid-credentials failure with error code 50126 and an interrupted sign-in where the password step succeeded. Access to the saved SSPR policy configuration was restricted, so its effective setting could not be confirmed.

No authentication settings were changed during this lab.

## Key Learnings

Administrator-initiated password resets and self-service password reset are different processes. Administrators can initiate password resets, while SSPR allows eligible users to recover access themselves when the feature is configured and available to them.

Registered authentication methods provide useful information when investigating MFA issues, but registration alone does not prove that authentication requests are currently working.

Sign-in logs help administrators investigate access problems by showing the event status, error codes, failure reasons, and authentication steps when those details are available.

Error code 50126 indicates that the submitted username or password was not accepted. An interrupted sign-in with a successful password step requires further investigation before its cause can be determined.

Effective troubleshooting requires distinguishing confirmed evidence from assumptions and avoiding unnecessary changes to user accounts or authentication settings.
