⸻
 
What Are Microsoft Entra Roles?
Microsoft Entra built-in roles provide administrative permissions inside Microsoft Entra ID.
Unlike Azure RBAC, which controls access to Azure resources such as:
* Virtual Machines
* Storage Accounts
* Resource Groups
* Virtual Networks
Microsoft Entra roles manage identity and directory resources, such as:
* Users
* Groups
* Applications
* Authentication methods
* Passwords
* Domains
* Licenses
* Security attributes
 
⸻
 
Microsoft Entra Roles vs Azure RBAC
Microsoft Entra Roles
Microsoft Entra roles manage identity and directory resources.
Examples:
* Global Administrator
* User Administrator
* Application Administrator
* Authentication Administrator
Scope:
Microsoft Entra ID
 
⸻
 
Azure RBAC
Azure RBAC manages Azure resources.
Examples:
* Owner
* Contributor
* Reader
Scopes:
Management Group
        ↓
Subscription
        ↓
Resource Group
        ↓
Resource
Easy Memory Trick
Microsoft Entra Roles
        ↓
Identity / Directory

Azure RBAC
        ↓
Azure Resources
 
⸻
 
1. Global Administrator
Purpose
The Global Administrator has the highest level of administrative access in Microsoft Entra ID.
Think of it as:
Global Administrator
        ↓
Broad / Full Administrative Control
Because of the high level of privilege, this role should be used carefully.
Security Best Practice
Use lower-privileged roles whenever possible.
Follow the principle of:
Least Privilege
 
⸻
 
2. Application Administrator ⭐
Purpose
The Application Administrator manages applications and enterprise applications in Microsoft Entra ID.
Can Do
* Create application registrations
* Delete applications
* Manage enterprise applications
* Manage Application Proxy
* Manage service principals
* Manage application credentials
* Manage OAuth permission grants
* Create provisioning connectors
* Manage synchronization settings
* Create support tickets
 
⸻
 
Important Exam Point ⚠️
An Application Administrator can manage application credentials.
This is important because controlling application credentials can potentially allow the administrator to act as the application and inherit permissions assigned to that application.
For example:
Application
    ↓
Application Credentials
    ↓
Application Permissions
If someone can control the application’s credentials, they may be able to authenticate as that application.
Key Concept
Application Administrator = Manage Applications
 
⸻
 
What Cannot an Application Administrator Do?
An Application Administrator cannot grant Microsoft Graph application permissions that require a higher level of privilege.
For such privileged permission grants, a sufficiently privileged administrator such as a Global Administrator may be required.
 
⸻
 
Typical Use Cases
Application Administrators commonly manage:
* App registrations
* Enterprise applications
* SAML integrations
* OIDC integrations
* Application Proxy
* Service principals
* Application credentials
 
⸻
 
3. Application Developer ⭐
Purpose
The Application Developer role allows users to create and manage applications they own.
Can Do
* Create application registrations
* Create service principals
* Create OAuth permission grants
* Become an owner of applications they create
Important Exam Point
The key difference is:
Application Developer
        ↓
Creates + Owns Applications
while:
Application Administrator
        ↓
Manages Applications
Easy Memory Trick
Developer = Creates Apps
Administrator = Manages Apps
 
⸻
 
Application Administrator vs Application Developer
Role	Main Responsibility
Application Administrator	Manage applications across the directory
Application Developer	Create and manage applications they own
Exam Shortcut
If the question says:
“Create application registrations”
Think:
Application Developer
If it says:
“Manage all applications”
Think:
Application Administrator
 
⸻
 
Custom Security Attributes
Microsoft Entra ID supports Custom Security Attributes.
These allow organizations to add additional business or security-related information to supported identity objects.
Examples:
Department = Finance
Sensitivity = High
Region = EU
They can be associated with supported objects such as:
* Users
* Devices
* Service principals
* Managed identities
 
⸻
 
4. Attribute Assignment Administrator
Purpose
The Attribute Assignment Administrator manages the assignment of custom security attributes.
Can Do
* Read custom security attributes
* Assign custom security attributes
* Modify custom security attributes
For supported objects such as:
* Users
* Devices
* Service principals
* Managed identities
Example
The administrator can assign:
Sensitivity = Confidential
to a supported user or other supported object.
Memory Trick
Assignment Administrator = Assigns Attribute Values
 
⸻
 
5. Attribute Assignment Reader
Purpose
The Attribute Assignment Reader provides read access to custom security attributes.
Can Do
* Read custom security attributes
Cannot Do
* Modify attributes
* Assign attributes
Memory Trick
Assignment Reader
        ↓
Read
        ↓
No Changes
 
⸻
 
6. Attribute Definition Administrator
Purpose
The Attribute Definition Administrator manages the definitions of custom security attributes.
Can Do
* Create attribute sets
* Create attribute definitions
* Modify definitions
* Activate attributes
* Deactivate attributes
Example
Create definitions such as:
Region
BusinessUnit
SecurityClassification
Important Distinction
This role manages the definition of an attribute.
It is different from assigning an attribute value to a user.
Attribute Definition Administrator
        ↓
Creates / Manages Attribute Definitions

Attribute Assignment Administrator
        ↓
Assigns Attribute Values
 
⸻
 
7. Attribute Definition Reader
Purpose
Provides read-only access to custom security attribute definitions.
Can Do
* Read attribute definitions
Cannot Do
* Create definitions
* Modify definitions
* Delete definitions
Memory Trick
Definition Reader = Read Definitions Only
 
⸻
 
8. Attribute Log Administrator
Purpose
The Attribute Log Administrator is used to audit and monitor changes related to custom security attributes.
Can Do
* Read custom security attribute audit logs
* Configure diagnostic settings
* Monitor attribute changes
Cannot Do
* Read unrelated Azure audit logs simply because of this role
Memory Trick
Attribute Log Administrator = Manage Attribute Audit Logging
 
⸻
 
9. Attribute Log Reader
Purpose
Provides read-only access to audit logs related to custom security attributes.
Can Do
* Read custom security attribute audit logs
Cannot Do
* Configure diagnostic settings
* Manage logs
Memory Trick
Attribute Log Reader
        ↓
Read Logs

Attribute Log Administrator
        ↓
Manage / Configure Attribute Logging
 
⸻
 
10. Authentication Administrator ⭐
Purpose
The Authentication Administrator manages authentication methods and certain authentication-related operations for users.
Can Do
* Reset passwords
* Manage authentication methods
* Reset MFA registration
* Revoke MFA sessions
* Force authentication re-registration
* Restore deleted users
* Disable users
* Enable users
* Invalidate refresh tokens
* Create support tickets
 
⸻
 
Important Exam Point ⚠️
Authentication Administrators can perform sensitive credential operations on applicable users.
Examples include resetting or managing:
* Microsoft Authenticator
* FIDO2 authentication
* Phone authentication
* Passwords
 
⸻
 
Cannot Do
An Authentication Administrator does not manage tenant-wide authentication policies.
For example, it does not generally configure:
* Authentication Method Policies
* MFA policies
* Password Protection policies
* Hardware OATH token management
Those responsibilities belong to more specialized roles.
 
⸻
 
11. Authentication Policy Administrator
Purpose
The Authentication Policy Administrator manages authentication policies across the tenant.
Can Do
* Manage Authentication Methods Policy
* Configure MFA settings
* Manage Password Protection
* Configure Smart Lockout
* Manage custom banned passwords
* Manage supported Verified ID / verifiable credential configuration
* Create support tickets
 
⸻
 
Example
An administrator wants to configure:
Microsoft Authenticator → Allowed
FIDO2                 → Allowed
SMS                   → Disabled
This is a policy-level task.
Therefore, think:
Authentication Policy Administrator
 
⸻
 
Cannot Do
This role does not primarily manage individual user credentials.
For example, it does not:
* Reset user passwords
* Restore users
* Delete users
* Perform sensitive user authentication operations
 
⸻
 
Authentication Administrator vs Authentication Policy Administrator
This is one of the most important distinctions to memorize.
Role	Main Responsibility
Authentication Administrator	Manage authentication for users
Authentication Policy Administrator	Manage authentication policies
Easy Memory Trick
Authentication Administrator
        ↓
USERS

Authentication Policy Administrator
        ↓
POLICIES
 
⸻
 
12. Privileged Authentication Administrator
The Privileged Authentication Administrator provides a higher level of authentication administration.
It can manage authentication methods and credentials for a broader range of users, including highly privileged users.
Think:
Authentication Administrator
        ↓
User Authentication

Privileged Authentication Administrator
        ↓
Privileged / Broader Authentication Management
Exam Tip
When a question involves managing authentication information for all users or highly privileged users, consider the Privileged Authentication Administrator.
 
⸻
 
13. User Administrator
Purpose
The User Administrator manages users and many user-related administrative tasks.
Can Do
* Create users
* Delete users
* Restore users
* Update user properties
* Manage certain user-related settings
Important Distinction
The User Administrator is primarily focused on user management, not tenant-wide authentication policy configuration.
Memory Trick
User Administrator = Manage Users
 
⸻
 
Authentication Roles Comparison
Role	Users	Authentication Methods	Authentication Policies
User Administrator	✅	Limited	❌
Authentication Administrator	✅	✅	❌
Privileged Authentication Administrator	✅	✅ Broad / privileged	❌
Authentication Policy Administrator	❌	Policy-level	✅
 
⸻
 
Quick Exam Scenarios
Scenario 1
A user needs to reset passwords for employees.
Answer
Authentication Administrator
Think:
User Credential Operation
        ↓
Authentication Administrator
 
⸻
 
Scenario 2
An administrator needs to configure MFA policy for the tenant.
Answer
Authentication Policy Administrator
Think:
Tenant Authentication Policy
        ↓
Authentication Policy Administrator
 
⸻
 
Scenario 3
An administrator needs to manage application registrations and enterprise applications.
Answer
Application Administrator
 
⸻
 
Scenario 4
A developer needs to create application registrations and manage applications they own.
Answer
Application Developer
 
⸻
 
Scenario 5
An administrator needs to assign custom security attributes.
Answer
Attribute Assignment Administrator
 
⸻
 
Scenario 6
An administrator needs to create custom security attribute definitions.
Answer
Attribute Definition Administrator
 
⸻
 
Scenario 7
An administrator only needs to read custom security attribute audit logs.
Answer
Attribute Log Reader
 
⸻
 
Scenario 8
An administrator needs to configure authentication methods for the entire tenant.
Answer
Authentication Policy Administrator
 
⸻
 
Most Important Roles to Remember
Global Administrator
    ↓
Broad / Full Administrative Control

Application Administrator
    ↓
Manages Applications

Application Developer
    ↓
Creates + Owns Applications

Authentication Administrator
    ↓
Manages User Authentication

Authentication Policy Administrator
    ↓
Manages Authentication Policies

Privileged Authentication Administrator
    ↓
Privileged Authentication Management

User Administrator
    ↓
Manages Users

Attribute Assignment Administrator
    ↓
Assigns Custom Security Attributes

Attribute Definition Administrator
    ↓
Creates / Manages Attribute Definitions

Attribute Log Reader
    ↓
Reads Attribute Audit Logs
 
⸻
 
Golden Rules
Rule 1 — Applications
Application Developer
        ↓
Creates Applications

Application Administrator
        ↓
Manages Applications
 
⸻
 
Rule 2 — Authentication
Authentication Administrator
        ↓
Manages USER Authentication

Authentication Policy Administrator
        ↓
Manages AUTHENTICATION POLICIES
 
⸻
 
Rule 3 — Custom Security Attributes
Attribute Assignment Administrator
        ↓
Assigns Attribute Values

Attribute Definition Administrator
        ↓
Creates Attribute Definitions

Attribute Assignment Reader
        ↓
Reads Assigned Attributes

Attribute Definition Reader
        ↓
Reads Attribute Definitions

Attribute Log Administrator
        ↓
Manages Attribute Audit Logging

Attribute Log Reader
        ↓
Reads Attribute Audit Logs
 
⸻
 
Microsoft Entra Roles — Quick Reference
Role	Main Purpose
Global Administrator	Broad administrative control
User Administrator	Manage users
Application Administrator	Manage applications
Application Developer	Create/manage owned applications
Authentication Administrator	Manage user authentication
Privileged Authentication Administrator	Manage privileged authentication
Authentication Policy Administrator	Manage authentication policies
Attribute Assignment Administrator	Assign custom security attributes
Attribute Assignment Reader	Read custom security attributes
Attribute Definition Administrator	Create/manage attribute definitions
Attribute Definition Reader	Read attribute definitions
Attribute Log Administrator	Manage attribute audit logging
Attribute Log Reader	Read attribute audit logs
 
⸻
 
Exam Memory Formula
APPLICATIONS
Developer → Create
Administrator → Manage
AUTHENTICATION
Authentication Administrator → Users
Policy Administrator → Policies
Privileged Authentication Administrator → Privileged Users
ATTRIBUTES
Assignment Administrator → Assign
Assignment Reader → Read Assigned Attributes

Definition Administrator → Define
Definition Reader → Read Definitions

Log Administrator → Manage Logs
Log Reader → Read Logs
 
⸻
 
Final Mental Model
When you see a Microsoft Entra built-in role question, identify what the administrator needs to manage.
Need to manage users?
        ↓
User Administrator

Need to manage user authentication?
        ↓
Authentication Administrator

Need to manage authentication policies?
        ↓
Authentication Policy Administrator

Need to create applications?
        ↓
Application Developer

Need to manage applications?
        ↓
Application Administrator

Need to assign custom security attributes?
        ↓
Attribute Assignment Administrator

Need to create attribute definitions?
        ↓
Attribute Definition Administrator

Need to read attribute logs?
        ↓
Attribute Log Reader

Need broad Entra administrative control?
        ↓
Global Administrator
One-Line Summary
Microsoft Entra built-in roles provide specialized administrative permissions for identity, users, applications, authentication, and directory resources. Choose the least privileged role that can perform the required task.
