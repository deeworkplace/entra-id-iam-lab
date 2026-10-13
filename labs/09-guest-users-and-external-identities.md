# Lab 09: Guest Users and External Identities

## Objective

Review guest account configuration in Microsoft Entra ID, complete an external user invitation, verify the guest account properties, and examine the related audit log event.

## 1. Review External Collaboration Settings

The existing settings under **Identity > External Identities > External collaboration settings** were reviewed.

Findings:

- Guest users have limited access to directory object properties and memberships.
- Anyone in the organization, including guests and non-admin users, can invite guest users.
- Guest self-service sign-up through user flows is disabled.
- External users are allowed to remove themselves from the organization.
- Invitations to specified domains are denied.
- Email one-time passcode settings for guests are available under All Identity Providers.

No configuration changes were made.

The invitation policy allows a broad range of users to invite external guests. This makes regular reviews of guest accounts and their access important for maintaining appropriate access controls.

## 2. Invite and Accept a Test Guest

A test guest account named `NorthStar Test Guest` was created using an alternate email address.

The invitation was opened from the invited email account and the redemption process was completed. During sign-in, the option to create a passkey was presented. Passkey enrollment was completed, and the session was set to remain signed in.

After the invitation was redeemed, access to the dashboard was confirmed.

This process demonstrated that sending an invitation and redeeming it are separate steps. Successful redemption confirms that the external user completed the invitation process, but does not automatically grant access to company resources.

## 3. Review the Guest Account

The `NorthStar Test Guest` account was reviewed in the Microsoft Entra admin center.

Account findings:

- User type: Guest
- Account enabled: Yes
- B2B invitation state: Accepted
- B2B collaboration: Current user is external
- Group memberships: None
- Assigned directory roles: None
- Application assignments: None found

The account also displayed a **Convert to Internal User** option. No conversion was performed, and the account remained a Guest.

Although the account was enabled and the invitation had been accepted, no group memberships, directory roles, or application assignments were found. This demonstrates that a guest account can complete the sign-in process without automatically receiving permissions to company resources.

## 4. Review the Guest Invitation Audit Log

The audit logs under **Entra ID > Monitoring & health > Audit logs** were reviewed for the invitation redemption event.

Event details:

- Activity: Redeem external user invite
- Date: October 13, 2026, at 3:39 PM
- Category: UserManagement
- Status: Success
- Status reason: Blank
- Initiated by: User
- Initiating actor display name: Blank
- Initiating actor object ID: Blank
- User Principal Name: Alternate email address used for the invitation
- User agent: iPhone running iOS 18.6.2, with Safari reported as the browser
- Correlation ID: Available in the original audit record

The successful audit event was consistent with the Accepted invitation state shown on the guest account.

The initiating actor's display name and object ID were blank. These fields alone do not indicate a failure because the event status was Success.

The user agent provided contextual information about the browser and operating system reported with the request. This information does not independently verify the identity of the person or the physical device used.

The correlation ID was retained in the original audit record for potential investigation of related events. It should not be included in publicly shared lab documentation.

## 5. Key Findings

This lab demonstrated several important aspects of external identity management in Microsoft Entra ID.

**Guest identity and invitation state are separate properties.** The User type identifies the account as a Guest, while the invitation state indicates whether the external user has accepted the invitation.

**Authentication does not automatically grant authorization.** The guest successfully redeemed the invitation and completed sign-in, but no group memberships, directory roles, or application assignments were found.

**Audit logs provide evidence of identity-related activity.** The successful Redeem external user invite event supported the invitation state displayed on the account.

**Guest invitation policies affect access governance.** When users across an organization can invite guests, regular reviews are important to ensure external accounts remain appropriate and do not retain unnecessary access.

## Conclusion

The external guest invitation was successfully redeemed, the guest account properties were reviewed, and the corresponding audit log event was identified.

The findings confirm that successful invitation redemption does not, by itself, grant access to company resources. Guest access must be evaluated through group memberships, directory roles, application assignments, and any other applicable access controls.

The test account remains a Guest, no additional permissions were assigned, and no tenant-wide settings were changed.
