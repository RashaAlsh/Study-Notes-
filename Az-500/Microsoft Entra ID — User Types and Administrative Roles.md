Microsoft Entra ID — User Types and Administrative Roles

This section explains how to securely manage users in Microsoft Entra ID by understanding user types, external identities, and the principle of least privilege.

⸻

Required Administrative Roles

Different administrative tasks require different Microsoft Entra roles.

Task	Minimum Role
Create a new user	User Administrator
Invite an external guest	Guest Inviter
Assign Microsoft Entra roles	Privileged Role Administrator
Full administrative control of the tenant	Global Administrator

Security Best Practice: Always use the least privileged role necessary instead of using Global Administrator for every task.

⸻

User Types in Microsoft Entra ID

Microsoft Entra ID primarily uses two UserType values:

* Member
* Guest

However, users can also be classified based on whether their identity originates from your organization or from an external organization.

This gives us four useful scenarios to understand:

1. Internal Member
2. Internal Guest
3. External Member
4. External Guest

Important: Internal/External describes the origin and management of the identity. Member/Guest is the user’s Entra UserType.

⸻

1. Internal Member

Who Are They?

Internal Members are users who belong to your organization and are normally created and managed within your Microsoft Entra tenant.

Examples:

* Regular employees
* Full-time staff
* Internal workers

Authentication

Authentication is generally managed by your organization’s identity environment.

Depending on the configuration, users may authenticate using:

* Passwords
* Microsoft Authenticator
* Passwordless authentication
* Passkeys
* Security keys
* Other supported authentication methods

Password resets may be performed by administrators or through Self-Service Password Reset (SSPR) if enabled.

Access Level

The user has the Member user type and normally receives the internal user experience of the organization.

Example

john@contoso.com

⸻

2. Internal Guest

Who Are They?

An internal guest is a user who exists in your Microsoft Entra tenant but has the Guest user type.

This can occur in scenarios where an organization creates or maintains guest-style accounts internally.

Authentication

Depending on how the account was created and configured, authentication may be managed within the tenant or through an external identity.

Access Level

The user has the Guest user type and is normally treated as an external/limited-access identity from an authorization perspective.

Important: Do not assume that every Guest account has its password stored in your tenant. The authentication method depends on the identity configuration.

⸻

3. External Member

Who Are They?

An external member scenario involves a user whose identity originates outside your organization but who is represented as a Member in your tenant.

This can occur in certain multi-tenant or cross-organization scenarios.

Authentication

The user’s identity may be authenticated through their home organization or another configured identity provider.

For example:

User
  ↓
Home Organization
  ↓
Authentication
  ↓
Your Entra Tenant

Password Reset

If authentication is performed by the user’s home organization, password management is handled by that organization.

Access Level

The user has the Member user type in your tenant.

Important: Being an external user does not automatically mean the user must have the Guest user type.

⸻

4. External Guest

This is the most common B2B collaboration scenario.

Who Are They?

External guests are people from outside your organization who need access to selected resources.

Examples:

* Vendors
* Partners
* Contractors
* Consultants
* Customers

Authentication

External guests can authenticate using an identity associated with their home organization or another supported external identity method.

A common flow is:

External User
      ↓
Invitation
      ↓
External Identity
      ↓
Authentication
      ↓
Your Entra Tenant
      ↓
Access to Assigned Resources

Password Reset

If the user authenticates through their home organization, password management is handled by that organization.

If another authentication method is used, password management depends on that method.

Access Level

The user has the Guest user type.

Guest access should normally be limited to the resources the external user actually needs.

Example

A company invites a supplier to collaborate on a Microsoft Teams project.

The supplier may receive guest access to selected organizational resources without becoming a normal internal employee account.

⸻

User Type Comparison

Scenario	User Type	Identity Origin	Typical Authentication
Internal employee	Member	Your organization	Your organization’s identity system
Internal guest-style account	Guest	Your tenant or configured identity source	Depends on configuration
External user represented as a member	Member	External organization	Home organization or configured identity provider
External B2B collaborator	Guest	External organization	External identity / home provider

⸻

Member vs. Guest

A simple way to understand the difference:

Member

Generally represents a user who belongs to the organization or is treated as a regular organizational user within the tenant.

Guest

Generally represents a user who needs limited collaboration or external access.

Memory Aid

Member = Regular organizational user experience
Guest = External / limited collaboration scenario

Important: Do not interpret “Guest = no permissions.” A Guest can receive significant permissions if administrators explicitly assign them. The difference is the identity type and intended access model, not a guarantee of specific permissions.

⸻

Internal vs. External

Another useful distinction is the origin of the identity.

Internal

The identity is managed within your organization’s identity environment.

Internal User
      ↓
Your Entra Tenant
      ↓
Authentication / Access

External

The identity originates outside your organization’s identity environment.

External User
      ↓
Home Organization / External Identity
      ↓
Your Entra Tenant
      ↓
Access

Easy Memory Aid

Internal = Your organization manages the identity.

External = The identity originates outside your organization.

⸻

Password Management

Password management depends on where the user authenticates.

Do not simply assume:

External = Password is outside your tenant

or:

Internal = Password is always stored in your tenant

The actual behavior depends on the user’s identity configuration and authentication method.

For example:

* A cloud-only user may have their authentication managed directly by Microsoft Entra ID.
* A synchronized identity may have authentication connected to an on-premises identity system.
* A B2B guest may authenticate through their home organization.
* Other external authentication methods may also be used.

⸻

Security Recommendations

1. Use Guest Access for External Collaboration

When external users need access to organizational resources, use an appropriate guest/B2B model rather than treating them like normal employees.

⸻

2. Grant Only the Access They Need

Follow the principle of least privilege.

Do not give an external user more access than required.

Required Access
      ↓
Minimum Permissions
      ↓
Regular Review

⸻

3. Apply MFA

Use Multi-Factor Authentication (MFA) to provide additional protection for external and internal users.

Conditional Access can be used to enforce authentication requirements based on organizational policies.

⸻

4. Use Conditional Access

Conditional Access can help enforce rules for external users.

For example:

IF
User is external
      ↓
THEN
Require MFA

More advanced policies can evaluate additional conditions such as:

* User
* Group
* Application
* Device
* Location
* Risk
* Authentication context

⸻

5. Regularly Review Guest Accounts

Guest accounts should be reviewed regularly.

Remove or disable accounts that are no longer required.

This helps reduce unnecessary external access.

⸻

6. Use Privileged Identity Management

For privileged administrative roles, consider using Microsoft Entra Privileged Identity Management (PIM).

PIM can help organizations:

* Limit permanent privileged access
* Use Just-In-Time access
* Require additional controls
* Review privileged role assignments
* Audit privileged activity

⸻

Least Privilege

The principle of least privilege means:

Give a user or administrator only the permissions required to perform their task.

Example

A help-desk administrator needs to manage users.

Do not automatically give the administrator:

Global Administrator

Instead, assign the appropriate administrative role that provides the required permissions.

Simple Model

Task
  ↓
Required Permission
  ↓
Minimum Role

⸻

Example: Choosing the Correct Administrative Role

Imagine an administrator needs to perform four different tasks.

Task 1 — Create a User

Use:

User Administrator

Task 2 — Invite an External Guest

Use:

Guest Inviter

Task 3 — Assign Microsoft Entra Roles

Use an appropriate privileged role such as:

Privileged Role Administrator

Task 4 — Full Tenant Administration

Use:

Global Administrator

Because Global Administrator is highly privileged, it should not be used when a less privileged role can perform the task.

⸻

Exam Tips

Remember the Two User Types

UserType
   ↓
Member
Guest

⸻

Remember Identity Origin

Internal
External

These are useful concepts, but they are not the same thing as the Member and Guest user types.

⸻

Remember Authentication

Ask:

Where does this user authenticate?

Possible answers include:

* Your Entra tenant
* Their home organization
* Another configured identity provider
* Another supported authentication method

⸻

Remember Least Privilege

Ask:

What is the minimum role required for this task?

Do not automatically choose:

Global Administrator

⸻

Quick Revision

Microsoft Entra ID
        ↓
Users
        ↓
Member / Guest
        ↓
Internal / External Identity Origin
        ↓
Authentication
        ↓
Authorization
        ↓
Access

Administrative Roles

Create User
    ↓
User Administrator
Invite Guest
    ↓
Guest Inviter
Assign Entra Roles
    ↓
Privileged Role Administrator
Full Tenant Administration
    ↓
Global Administrator

⸻

Final Memory Aid

Remember these three concepts:

1. Member vs. Guest

Member = Regular organizational user type

Guest = Collaboration/external user type

2. Internal vs. External

Internal = Identity originates from your organization

External = Identity originates outside your organization

3. Least Privilege

Give only the permissions required for the task.

Best Practice: Protect privileged roles, use MFA and Conditional Access, regularly review external access, and avoid using Global Administrator when a more specific role is sufficient.