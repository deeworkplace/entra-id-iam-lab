# Lab 09: Guest Users and External Identities

## Objective

Review guest account configuration in Microsoft Entra ID, complete an external user invitation, verify the guest account properties, and examine the related audit log event.

## Scenario

An IAM administrator reviews external collaboration settings and tests the guest invitation process to understand how external identities are created, authenticated, and assigned access.

## Environment

- Microsoft Entra admin center
- External collaboration settings
- Guest user account
- Audit logs
- Test guest: `NorthStar Test Guest`

## Tasks Performed

1. Reviewed Microsoft Entra external collaboration settings.
2. Created and redeemed an invitation for a test guest account.
3. Verified the guest account properties after invitation redemption.
4. Reviewed the corresponding `Redeem external user invite` audit event.
5. Confirmed that the guest account had no group memberships, directory roles, or application assignments.

## 1. Review External Collaboration Settings

The settings under **Identity > External Identities > External collaboration settings** were reviewed.

### Findings

- Guest users have limited access to directory object properties and memberships.
- Anyone in the organization, including guests and non-admin users, can invite guest users.
- Guest self-service sign-up through user flows is disabled.
- External users are allowed to remove themselves from the organization.
- Invitations to specified domains are denied.
- Email one-time passcode settings for guests are available under **All Identity Providers**.

No configuration changes were made.

The current invitation policy allows a broad range of users to invite external guests. Guest accounts should therefore be reviewed regularly to ensure external access remains appropriate.

## 2. Invite and Redeem a Test Guest

A test guest account named `NorthStar Test Guest` was created using an alternate email address.

The invitation was opened from the invited email account and the redemption process was completed. During sign-in, the option to create a passkey was presented. Passkey enrollment was completed, and the session was set to remain signed in.

After the invitation was redeemed, access to the dashboard was confirmed.

The invitation and redemption process demonstrated that an external user must complete the invitation process before the guest account can be used for authentication. Successful redemption does not automatically provide access to company resources.

## 3. Review the Guest Account

The `NorthStar Test Guest` account was reviewed in the Microsoft Entra admin center.

### Account Findings

- User type: Guest
- Account enabled: Yes
- B2B invitation state: Accepted
- B2B collaboration: Current user is external
- Group memberships: None
- Assigned directory roles: None
- Application assignments: None found

The account also displayed a **Convert to Internal User** option. No conversion was performed, and the account remained a Guest.

The guest account was enabled and the invitation was accepted, but no additional access assignments were found.

## 4. Review the Guest Invitation Audit Log

The audit logs under **Entra ID > Monitoring & health > Audit logs** were reviewed for the invitation redemption event.

### Event Details

- Activity: `Redeem external user invite`
- Date: October 13, 2026, at 3:39 PM
- Category: UserManagement
- Status: Success
- Status reason: Blank
- Initiated by: User
- Initiating actor display name: Blank
- Initiating actor object ID: Blank
- User Principal Name: Alternate email address used for the invitation
- User agent: iPhone running iOS 18.6.2 with Safari
- Correlation ID: Available in the original audit record

The successful audit event was consistent with the **Accepted** invitation state shown on the guest account.

The initiating actor display name and object ID were blank. Because the event status was **Success**, the blank fields do not indicate that the operation failed.

The user agent provided information about the browser and operating system reported with the request. This information does not independently verify the identity of the person or the physical device.

The correlation ID was retained in the original audit record for potential investigation of related events and was not included in the lab documentation.

## Key Learnings

- Guest accounts are identified separately from internal users through the User type property.
- The B2B invitation state shows whether the external user has accepted the invitation.
- Successfully redeeming an invitation does not automatically grant access to company resources.
- Group memberships, directory roles, and application assignments are separate access controls that should be reviewed when evaluating guest access.
- Audit logs provide evidence of guest invitation and redemption activity.
- Blank fields in a successful audit event do not necessarily indicate an error.
- Guest invitation policies should be reviewed as part of external access governance.

## Conclusion

The test guest invitation was successfully redeemed, the guest account properties were reviewed, and the corresponding audit log event was identified.

The guest account remained a Guest with no group memberships, directory roles, or application assignments. No tenant-wide settings were changed during the lab.
