Azure Role-Based Access Control (Azure RBAC)

What Is Azure RBAC?

Azure Role-Based Access Control (Azure RBAC) is Azure’s authorization system for controlling access to Azure resources.

It determines:

* Who can access a resource
* What they can do
* Where they can do it

Simple Definition

Azure RBAC = Who + What + Where

Who
↓
Security Principal
What
↓
Role Definition
Where
↓
Scope
        ↓
Role Assignment

⸻

Why Do We Use Azure RBAC?

Organizations rarely want every user to have full access to Azure.

For example:

* A VM administrator should manage Virtual Machines.
* A network administrator should manage Virtual Networks.
* A DBA should manage SQL resources.
* A developer may need access only to a specific Resource Group.
* An application may need access to Azure resources.
* A security team may need read-only access.

Azure RBAC allows organizations to follow the principle of least privilege.

Give users and applications only the permissions they actually need.

⸻

Azure RBAC vs Microsoft Entra Roles

This is an important distinction.

Microsoft Entra Roles

Control access to Microsoft Entra ID and identity-related administrative functions.

Examples:

* Global Administrator
* User Administrator
* Security Administrator

Azure RBAC

Controls access to Azure resources.

Examples:

* Virtual Machines
* Storage Accounts
* Virtual Networks
* SQL Databases
* Resource Groups

Easy Memory Trick

Microsoft Entra Roles
        ↓
Identity / Directory
Azure RBAC
        ↓
Azure Resources

⸻

Core RBAC Components

Azure RBAC is based on three key elements:

Security Principal
        +
Role Definition
        +
Scope
        =
Role Assignment

Let’s examine each one.

⸻

1. Security Principal

What Is a Security Principal?

A security principal is the identity that receives permissions.

It can be:

* User
* Group
* Service principal
* Managed identity

⸻

User

Example:

rasha@contoso.com

You can assign an Azure role directly to the user.

Example:

Rasha
+
Reader
+
Subscription

Result:

Rasha can read resources within that subscription, subject to other access controls.

⸻

Group

Instead of assigning permissions individually:

User A → Contributor
User B → Contributor
User C → Contributor

you can assign the role to a group:

IT Administrators
        ↓
    Contributor

Then users become members of the group.

Benefit

Group-based assignments make access management easier and more scalable.

⸻

Service Principal

A service principal is an identity used by an application or service to access Azure resources.

Example:

Azure DevOps Pipeline
        ↓
Service Principal
        ↓
Azure Resource

Instead of giving the application a human user’s credentials, the application can use its own identity.

⸻

Managed Identity

A managed identity is an identity managed by Azure for an Azure resource.

Example:

Virtual Machine
      ↓
Managed Identity
      ↓
Azure Key Vault

The VM can authenticate to Azure services without you having to store a password or secret in the application.

⸻

2. Role Definition

What Is a Role Definition?

A role definition is a collection of permissions.

It specifies which operations an identity can perform.

Examples of operations include:

* Read
* Write
* Delete
* Create

⸻

Built-In Roles

Azure provides many built-in roles.

The three most important beginner roles are:

Owner

Owner provides full management access to Azure resources, including the ability to assign Azure RBAC roles.

Owner
├── Read
├── Create
├── Modify
├── Delete
└── Assign Access

⸻

Contributor

Contributor can manage Azure resources but cannot assign Azure RBAC access to others.

Contributor
├── Read
├── Create
├── Modify
└── Delete
❌ Cannot assign Azure RBAC roles

⸻

Reader

Reader provides read-only access.

Reader
└── View resources
❌ Create
❌ Modify
❌ Delete
❌ Assign access

⸻

Important Comparison

Role	View	Create	Modify	Delete	Assign Azure RBAC
Owner	✅	✅	✅	✅	✅
Contributor	✅	✅	✅	✅	❌
Reader	✅	❌	❌	❌	❌

Easy Memory Trick

Owner
↓
Manage + Assign Access
Contributor
↓
Manage
Reader
↓
View

⸻

Specialized Roles

Azure also provides specialized built-in roles.

Examples include:

* Virtual Machine Contributor
* Storage Blob Data Reader
* Storage Blob Data Contributor
* SQL-related roles
* Network Contributor

These roles provide more targeted permissions.

For example:

Network Contributor
        ↓
Manage Azure networking resources

This is often better than giving someone broad Contributor access across an entire subscription.

⸻

Custom Roles

Sometimes built-in roles don’t provide exactly the permissions an organization needs.

In that situation, an organization can create a custom Azure RBAC role.

Example:

Custom VM Operator
Allowed:
✅ Start VM
✅ Restart VM
✅ Read VM
Not allowed:
❌ Delete VM
❌ Change networking
❌ Assign permissions

Custom roles help organizations implement more precise least-privilege access.

⸻

3. Scope

What Is Scope?

Scope determines where a role assignment applies.

Azure RBAC supports four major scopes:

Management Group
       ↓
Subscription
       ↓
Resource Group
       ↓
Resource

⸻

1. Management Group

The highest common Azure RBAC scope in this hierarchy.

A role assignment here can apply to subscriptions and resources underneath the management group.

⸻

2. Subscription

A subscription can contain many Resource Groups and resources.

Example:

Subscription
├── Resource Group A
├── Resource Group B
└── Resource Group C

Assigning a role at subscription scope can affect resources beneath that subscription.

⸻

3. Resource Group

A Resource Group contains Azure resources.

Example:

Resource Group: Production
├── VM
├── Storage Account
├── Network Interface
└── Public IP

Assigning:

Contributor
+
Production Resource Group

allows the principal to manage applicable resources within that scope.

⸻

4. Resource

The most specific scope.

Example:

Virtual Machine: WebServer01

You can assign a role directly to that individual resource.

⸻

Scope Hierarchy

Remember:

Management Group
       ↓
Subscription
       ↓
Resource Group
       ↓
Resource

Easy Memory Trick

The higher the scope, the broader the potential access.

⸻

Role Assignment

A role assignment connects:

WHO
+
WHAT
+
WHERE

Example:

IT Administrators
        +
Contributor
        +
Production Resource Group

Result:

Members of the IT Administrators group can manage applicable resources within the Production Resource Group.

⸻

Role Assignment Example

Suppose we have:

User:
Rasha
Role:
Reader
Scope:
Production Resource Group

The effective assignment is:

Rasha
 ↓
Reader
 ↓
Production Resource Group

Rasha can view applicable resources in that Resource Group but cannot modify them.

⸻

Role Inheritance

Permissions assigned at a higher scope are inherited by lower scopes.

Example:

Subscription
     ↓
Resource Group
     ↓
Virtual Machine

If a user receives:

Reader
+
Subscription

the Reader permission can apply to resources within that subscription.

Example

Reader
  ↓
Subscription
  ↓
Resource Group A
  ↓
VM01

The user can read the applicable resources underneath the subscription.

⸻

More Specific Scope

You can also assign a role at a more specific scope.

Example:

Subscription
      ↓
Resource Group A
      ↓
VM01

If someone receives:

Contributor
+
VM01

their Contributor assignment applies specifically to that VM rather than the entire subscription.

⸻

Azure RBAC Is Additive

Azure RBAC permissions can come from multiple role assignments.

Example:

Subscription
    ↓
Contributor
Resource Group
    ↓
Reader

The user’s effective permissions are based on the applicable role assignments.

The additional Reader assignment does not remove Contributor permissions.

Important

Azure RBAC is generally additive.

Multiple applicable Allow role assignments are combined.

⸻

Example of Multiple Role Assignments

Suppose Ahmed has:

Reader
+
Subscription

and:

Contributor
+
Development Resource Group

Ahmed has:

* Reader access across the subscription
* Contributor access within the Development Resource Group

Therefore:

Development Resource Group
        ↓
Contributor
Other Resources
        ↓
Reader

⸻

Actions vs. DataActions

This is an important Azure RBAC exam concept.

Azure RBAC distinguishes between management-plane operations and data-plane operations.

⸻

Actions

Actions represent management operations on Azure resources.

Examples:

* Create a Virtual Machine
* Delete a Virtual Machine
* Update a Storage Account
* Create a Network Interface

Think:

Managing the Azure resource itself.

⸻

DataActions

DataActions represent operations against the actual data inside a resource.

Examples:

* Read a Blob
* Write a Blob
* Read queue messages
* Access data stored in an Azure service

Think:

Accessing the data inside the resource.

⸻

Actions vs. DataActions

Management Plane
       ↓
Actions
       ↓
Manage Azure Resources
Data Plane
       ↓
DataActions
       ↓
Access Data

Example

A user might be able to:

Manage Storage Account

without necessarily being able to:

Read Blob Data

These are different permissions.

⸻

NotActions and NotDataActions

Role definitions can also contain exclusions.

Conceptually:

Actions
-
NotActions
=
Applicable Management Permissions

And:

DataActions
-
NotDataActions
=
Applicable Data Permissions

Important

NotActions does not mean “deny assignment.”

It defines exclusions from the actions granted by that role definition.

⸻

Deny Assignments

Azure also supports Deny assignments.

A Deny assignment can prevent access even when an Allow role assignment would otherwise grant that permission.

Conceptually:

Allow
+
Deny
=
Access Denied

Easy Memory Trick

Deny takes precedence over Allow.

However, Azure deny assignments have specific behavior and are not something administrators typically create in the same way as normal role assignments.

⸻

RBAC Evaluation

When a user attempts to access an Azure resource, Azure evaluates the request against the applicable authorization information.

A simplified model is:

User
 ↓
Authentication
 ↓
Azure Resource Manager
 ↓
Identify applicable role assignments
 ↓
Evaluate applicable permissions
 ↓
Evaluate deny conditions
 ↓
Evaluate conditions where applicable
 ↓
Allow or Deny

⸻

Step-by-Step Example

Rasha wants to delete a VM.

Step 1

Rasha authenticates.

Rasha
 ↓
Microsoft Entra ID
 ↓
Authenticated

Step 2

She sends a request to Azure Resource Manager.

Delete VM

Step 3

Azure determines her applicable role assignments.

For example:

Contributor
+
Production Resource Group

Step 4

Azure checks whether the requested operation is allowed.

Contributor normally allows resource deletion.

Step 5

Azure evaluates other applicable authorization controls, including any relevant deny assignments or conditions.

Step 6

The request is either:

✅ Allowed

or:

❌ Denied

⸻

Azure RBAC and Authentication

Remember that Azure RBAC is primarily about authorization, not authentication.

Authentication
↓
Who are you?
Authorization
↓
What can you do?

Microsoft Entra ID is responsible for identity and authentication.

Azure RBAC determines what authenticated identities can do to Azure resources.

⸻

Example: Complete Flow

Rasha
 ↓
Microsoft Entra Authentication
 ↓
Identity Confirmed
 ↓
Azure Request
 ↓
Azure RBAC
 ↓
Who?
Rasha
What?
Contributor
Where?
Production Resource Group
 ↓
Authorization Decision
 ↓
Access Granted / Denied

⸻

RBAC and Groups

Using groups is a common best practice.

Instead of:

Rasha → Contributor
Ahmed → Contributor
Sara  → Contributor
Omar  → Contributor

use:

IT Administrators
       ↓
Contributor
       ↓
Production Resource Group

Then manage membership separately.

Benefits

* Easier administration
* Better scalability
* Easier onboarding/offboarding
* Less individual role assignment management
* Better access governance

⸻

RBAC and Managed Identities

Applications and Azure resources can also receive RBAC permissions.

Example:

Azure VM
   ↓
Managed Identity
   ↓
Reader
   ↓
Storage Account

The VM can use its managed identity to authenticate to Azure and request the permissions granted through Azure RBAC.

This avoids embedding credentials in application code.

⸻

RBAC and Service Principals

Applications can also use service principals.

Example:

Azure DevOps
     ↓
Service Principal
     ↓
Contributor
     ↓
Resource Group

The pipeline can then perform the operations allowed by its role assignment.

Security Best Practice

Avoid giving automation accounts broad permissions such as subscription-level Owner unless there is a strong, documented requirement.

Use the smallest scope and role that supports the workload.

⸻

Least Privilege

One of the most important RBAC security principles is:

Give the minimum permissions required to perform the job.

Instead of:

Developer
 ↓
Owner
 ↓
Entire Subscription

consider:

Developer
 ↓
Specific Role
 ↓
Specific Resource Group

or even:

Developer
 ↓
Specific Resource

when appropriate.

⸻

Common Built-In Roles

Role	Main Purpose
Owner	Full resource management + Azure RBAC access assignment
Contributor	Manage resources but cannot assign Azure RBAC access
Reader	Read-only access
User Access Administrator	Manage user access to Azure resources
Specialized roles	Manage specific Azure services or data

⸻

Owner vs Contributor

This is one of the most common exam questions.

Owner

Manage Resources
+
Assign Azure RBAC Access

Contributor

Manage Resources
-
Assign Azure RBAC Access

Memory Trick

Owner = Contributor + Access Management

⸻

Reader

Reader is straightforward:

Reader
 ↓
View

The user can inspect resources but cannot normally:

* Create resources
* Modify resources
* Delete resources
* Assign Azure RBAC permissions

⸻

Azure RBAC vs Azure Policy

These are often confused.

Azure RBAC

Answers:

Who is allowed to perform an action?

Example:

Can Ahmed delete this VM?

⸻

Azure Policy

Answers:

Is this resource configuration compliant with organizational rules?

Example:

Only allow resources in approved regions.

Easy Memory Trick

RBAC
↓
Who can do it?
Azure Policy
↓
What is allowed / compliant?

⸻

Azure RBAC vs Microsoft Entra Roles

Another important comparison:

Technology	Controls
Microsoft Entra Roles	Identity and directory administration
Azure RBAC	Azure resource authorization
Azure Policy	Resource compliance and configuration

Example:

Global Administrator
        ↓
Microsoft Entra / Identity
Owner
        ↓
Azure Resource Access
Azure Policy
        ↓
Resource Compliance

⸻

Exam Tips

What is Azure RBAC?

Azure’s authorization system for managing access to Azure resources.

⸻

What are the three components of a role assignment?

Security Principal
Role Definition
Scope

⸻

What does Security Principal mean?

The identity receiving the permissions.

Examples:

* User
* Group
* Service principal
* Managed identity

⸻

What is a Role Definition?

A collection of permissions that specifies what operations can be performed.

⸻

What is Scope?

The level at which a role assignment applies.

⸻

What are the four main Azure RBAC scopes?

Management Group
Subscription
Resource Group
Resource

⸻

Which role has full management access and can assign Azure RBAC permissions?

Owner

⸻

Which role can manage resources but cannot assign Azure RBAC access?

Contributor

⸻

Which role is read-only?

Reader

⸻

Is Azure RBAC additive?

Yes, applicable Allow permissions from multiple assignments are combined.

⸻

What takes precedence when a relevant Deny assignment applies?

Deny takes precedence over Allow.

⸻

What is the difference between Actions and DataActions?

Actions control management operations on Azure resources.

DataActions control access to data within supported Azure resources.

⸻

Quick Memory Formula

Azure RBAC
=
WHO
+
WHAT
+
WHERE
WHO
↓
Security Principal
WHAT
↓
Role Definition
WHERE
↓
Scope

⸻

Scope Memory Trick

Management Group
        ↓
Subscription
        ↓
Resource Group
        ↓
Resource

Higher scope = broader potential access.

⸻

Role Memory Trick

Owner
↓
Manage + Assign Access
Contributor
↓
Manage
Reader
↓
View

⸻

Final Mental Model

When you see an Azure RBAC question, ask three things:

1. WHO?

Who receives the permissions?

User
Group
Service Principal
Managed Identity

2. WHAT?

What can they do?

Reader
Contributor
Owner
Custom Role
Specialized Role

3. WHERE?

Where does the permission apply?

Management Group
Subscription
Resource Group
Resource

Then remember:

WHO + WHAT + WHERE
        ↓
   Role Assignment
        ↓
   Authorization

⸻

Final One-Line Summary

Azure RBAC is Azure’s authorization system that uses security principals, role definitions, and scopes to determine who can perform which actions on which Azure resources.#