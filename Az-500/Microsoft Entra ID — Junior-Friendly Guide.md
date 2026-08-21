Microsoft Entra ID — Junior-Friendly Guide

What Is Microsoft Entra ID?

Microsoft Entra ID (formerly known as Azure Active Directory / Azure AD) is Microsoft’s cloud-based Identity and Access Management (IAM) service.

It helps organizations manage:

* Users
* Groups
* Authentication
* Permissions
* Application access
* Devices
* Security policies
* Administrator roles

Simple Definition

Think of Microsoft Entra ID as the digital security gatekeeper of a company.

When you sign in to services such as:

* Microsoft 365
* Outlook
* Microsoft Teams
* SharePoint
* Azure Portal
* Enterprise applications

using your work account:

rasha@company.com

Microsoft Entra ID can be involved in checking:

* Who you are
* Whether your authentication is valid
* Whether MFA is required and completed
* Whether your sign-in is considered risky
* What resources or applications you are allowed to access

⸻

Why Do Companies Use Microsoft Entra ID?

Without a centralized identity platform:

* Every application may have its own user accounts
* Users may need multiple passwords
* IT administration becomes more complicated
* Access management becomes harder
* Security risks increase

With Microsoft Entra ID:

* One central identity
* Centralized authentication
* Single Sign-On (SSO)
* Centralized access management
* Security policies
* Better visibility and control

Simple Comparison

Without Entra ID	With Entra ID
Multiple accounts	Centralized identity
Multiple passwords	Centralized authentication
Separate access management	Centralized access management
Difficult administration	Easier administration
More security risks	Stronger security controls

⸻

Who Uses Microsoft Entra ID?

1. IT Administrators

IT administrators use Entra ID to:

* Create users
* Disable users
* Manage groups
* Reset passwords
* Configure authentication methods
* Enable security policies
* Assign roles
* Manage application access
* Control administrative access

Example

An employee leaves the company.

The administrator can disable the user’s account in Entra ID.

This prevents the identity from being used to authenticate to resources that depend on that identity.

⸻

2. Developers

Developers use Microsoft Entra ID to:

* Add authentication to applications
* Implement Single Sign-On
* Secure APIs
* Register applications
* Request access tokens
* Integrate applications with Microsoft identity services

Example

A company develops an internal application with:

Sign in with Microsoft

The application can use Microsoft Entra ID to authenticate employees.

⸻

3. End Users

Employees interact with Entra ID regularly when accessing services such as:

* Microsoft Teams
* Outlook
* SharePoint
* Microsoft 365
* Azure Portal
* Enterprise applications

Users may not directly see Entra ID, but it can operate behind the scenes during authentication and authorization.

⸻

What Is a Tenant?

A tenant is a dedicated Microsoft Entra environment for an organization.

It contains identity-related objects such as:

* Users
* Groups
* Applications
* Service principals
* Devices
* Roles
* Policies

Simple Definition

Think of a tenant as:

An organization’s dedicated identity environment in Microsoft Entra ID.

Example

Company A:

contoso.onmicrosoft.com

Company B:

fabrikam.onmicrosoft.com

These companies can have separate Entra tenants.

Each tenant has its own identities, applications, configuration, and security settings.

⸻

Tenant vs. Subscription

This is an important Azure concept.

A Microsoft Entra tenant and an Azure subscription are not the same thing.

Entra Tenant

Primarily represents an organization’s identity environment.

It manages things such as:

* Users
* Groups
* Applications
* Authentication
* Identity policies
* Roles

Azure Subscription

Primarily represents a billing and resource-management boundary for Azure resources.

It contains resources such as:

* Virtual Machines
* Storage Accounts
* Virtual Networks
* Azure App Services

Easy Way to Remember

Tenant = Identity

Subscription = Azure Resources + Billing

An Azure subscription is associated with a Microsoft Entra tenant.

⸻

What Is Single Sign-On (SSO)?

SSO = Single Sign-On

SSO allows a user to authenticate once and then access multiple applications without having to enter credentials separately for every application.

Example

The user signs in with:

rasha@company.com

After authentication, the user can access applications such as:

* Teams
* Outlook
* SharePoint
* Azure Portal
* Other enterprise applications

without performing a completely separate login for every application.

Easy Way to Remember

SSO = Sign in once, access many applications.

⸻

What Is Multi-Factor Authentication (MFA)?

MFA = Multi-Factor Authentication

MFA requires users to provide more than one form of verification.

For example:

1. Password
2. Microsoft Authenticator approval

Other authentication methods can include:

* Security keys
* Passkeys
* Biometrics
* Authentication codes

Example

An attacker obtains a user’s password.

If MFA is required, the password alone may not be enough to complete authentication.

Easy Way to Remember

Password + another verification method = MFA

⸻

Authentication vs. Authorization

This is one of the most important concepts to understand.

Authentication

Authentication answers:

Who are you?

Example:

You enter your username and password.

Entra ID authenticates your identity.

⸻

Authorization

Authorization answers:

What are you allowed to access?

Example:

You successfully sign in, but you may only have permission to access certain applications or resources.

Easy Way to Remember

Authentication = Who are you?

Authorization = What can you access?

⸻

Main Features of Microsoft Entra ID

1. User and Group Management

Entra ID allows organizations to manage:

* Users
* Groups
* Administrative roles
* Devices
* Applications

Example

A new employee joins the company.

The administrator creates the user’s identity and adds the user to appropriate groups.

⸻

2. Authentication

Entra ID supports modern authentication methods and security features such as:

* Password authentication
* MFA
* Passwordless authentication
* Passkeys
* FIDO2 security keys
* Microsoft Authenticator

Authentication determines whether a user can successfully prove their identity.

⸻

3. Single Sign-On (SSO)

SSO allows users to access multiple applications after authenticating.

Example:

One identity → Multiple applications

This improves the user experience and can reduce the number of credentials users need to manage.

⸻

4. Conditional Access

Conditional Access allows organizations to create access policies based on conditions.

Think of it as:

IF these conditions are true → THEN allow or require something.

Example

A company may configure a policy requiring MFA when:

* A user accesses a sensitive application
* A sign-in is considered risky
* The user is outside a trusted environment

Another policy might block access under certain conditions.

Simple Model

User attempts sign-in
        ↓
Conditions evaluated
        ↓
Conditional Access policies
        ↓
Allow / Block / Require MFA / Other controls

Easy Way to Remember

Conditional Access = IF/THEN access rules

⸻

5. Identity Protection

Microsoft Entra ID includes identity-risk detection capabilities.

These capabilities can help identify potentially risky:

* Users
* Sign-ins
* Authentication events

Example

A user normally signs in from one region.

A suspicious sign-in occurs from an unusual location or under other risky conditions.

The sign-in may be evaluated as risky.

Organizations can use risk information together with Conditional Access policies to respond.

Easy Way to Remember

Identity Protection = Detect identity-related risk

⸻

6. Privileged Identity Management (PIM)

Microsoft Entra Privileged Identity Management (PIM) helps organizations manage privileged access.

Instead of giving an administrator permanent high-level access, an organization can use controlled, time-limited privileged access.

Example

An IT administrator needs Global Administrator privileges for a specific task.

Instead of keeping the role permanently active, the administrator can activate the role when needed, subject to configured controls.

This is commonly associated with:

Just-In-Time (JIT) privileged access

Easy Way to Remember

PIM = Protect privileged administrator access

⸻

7. Managed Identities

A Managed Identity allows an Azure resource to authenticate to supported services without developers having to store credentials such as passwords or secrets in application code.

Example

An Azure Virtual Machine needs to access:

Azure Key Vault

Instead of storing a secret inside the application, the VM can use a Managed Identity.

Conceptually:

Azure VM
   ↓
Managed Identity
   ↓
Microsoft Entra ID
   ↓
Azure Key Vault

Easy Way to Remember

Managed Identity = Identity for Azure resources

⸻

8. Application Registration

Applications can be registered in Microsoft Entra ID.

An application registration provides identity-related information that allows an application to integrate with Microsoft’s identity platform.

Developers may use application registrations for:

* Authentication
* Authorization
* OAuth 2.0
* OpenID Connect
* API access

Example

A company builds:

https://app.company.com

The development team registers the application in Entra ID so employees can sign in using their organizational identities.

⸻

Important Entra ID Concepts

Identity

An identity represents something that can be authenticated.

Depending on the scenario, this can include:

* A user
* An application
* A workload

⸻

User

A user represents a person or organizational identity.

Example:

rasha@company.com

⸻

Group

A group is a collection of identities.

Groups are commonly used to simplify:

* Access management
* Application assignments
* Permissions
* Policy targeting

Example:

Finance-Users
    ↓
Alice
Bob
Charlie

Instead of assigning access individually, administrators can manage access through the group.

⸻

Account

An account is the representation used to access a service or system, usually containing credentials or authentication-related information.

For junior-level understanding, remember:

User = identity representing a person

Account = access representation associated with that identity

⸻

Directory

A directory is the identity store/environment containing objects such as:

* Users
* Groups
* Applications
* Devices
* Other identity-related objects

In Microsoft Entra ID, the tenant represents the organization’s directory environment.

⸻

Global Administrator

Global Administrator is one of the highest-privileged administrative roles in Microsoft Entra ID.

A Global Administrator can perform a very broad range of administrative tasks across Microsoft services.

Because this role is highly privileged, organizations should protect and limit its use.

Best Practice

Use privileged access only when necessary and apply strong security controls such as:

* MFA
* PIM
* Least privilege
* Monitoring
* Auditing

⸻

Least Privilege

Least privilege means giving users and administrators only the permissions they need to perform their tasks.

Bad Example

A help-desk employee receives Global Administrator permissions.

Better Example

The employee receives only the administrative role required for help-desk tasks.

Easy Way to Remember

Least Privilege = Minimum permissions required

⸻

Entra ID Licensing

Microsoft Entra ID has different licensing levels.

At a high level:

Microsoft Entra ID Free

Provides core identity capabilities such as:

* User and group management
* Basic authentication capabilities
* Basic SSO capabilities
* Core directory functionality

⸻

Microsoft Entra ID P1

Adds capabilities such as:

* Conditional Access
* More advanced identity management
* Dynamic groups
* Hybrid identity capabilities
* Additional self-service features

⸻

Microsoft Entra ID P2

Adds advanced identity security capabilities such as:

* Microsoft Entra ID Protection
* Privileged Identity Management (PIM)
* Risk-based identity controls

Important: Microsoft licensing and feature availability can change. For certification exams, always check the current Microsoft documentation for the specific feature and license.

⸻

Important Terms for Exams

Term	Meaning
Identity	Something that can be authenticated
User	Identity representing a person
Group	Collection of users or other supported identities
Tenant	Organization’s dedicated Entra environment
Directory	Environment containing identity objects
Authentication	Proving who you are
Authorization	Determining what you can access
SSO	Sign in once and access multiple applications
MFA	Authentication using multiple verification factors
Conditional Access	Policy-based access controls
Global Administrator	Highly privileged Entra administrative role
Managed Identity	Identity used by Azure resources/workloads
PIM	Controls and manages privileged access
Identity Protection	Detects and responds to identity-related risks
Least Privilege	Giving only the permissions required

⸻

Authentication Flow — Simple Example

Imagine an employee wants to access an enterprise application.

User
  ↓
Enters work account
  ↓
Microsoft Entra ID
  ↓
Authentication
  ↓
MFA if required
  ↓
Conditional Access evaluation
  ↓
Authorization / Application access
  ↓
Application

The exact flow can vary depending on the application and authentication protocol, but this model is useful for understanding the basic concepts.

⸻

Real-World Example

Imagine a company called Contoso.

The company has:

* 500 employees
* Microsoft 365
* Azure resources
* Internal applications
* External SaaS applications

The company uses Microsoft Entra ID to manage employee identities.

Employee

rasha@contoso.com

Groups

Finance
IT
HR
Developers
Managers

Applications

Microsoft Teams
Outlook
SharePoint
Internal HR Application
Internal Finance Application

Security

The company requires:

* MFA
* Conditional Access
* Least privilege
* PIM for privileged administrators

Example Scenario

Rasha signs in from her laptop.

Rasha
  ↓
Microsoft Entra ID
  ↓
Authentication
  ↓
MFA
  ↓
Conditional Access
  ↓
Access granted
  ↓
Microsoft Teams

If Rasha’s sign-in violates a configured security policy, access may be blocked or additional requirements may be applied.

⸻

What Happens When an Employee Leaves?

This is a common real-world identity-management scenario.

Employee leaves the company

Employee leaves
      ↓
Admin disables the identity
      ↓
Authentication is prevented
      ↓
Access to dependent services is restricted

Additional offboarding actions may be required depending on the organization’s architecture, applications, devices, and security procedures.

Important Concept

Identity lifecycle management is about managing identities throughout their lifecycle:

Join → Manage → Change → Leave

⸻

Entra ID vs. Traditional Active Directory

These two technologies are related but are not the same.

Active Directory Domain Services (AD DS)

Traditional Active Directory is commonly used for on-premises environments.

It provides capabilities such as:

* Domain services
* Domain-joined computers
* Group Policy
* Kerberos
* LDAP
* Organizational Units

Microsoft Entra ID

Microsoft Entra ID is Microsoft’s cloud identity platform.

It focuses heavily on:

* Cloud authentication
* Modern authentication
* SaaS applications
* SSO
* MFA
* Conditional Access
* Cloud identity
* Application access

Easy Way to Remember

AD DS = Traditional/on-premises directory services

Entra ID = Cloud identity and access management

They can also work together in hybrid environments.

⸻

Common Junior-Level Interview Questions

What is Microsoft Entra ID?

Microsoft Entra ID is Microsoft’s cloud-based identity and access management service. It manages identities, authentication, authorization, application access, and identity security.

⸻

What is a tenant?

A tenant is an organization’s dedicated Microsoft Entra environment containing its identity objects, applications, policies, and configuration.

⸻

What is SSO?

SSO allows a user to authenticate once and access multiple applications without performing a separate login for every application.

⸻

What is MFA?

MFA requires more than one authentication factor or verification method to help protect user accounts.

⸻

What is Conditional Access?

Conditional Access is a policy-based access control system that evaluates conditions and can allow, block, or require additional controls such as MFA.

⸻

What is PIM?

Privileged Identity Management helps organizations manage privileged access by controlling and limiting when highly privileged roles are active.

⸻

What is a Managed Identity?

A Managed Identity provides an Azure resource or workload with an identity that can be used to authenticate to supported services without storing credentials in application code.

⸻

What is the difference between Authentication and Authorization?

Authentication: Who are you?

Authorization: What are you allowed to access?

⸻

The 5 Concepts Every Junior Should Know

If you are starting with Microsoft Entra ID, focus on these five concepts first:

1. Tenant

Understand what an Entra tenant represents.

2. Users and Groups

Understand how identities are organized and managed.

3. Authentication

Understand how users prove their identity.

4. MFA

Understand how additional verification protects accounts.

5. Conditional Access

Understand how organizations create rules that control access.

Once these concepts are clear, move on to:

* SSO
* Application registrations
* Service principals
* Managed identities
* Roles
* PIM
* Identity Protection
* Hybrid identity
* OAuth 2.0
* OpenID Connect
* Access tokens

⸻

Easy Mental Model

Think about Microsoft Entra ID like a company’s security system:

                 Microsoft Entra ID
                         |
        +----------------+----------------+
        |                |                |
      Users            Apps            Devices
        |                |                |
        +----------------+----------------+
                         |
                  Authentication
                         |
              +----------+----------+
              |                     |
             MFA            Conditional Access
              |                     |
              +----------+----------+
                         |
                    Authorization
                         |
                  Access Granted

⸻

One-Line Summary

Microsoft Entra ID is Microsoft’s cloud identity and access management platform that helps organizations manage identities, authenticate users, control access to applications and resources, and enforce identity security.

⸻

Quick Revision

Microsoft Entra ID
        ↓
Identity + Access Management
        ↓
Users
Groups
Authentication
Authorization
MFA
SSO
Conditional Access
Application Access
Identity Protection
PIM
Managed Identities
        ↓
Secure access to applications and resources

Final Memory Trick

Remember:

Entra ID = Identity + Authentication + Access + Security

And remember these core concepts:

Tenant
Users & Groups
Authentication
MFA
SSO
Conditional Access
PIM
Managed Identity

