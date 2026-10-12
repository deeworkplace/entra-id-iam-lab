# Lab 05: Authentication and Multi-Factor Authentication (MFA)

## Objective

Review Microsoft Entra ID authentication method policies, configure and verify a test user's Microsoft Authenticator registration, and examine how MFA-related sign-in activity is recorded.

## Scenario

NorthStar Technologies is reviewing its identity security configuration to understand how users authenticate and how administrators manage authentication methods. The IT team needs to verify registered authentication methods and understand how to investigate sign-in events without making unnecessary changes to security settings.

## Tasks

### 1. Review Authentication Method Policies

Reviewed the authentication method policies in the Microsoft Entra admin center without changing tenant configuration.

Methods reviewed included:

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

Observed that different authentication methods have different enablement settings, registration requirements, and configuration options.

### 2. Verify Security Defaults

Reviewed the tenant's Security Defaults configuration and confirmed that it was enabled.

Security Defaults provides baseline identity security protections. Its behavior does not guarantee a new MFA prompt for every sign-in.

### 3. Register Microsoft Authenticator

Created a dedicated test account named **MFA Test User**.

Completed the initial sign-in and password change, then registered Microsoft Authenticator on a mobile device. Completed the Authenticator registration process, including number matching and Face ID.

Verified in the Microsoft Entra admin center that the account's authentication methods included Microsoft Authenticator (iPhone12).

### 4. Review the Default Sign-In Method

Reviewed the test user's authentication methods and confirmed that the default sign-in method was **Microsoft Authenticator notification**.

Also reviewed the available administrative action to require a user to re-register multifactor authentication. Did not activate this action or modify the test user's authentication methods.

### 5. Investigate Sign-In Logs

Signed in to the test user's account through a private browser window and reviewed the corresponding sign-in logs.

Observed the following:

- Authentication requirement: Single-factor authentication.
- Authentication details indicated that the MFA requirement was satisfied by a claim in the token.
- The authentication details also indicated that no authentication events were triggered as part of that sign-in.

Repeated sign-in testing did not demonstrate a fresh MFA challenge. The results were recorded as observed rather than assuming that a new MFA challenge had occurred.

## Skills Demonstrated

- Reviewing Microsoft Entra ID authentication method policies.
- Understanding the purpose of Security Defaults.
- Registering Microsoft Authenticator for a test account.
- Verifying a user's registered authentication methods.
- Identifying the default sign-in method.
- Understanding administrative MFA re-registration controls.
- Reviewing sign-in logs and authentication requirements.
- Distinguishing a registered MFA method from evidence of a fresh MFA challenge.
- Documenting test results and limitations accurately.

## Environment

- Microsoft Entra ID free tenant
- Microsoft Entra admin center
- Dedicated MFA Test User account
- Microsoft Authenticator mobile application
- Private browser window for sign-in testing

## Results

Successfully registered Microsoft Authenticator for the test account and verified the registered method and default sign-in method in Microsoft Entra ID.

Reviewed Security Defaults and authentication method policies, and examined sign-in log details to understand how authentication requirements and token claims are reported.

The testing did not confirm a fresh MFA challenge. The sign-in logs reported single-factor authentication for the observed sign-in, with MFA requirement satisfaction indicated by a claim in the token. Further investigation would be required to demonstrate a fresh MFA challenge under controlled conditions.

No tenant-wide authentication policies were changed during this exercise.

## Key Learnings

Security Defaults is Microsoft's built-in set of baseline identity security protections in Microsoft Entra ID. It helps organizations protect accounts by requiring MFA registration, enforcing MFA in applicable sign-in scenarios, blocking legacy authentication, and protecting privileged accounts. During my lab, I confirmed that Security Defaults was enabled, registered Microsoft Authenticator for a test user, and reviewed the sign-in logs. I also learned that having an MFA method registered does not prove that a fresh MFA challenge occurred during a particular sign-in, so it's important to interpret the authentication details carefully.
