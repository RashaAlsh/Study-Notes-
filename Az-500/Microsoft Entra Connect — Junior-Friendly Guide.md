Microsoft Entra Connect — Junior-Friendly Guide

What Is Microsoft Entra Connect?

Microsoft Entra Connect is a Microsoft tool used to connect an organization’s on-premises Active Directory Domain Services (AD DS) environment with Microsoft Entra ID.

It is commonly used to build a hybrid identity environment, where users and identity information exist across on-premises and cloud environments.

Simple Definition

Think of Microsoft Entra Connect as a bridge between on-premises Active Directory and Microsoft Entra ID.

On-Premises Active Directory
          ↕
Microsoft Entra Connect
          ↕
Microsoft Entra ID
          ↓
Microsoft 365 / Cloud Applications

This allows organizations to synchronize identities between their local Active Directory environment and Microsoft Entra ID.

⸻

Why Do Companies Use Microsoft Entra Connect?

Many organizations already have an on-premises Active Directory environment.

For example:

Company
  ↓
On-Premises Active Directory
  ↓
Users + Groups + Computers

At the same time, the organization may use:

* Microsoft 365
* Exchange Online
* SharePoint Online
* Microsoft Teams
* Azure
* Other cloud applications

Microsoft Entra Connect helps connect the organization’s existing identity infrastructure with Microsoft Entra ID.

⸻

Main Benefits

Microsoft Entra Connect can provide:

* Hybrid identity
* User synchronization
* Group synchronization
* Password hash synchronization
* Pass-through authentication
* Integration with federation scenarios
* Centralized identity management across environments

Simple Idea

Instead of maintaining completely separate cloud identities, organizations can synchronize identity information from their existing Active Directory environment.

⸻

What Is Hybrid Identity?

Hybrid identity means an organization uses both:

On-Premises Identity
        +
Cloud Identity

For example:

On-Premises AD DS
        ↕
Microsoft Entra Connect
        ↕
Microsoft Entra ID
        ↓
Microsoft 365

Example

A company has an employee:

john@contoso.com

John has an identity in the organization’s on-premises Active Directory.

The organization synchronizes that identity to Microsoft Entra ID.

John can then use the organizational identity to access supported cloud services.

⸻

Important Microsoft Entra Connect Features

1. Password Hash Synchronization (PHS)

Password Hash Synchronization (PHS) synchronizes a representation of the user’s on-premises password credential to Microsoft Entra ID.

The actual plaintext password is not synchronized.

Simplified Flow

On-Premises Password
        ↓
Password Hash Processing
        ↓
Microsoft Entra ID

When PHS is used, Microsoft Entra ID can authenticate the user in the cloud without contacting the on-premises domain controller for every cloud sign-in.

Why Is PHS Important?

PHS is generally considered one of the simplest ways to provide hybrid identity.

It can help provide:

* Cloud authentication
* Simplified deployment
* Reduced infrastructure requirements
* Identity synchronization

Easy Way to Remember

PHS = Synchronize password hash information for cloud authentication.

⸻

2. Pass-Through Authentication (PTA)

Pass-Through Authentication (PTA) allows users to authenticate using their on-premises Active Directory credentials while Microsoft Entra ID works with on-premises authentication agents to validate the credentials.

Simplified Flow

User
  ↓
Microsoft Entra ID
  ↓
Authentication request
  ↓
On-Premises Authentication Agent
  ↓
On-Premises Active Directory
  ↓
Authentication result

The user’s password does not need to be stored as a password hash in Microsoft Entra ID for cloud authentication in the same way as PHS.

Important

PTA does not mean that Microsoft Entra ID directly sends the user’s password to a domain controller.

The authentication is handled through the appropriate on-premises authentication agent.

Easy Way to Remember

PTA = Authentication is validated against on-premises Active Directory.

⸻

PHS vs. PTA

This is a common exam topic.

Feature	PHS	PTA
Password hash synchronized to Entra ID	Yes	No
Authentication depends on on-premises authentication agent	No	Yes
Cloud authentication can continue if on-premises authentication infrastructure is unavailable	Generally yes	No
Infrastructure complexity	Lower	Higher
Common use	Simple hybrid authentication	Organizations requiring on-premises password validation

Easy Memory Trick

PHS → Hash goes to the cloud
PTA → Authentication goes to on-premises

⸻

3. Federation Integration

Microsoft Entra Connect can be used in environments that integrate with Active Directory Federation Services (AD FS).

Federation allows authentication to be handled by a federation service.

Simplified Flow

User
  ↓
Microsoft Entra ID
  ↓
Federation
  ↓
AD FS
  ↓
On-Premises Active Directory

AD FS can provide federated authentication for supported scenarios.

Important

Federation is generally more complex than PHS or PTA because it can require additional infrastructure and management.

Organizations may need to manage:

* AD FS servers
* Federation configuration
* Certificates
* Availability
* Load balancing
* Monitoring

Easy Way to Remember

Federation = Authentication handled through a federation service such as AD FS.

⸻

PHS vs. PTA vs. Federation

Method	Main Idea
PHS	Synchronize password hash information and authenticate in the cloud
PTA	Validate authentication against on-premises AD through authentication agents
Federation	Delegate authentication to a federation service such as AD FS

Simple Mental Model

PHS
Password Hash
     ↓
Cloud Authentication
PTA
Authentication
     ↓
On-Premises AD
Federation
Authentication
     ↓
AD FS

⸻

4. Directory Synchronization

Microsoft Entra Connect can synchronize identity objects from on-premises Active Directory to Microsoft Entra ID.

Common objects include:

* Users
* Groups
* Contacts
* Certain directory attributes

Example

On-Premises AD
Users
Groups
Contacts
Attributes
   ↓
Microsoft Entra Connect
   ↓
Microsoft Entra ID

Important

Synchronization is not simply a complete copy of Active Directory.

Administrators configure synchronization rules and scopes to determine which objects and attributes are synchronized.

⸻

What Happens During Synchronization?

Imagine an employee is created in on-premises Active Directory.

New Employee
     ↓
AD DS User Created
     ↓
Microsoft Entra Connect
     ↓
Synchronization
     ↓
Microsoft Entra ID
     ↓
Cloud Services

The synchronized identity can then be used for supported Microsoft cloud services.

⸻

5. Microsoft Entra Connect Health

Microsoft Entra Connect Health is a monitoring capability for hybrid identity infrastructure.

It helps administrators monitor the health of components involved in hybrid identity.

Depending on the environment, this can include:

* Microsoft Entra Connect Sync
* AD FS
* Active Directory Domain Services-related monitoring scenarios

Simple Definition

Microsoft Entra Connect = Connect and synchronize identities

Microsoft Entra Connect Health = Monitor the health of identity infrastructure

⸻

What Does Microsoft Entra Connect Health Provide?

It can provide information such as:

* Alerts
* Health status
* Server information
* Synchronization monitoring
* Performance information
* Usage and activity information for supported components

The information can be viewed through the Microsoft Entra administrative experience.

⸻

Microsoft Entra Connect Health Agents

Microsoft Entra Connect Health uses agents installed on supported servers to collect health information.

These agents communicate information about the monitored identity infrastructure to the Microsoft Entra service.

Simplified Architecture

On-Premises Server
       ↓
Health Agent
       ↓
Microsoft Entra
       ↓
Health Monitoring
       ↓
Admin Center

⸻

Health Monitoring Example

Imagine an organization has:

AD FS Server 1
AD FS Server 2
Microsoft Entra Connect Server

Connect Health can help administrators monitor the health of supported components.

If a problem occurs, administrators may receive an alert so they can investigate.

⸻

Why Is Health Monitoring Important?

Hybrid identity is business-critical.

If synchronization or authentication infrastructure fails, users may experience problems accessing cloud services.

For example:

AD DS
  ↓
Entra Connect
  ↓
Synchronization Problem
  ↓
Cloud Identity Not Updated
  ↓
User Access Problems

Monitoring helps administrators detect problems earlier.

⸻

Key Benefits of Microsoft Entra Connect Health

1. Health Monitoring

Provides visibility into supported hybrid identity infrastructure.

⸻

2. Alerts

Helps administrators identify issues that require attention.

Examples may include:

* Synchronization problems
* Authentication problems
* Service health issues
* Configuration-related issues

⸻

3. Centralized Visibility

Administrators can monitor supported identity components through the Microsoft Entra administrative experience.

⸻

4. Performance and Usage Information

For supported components, Connect Health can provide information that helps administrators understand:

* Authentication activity
* Server health
* Usage patterns
* Performance

⸻

Microsoft Entra Connect vs. Microsoft Entra Connect Health

This distinction is extremely important.

Microsoft Entra Connect

Main purpose:

Synchronize identities between on-premises Active Directory and Microsoft Entra ID.

Think:

Connect = Synchronize

⸻

Microsoft Entra Connect Health

Main purpose:

Monitor the health of supported hybrid identity infrastructure.

Think:

Health = Monitor

⸻

Side-by-Side Comparison

Feature	Entra Connect	Entra Connect Health
Identity synchronization	✅	❌
User synchronization	✅	❌
Group synchronization	✅	❌
Password Hash Synchronization	✅	❌
Pass-Through Authentication integration	✅	❌
Federation integration	✅	❌
Health monitoring	Limited/operational role	✅
Alerts	Operational information	✅
Server health	❌	✅
Identity infrastructure monitoring	❌	✅

⸻

Real-World Example

Imagine a company called Contoso.

The company has:

500 Employees
        ↓
On-Premises Active Directory
        ↓
Microsoft Entra Connect
        ↓
Microsoft Entra ID
        ↓
Microsoft 365

Step 1 — Create User

An administrator creates:

john@contoso.com

in on-premises Active Directory.

Step 2 — Synchronization

Microsoft Entra Connect synchronizes the identity to Microsoft Entra ID.

Step 3 — Cloud Access

John can use the synchronized identity for supported Microsoft cloud services.

Step 4 — Monitoring

Microsoft Entra Connect Health monitors supported hybrid identity components.

AD DS
  ↓
Entra Connect
  ↓
Microsoft Entra ID
  ↓
Microsoft 365
       +
Entra Connect Health
       ↓
Monitoring + Alerts

⸻

Common Troubleshooting Scenario

Suppose a user says:

“My account was created yesterday, but I cannot see it in Microsoft Entra ID.”

A junior administrator should think about synchronization.

Possible Investigation Path

Was the user created in AD DS?
        ↓
Is the user inside the synchronization scope?
        ↓
Did synchronization run?
        ↓
Are there synchronization errors?
        ↓
Is Microsoft Entra Connect healthy?
        ↓
Does the user appear in Entra ID?

This is why understanding Connect + Connect Health is important for hybrid environments.

⸻

Security Considerations

Microsoft Entra Connect is an important part of the organization’s identity infrastructure.

Best practices include:

* Keep the server secure
* Restrict administrative access
* Keep software updated
* Monitor synchronization health
* Monitor authentication infrastructure
* Use least privilege
* Protect privileged accounts with MFA
* Regularly review synchronization configuration
* Monitor alerts

⸻

Exam Tips

Microsoft Entra Connect

Remember:

Hybrid Identity
Users
Groups
Synchronization
PHS
PTA
Federation

Main Question

What connects on-premises AD DS with Microsoft Entra ID?

Microsoft Entra Connect

⸻

Microsoft Entra Connect Health

Remember:

Monitoring
Alerts
Health
Performance
Usage
Hybrid Identity Infrastructure

Main Question

What monitors the health of supported hybrid identity infrastructure?

Microsoft Entra Connect Health

⸻

Common Exam Questions

What is Microsoft Entra Connect?

Microsoft Entra Connect is a Microsoft tool used to integrate on-premises Active Directory with Microsoft Entra ID and synchronize identity information.

⸻

What is hybrid identity?

Hybrid identity is an identity architecture that connects on-premises identity infrastructure with cloud identity services.

⸻

What is Password Hash Synchronization?

PHS synchronizes a representation of the user’s password hash information to Microsoft Entra ID so cloud authentication can occur without requiring every authentication to be validated against on-premises Active Directory.

⸻

What is Pass-Through Authentication?

PTA allows Microsoft Entra authentication requests to be validated against on-premises Active Directory through authentication agents.

⸻

What is federation?

Federation allows authentication to be delegated to a federation service such as AD FS.

⸻

What is Microsoft Entra Connect Health?

It is a monitoring capability that provides health, alerting, and operational information for supported hybrid identity infrastructure.

⸻

What is the difference between Connect and Connect Health?

Connect = Synchronization

Connect Health = Monitoring

⸻

PHS vs. PTA vs. Federation — Quick Revision

PHS
↓
Password hash information synchronized
↓
Cloud authentication
PTA
↓
Authentication request
↓
On-Premises Authentication Agent
↓
On-Premises AD
Federation
↓
Authentication
↓
AD FS
↓
On-Premises AD

⸻

Final Memory Trick

Remember:

Microsoft Entra Connect
        ↓
CONNECT
        ↓
Synchronize
        ↓
Users + Groups + Identity Data

And:

Microsoft Entra Connect Health
        ↓
HEALTH
        ↓
Monitor
        ↓
Alerts + Health + Performance

One-Line Summary

Microsoft Entra Connect connects on-premises Active Directory with Microsoft Entra ID for hybrid identity and synchronization, while Microsoft Entra Connect Health helps monitor the health and operation of supported hybrid identity infrastructure.