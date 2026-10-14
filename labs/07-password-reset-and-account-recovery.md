# Lab 07: Password Reset and Account Recovery

## Objective

Review password reset options in Microsoft Entra ID, verify a test user's registered authentication method, and investigate sign-in events related to account access issues.

## Scenario

A user reports difficulty signing in. The helpdesk investigation involves reviewing the available account information and sign-in logs to identify possible causes before making account or authentication changes.

## Environment

- Platform: Microsoft Entra ID
- Test account: MFA Test User
- Authentication app: Microsoft Authenticator
- Tools: Microsoft Entra admin center and sign-in logs

## Tasks Performed

### 1. Review Administrator-Initiated Password Reset

Initiated a password reset for the test user through the Microsoft Entra admin center.

Entra ID generated a temporary password and indicated that the user would need to change it at the next sign-in.

This demonstrated how an administrator can initiate a password reset and require the user to establish a new password.

### 2. Review Self-Service Password Reset

Opened the Self-service password reset settings in Microsoft Entra ID.

The available policy options were None, Selected, and All. No option appeared selected, and the Save and Discard buttons were disabled.

An attempt to access the policy returned the following error:

`Read password reset policy forbidden`

The saved SSPR configuration could not be verified, and no settings were changed.

### 3. Review Registered Authentication Methods

Opened the authentication methods for MFA Test User.

The account listed the following method:

- Authentication method: Microsoft Authenticator
- Display name: iPhone 12
- Phone application version: 6.8.56

This confirmed that Microsoft Entra ID listed Microsoft Authenticator as a registered authentication method for the test account. It did not independently confirm that the method would succeed during a new authentication attempt.

### 4. Investigate a Failed Sign-In

Reviewed a failed sign-in event in the test user's sign-in logs.

- Status: Failure
- Sign-in error code: 50126
- Failure reason: Error validating credentials due to invalid username or password

The event indicated that the submitted credentials were not accepted. The available details did not establish whether the username or password was entered incorrectly.

### 5. Review an Interrupted Sign-In

Reviewed a separate sign-in event with the status Interrupted.

The authentication details showed:

- Authentication step: Password
- Authentication method: Password in the cloud
- Succeeded: True
- Result detail: Correct password

No sign-in error code or failure reason was available in the event details.

The password step succeeded, but the overall sign-in was interrupted. The available evidence was insufficient to determine the exact cause.

### 6. Review a Successful Sign-In

Reviewed another sign-in event with the status Success.

The event did not include authentication details identifying the steps used during that sign-in.

The available record confirmed a successful sign-in but did not establish whether a fresh MFA challenge occurred.

## Verification Results

- The administrator-initiated password reset generated a temporary password and indicated that a password change was required at the next sign-in.
- The saved SSPR configuration could not be verified because the policy request returned `Read password reset policy forbidden`.
- Microsoft Authenticator was listed as a registered method for MFA Test User.
- Sign-in error code 50126 identified a credentials validation failure.
- A separate interrupted sign-in showed that the password step succeeded, but the overall sign-in did not complete.
- A successful sign-in event was reviewed, but its available details did not establish whether a fresh MFA challenge occurred.
- No authentication settings were changed during the investigation.

## Results

The review covered administrator-initiated password resets, SSPR policy access, registered authentication methods, and three types of sign-in outcomes.

The logs identified a credentials validation failure and an interrupted sign-in where the password step succeeded. The cause of the interrupted sign-in could not be determined from the available event details.

Access to the saved SSPR configuration was restricted, so the effective policy setting could not be confirmed. No authentication settings were changed during this lab.

## Key Learnings

Password reset options serve different purposes. Administrators can initiate resets for users, while self-service password reset allows eligible users to recover access when the feature is configured and available to them.

Registered authentication methods are useful when investigating sign-in issues, but registration alone does not confirm that the method will work during a new sign-in.

Sign-in logs provide evidence for troubleshooting, but each event must be interpreted in context. A failed credentials check, an interrupted sign-in, and a successful sign-in represent different outcomes. When the logs do not identify the cause, further investigation is needed rather than assuming what happened.
