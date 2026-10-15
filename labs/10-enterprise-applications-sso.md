# Lab 10: Microsoft Entra ID SAML Single Sign-On

## Objective

Configure Microsoft Entra ID for SAML-based single sign-on (SSO) and test authentication using the FrostID SAML Service Provider playground.

## Environment

- **Identity Provider:** Microsoft Entra ID
- **Service Provider:** FrostID SAML Playground
- **Enterprise Application:** NorthStar SSO Test
- **Protocol:** SAML 2.0
- **NameID Format:** Unspecified
- **NameID Source:** Microsoft Entra user object ID

## Configuration

1. Created a non-gallery enterprise application in Microsoft Entra ID.
2. Set the SAML Identifier (Entity ID) to `https://sandbox-sp.frostid.se`.
3. Set the Reply URL (ACS URL) to `https://sandbox-sp.frostid.se/acs`.
4. Retrieved the application's federation metadata URL and submitted it to FrostID for validation.
5. Set the required NameID to `user.objectid` with the Unspecified format.
6. Removed additional claims that were not needed for the test.
7. Configured SAML assertion signing to meet the Service Provider's requirement for signed assertions.

## Validation

FrostID accepted the Microsoft Entra federation metadata and completed the SAML login test successfully.

The test verified:

- SAML Response signature
- Audience
- `InResponseTo` request correlation
- Assertion validity window

The returned NameID was an object identifier rather than an email address. The displayed assertion did not contain email, given name, surname, or user principal name attributes.

## Security and Privacy

- Used an object identifier instead of an email address for NameID.
- Removed unnecessary additional claims to limit the user information included in the assertion.
- Reviewed the returned assertion to understand which identity and authentication details were shared.
- Excluded detailed authentication output and sensitive identifiers from public portfolio evidence.

## Skills Demonstrated

- Microsoft Entra enterprise application configuration
- SAML 2.0 SSO setup and testing
- Entity ID and Reply URL configuration
- Federation metadata validation
- NameID and claims configuration
- SAML assertion signing and response validation
- Identity data minimization

## Outcome

Successfully configured and tested SAML SSO between Microsoft Entra ID and the FrostID playground. The test confirmed that the SAML response passed the signature, audience, request correlation, and validity checks.

## Evidence

The screenshot below shows the successful SAML login test and the validation checks completed by FrostID.

