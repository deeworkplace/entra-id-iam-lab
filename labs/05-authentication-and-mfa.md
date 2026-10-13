# Lab 05: Authentication and Multi-Factor Authentication (MFA)

## Objective

Review Microsoft Entra ID authentication method policies, register Microsoft Authenticator for a test account, and examine sign-in logs to understand how authentication requirements are recorded.

## Scenario

NorthStar Technology is reviewing its identity security configuration to understand how users authenticate and how administrators manage authentication methods. The exercise focuses on checking existing settings, verifying a test user's registration, and reviewing sign-in activity without making unnecessary changes to tenant security policies.

## Environment

- Platform: Microsoft Entra ID
- Tenant: Free test tenant
- Test account: MFA Test User
- Authentication app: Microsoft Authenticator
- Sign-in testing: Private browser window

## Tasks Performed

### 1. Review Authentication Method Policies

Reviewed the authentication method policies in the Microsoft Entra admin center without changing tenant configuration.

The methods reviewed included:

- Microsoft Authenticator
- Passkey (FIDO2)
- Temporary Access Pass (TAP)
- Software OATH tokens
- Email one-time passcode (OTP)
- SMS
- Voice call
- Hardware OATH tokens
- Certificate-based authentication
- Verified ID
- QR code authentication

The available methods have different enablement settings and registration requirements. Their availability depends on the tenant configuration and the applicable authentication policies.

### 2. Check Security Defaults

Reviewed the tenant's Security Defaults configuration and confirmed that it was enabled.

Security Defaults provides baseline identity security protections, including MFA-related requirements in applicable sign-in scenarios. An enabled configuration does not mean every sign-in will trigger a new MFA prompt.

### 3. Register Microsoft Authenticator

Created a dedicated test account named `MFA Test User`.

After the initial sign-in and password change, Microsoft Authenticator was registered on a mobile device. The registration process included number matching and Face ID.

The Microsoft Entra admin center was then checked to verify the registered authentication method. Microsoft Authenticator was listed as **Microsoft Authenticator (iPhone12)**.

### 4. Review the Default Sign-In Method

Reviewed the test user's authentication methods and confirmed that the default sign-in method was **Microsoft Authenticator notification**.

The available administrative action to require MFA re-registration was also reviewed. The action was not activated, and no changes were made to the test user's authentication methods.

### 5. Review Sign-In Logs

Signed in to the test account through a private browser window and examined the corresponding sign-in logs.

The recorded details showed:

- Authentication requirement: Single-factor authentication
- MFA requirement: Satisfied by a claim in the token
- Authentication events: No authentication events were triggered as part of the observed sign-in

Repeated testing did not produce evidence of a fresh MFA challenge. The results were documented as recorded in the logs rather than assuming that a new challenge had occurred.

## Verification Results

- Security Defaults was enabled.
- Microsoft Authenticator was registered for `MFA Test User`.
- The registered method appeared in the user's authentication methods.
- Microsoft Authenticator notification was listed as the default sign-in method.
- The sign-in logs reported single-factor authentication for the observed sign-in.
- No fresh MFA challenge was confirmed during testing.
- No tenant-wide authentication policies were changed.

## Results

Microsoft Authenticator was successfully registered for the test account, and the registered method and default sign-in method were verified in Microsoft Entra ID.

The sign-in logs provided additional information about how the authentication requirement was evaluated. Although the token claim indicated that the MFA requirement had been satisfied, the observed sign-in was recorded as single-factor authentication, and no fresh MFA challenge was confirmed.

Further testing under controlled conditions would be needed to demonstrate a new MFA challenge and verify the resulting sign-in log details.

## Key Learnings

Registering an authentication method and completing an MFA challenge are two different things. A user can have Microsoft Authenticator registered without being prompted to approve a new request during every sign-in.

Security Defaults provides baseline identity protections, but the authentication experience depends on the sign-in context and the applicable requirements. Sign-in logs must be reviewed carefully to distinguish a registered method, a previously satisfied MFA requirement, and a new authentication event.

This lab also demonstrated how to verify authentication method registration and review sign-in evidence without changing tenant-wide security settings.
