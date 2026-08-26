Authentication Options in Microsoft Entra ID

Big Picture

When an organization connects its on-premises Active Directory environment to Microsoft Entra ID, one of the first questions is:

How will users authenticate?

For hybrid identity environments, three important authentication approaches are:

1. Password Hash Synchronization (PHS)
2. Pass-Through Authentication (PTA)
3. Federated Authentication

A good junior-level understanding is to know where authentication is performed, what infrastructure is required, and what happens if the on-premises environment becomes unavailable.

⸻

1. Password Hash Synchronization (PHS)

What Is PHS?

Password Hash Synchronization (PHS) is a Microsoft Entra Connect authentication method that synchronizes a representation of the user’s on-premises password hash information to Microsoft Entra ID.

The user’s plaintext password is not synchronized.

Authentication for cloud services can then be performed by Microsoft Entra ID.

Simple Flow

User
  ↓
Microsoft Entra ID
  ↓
Cloud Authentication
  ↓
Access Granted

The identity information and password hash synchronization are initially sourced from on-premises Active Directory.

⸻

How PHS Works

Suppose Ahmed has an account:

ahmed@contoso.com

His password is managed in the on-premises Active Directory environment.

Microsoft Entra Connect synchronizes the appropriate password hash representation to Microsoft Entra ID.

When Ahmed signs in to a cloud service:

Ahmed
  ↓
Microsoft Entra ID
  ↓
Authentication in the cloud
  ↓
Access

The cloud authentication does not require Microsoft Entra ID to contact an on-premises domain controller for every sign-in.

⸻

Advantages of PHS

PHS is attractive because it is relatively simple to deploy and operate.

Benefits include:

* Simple architecture
* Lower infrastructure requirements
* Cloud-based authentication
* Reduced dependency on on-premises authentication servers
* Good resilience for cloud authentication
* Easier disaster recovery

Easy Way to Remember

PHS = Password hash information is synchronized → Authentication happens in the cloud.

⸻

2. Pass-Through Authentication (PTA)

What Is PTA?

Pass-Through Authentication (PTA) allows users to authenticate with their on-premises Active Directory credentials while Microsoft Entra ID uses Pass-through Authentication agents to validate the credentials against the on-premises Active Directory environment.

Simple Flow

User
  ↓
Microsoft Entra ID
  ↓
PTA Authentication Agent
  ↓
On-Premises Active Directory
  ↓
Authentication Result
  ↓
Microsoft Entra ID

Authentication starts with the cloud service, but credential validation depends on the on-premises environment.

⸻

Why Use PTA?

Organizations may choose PTA when they want authentication to be validated against their on-premises Active Directory environment.

For example, authentication can reflect the current state of the on-premises account.

If an account is:

* Disabled
* Locked
* Invalid according to the on-premises directory

the on-premises authentication process can reject the authentication attempt.

⸻

PTA Infrastructure

PTA requires authentication agents to be deployed on-premises.

Organizations should therefore consider:

* Agent availability
* Server health
* Network connectivity
* Monitoring
* High availability
* Disaster recovery

Important

PTA creates a dependency on the availability of the on-premises authentication infrastructure.

⸻

3. Federated Authentication

What Is Federation?

Federated authentication allows Microsoft Entra ID to trust another identity provider to authenticate the user.

A common Microsoft example is:

Active Directory Federation Services (AD FS)

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
  ↓
Authentication Result
  ↓
Microsoft Entra ID
  ↓
Application

In this model, the federation service performs the authentication rather than Microsoft Entra ID directly validating the user’s password.

⸻

Why Use Federation?

Federation can be useful when an organization has specific authentication requirements that require an external or custom identity provider.

Examples may include:

* Existing federation infrastructure
* Specialized authentication requirements
* Custom authentication workflows
* Certain third-party authentication integrations
* Specific organizational requirements

However, federation generally introduces more infrastructure and operational complexity than PHS.

⸻

PHS vs. PTA vs. Federation

Feature	PHS	PTA	Federation
Authentication location	Microsoft Entra ID	On-premises AD through PTA agents	Federation provider
Password hash synchronized	Yes	No	No
Requires on-premises authentication servers	No	Yes	Yes
Infrastructure complexity	Low	Medium	High
Maintenance	Lower	Medium	Higher
Dependency on on-premises authentication	Low	High	High
Common federation service	N/A	N/A	AD FS

⸻

Easy Visual Comparison

PHS
User
 ↓
Microsoft Entra ID
 ↓
Cloud Authentication
PTA
User
 ↓
Microsoft Entra ID
 ↓
PTA Agent
 ↓
On-Premises AD
Federation
User
 ↓
Microsoft Entra ID
 ↓
AD FS / Identity Provider
 ↓
On-Premises AD

⸻

Which Method Is Simpler?

For many organizations, PHS is the simplest hybrid authentication approach.

Why?

* Less infrastructure
* Fewer servers
* Easier management
* Reduced on-premises dependency
* Strong cloud resilience

Microsoft generally recommends evaluating PHS first for hybrid authentication scenarios unless there is a specific requirement for another approach.

⸻

What Happens During an On-Premises Outage?

This is an important concept.

PHS

If the on-premises authentication infrastructure becomes unavailable after synchronization has already occurred:

On-Premises AD
      X
      |
Microsoft Entra ID
      ↓
Cloud Authentication

Users can generally continue authenticating to cloud services because authentication occurs in Microsoft Entra ID.

However, synchronization of new changes may be affected while the synchronization infrastructure is unavailable.

⸻

PTA

If the on-premises PTA authentication agents or required infrastructure are unavailable:

User
 ↓
Microsoft Entra ID
 ↓
PTA Agent
      X
 ↓
On-Premises AD

Cloud authentication may fail because the credentials need to be validated through the on-premises authentication infrastructure.

For this reason, PTA deployments should use multiple agents and appropriate availability planning.

⸻

Federation

If the federation service such as AD FS becomes unavailable:

User
 ↓
Microsoft Entra ID
 ↓
AD FS
      X

Authentication can fail because Microsoft Entra ID cannot obtain the required authentication result from the federation provider.

Federated environments therefore require careful planning for:

* High availability
* Load balancing
* Certificates
* Federation servers
* Monitoring
* Disaster recovery

⸻

PHS and Disaster Recovery

One of the major advantages of PHS is reduced dependency on on-premises authentication infrastructure.

For cloud authentication:

PHS
 ↓
Microsoft Entra ID
 ↓
Cloud Authentication

This can make PHS a strong option for organizations that want cloud authentication to continue even when parts of the on-premises environment are unavailable.

⸻

Important Correction: PHS as a Backup

A common misunderstanding is:

“If we use PTA or federation, Microsoft automatically switches to PHS when they fail.”

That is not something you should assume.

If an organization wants an alternative authentication method or disaster-recovery strategy, it must be designed and configured appropriately.

For exam purposes, remember:

PHS reduces dependency on on-premises authentication infrastructure.

Do not assume automatic failover unless the specific Microsoft-supported configuration provides it.

⸻

PHS and Identity Protection

PHS is also important for certain identity-security capabilities.

Microsoft Entra ID Protection can use password-related signals to help identify potentially compromised credentials.

For example:

Credential Exposure
       ↓
Identity Protection
       ↓
Risk Detection
       ↓
Conditional Access
       ↓
MFA / Remediation

Important: Do not memorize this as “Identity Protection always requires PHS.” Specific Identity Protection capabilities and licensing requirements should be checked against the current Microsoft documentation.

⸻

Authentication Location

This is one of the easiest ways to distinguish the three methods.

PHS

Authentication happens in the cloud.

Microsoft Entra ID

PTA

Authentication is validated through on-premises infrastructure.

Microsoft Entra ID
       ↓
PTA Agent
       ↓
On-Premises AD

Federation

Authentication is delegated to a federation provider.

Microsoft Entra ID
       ↓
AD FS / Federation Provider

⸻

Authentication Method in One Sentence

Password Hash Synchronization

Microsoft Entra ID authenticates the user in the cloud using synchronized password hash information.

Pass-Through Authentication

Microsoft Entra ID uses an on-premises PTA agent to validate the user’s credentials against Active Directory.

Federation

Microsoft Entra ID delegates authentication to a trusted federation or identity provider such as AD FS.

⸻

Real-World Example

Imagine Contoso has:

10,000 Employees
        ↓
On-Premises Active Directory
        ↓
Microsoft Entra Connect
        ↓
Microsoft Entra ID
        ↓
Microsoft 365

The company needs to decide how users will authenticate.

Option 1 — PHS

User
 ↓
Microsoft Entra ID
 ↓
Cloud Authentication

Simple and highly cloud-dependent.

Option 2 — PTA

User
 ↓
Microsoft Entra ID
 ↓
PTA Agent
 ↓
On-Premises AD

More dependent on on-premises authentication infrastructure.

Option 3 — Federation

User
 ↓
Microsoft Entra ID
 ↓
AD FS
 ↓
On-Premises AD

More complex and requires additional infrastructure.

⸻

Quick Decision Model

Do we need a specific federation requirement?
             ↓
          No
             ↓
      Consider PHS first
             ↓
       Simple + Reliable

If an organization has a specific reason to keep authentication on-premises:

Need on-premises password validation?
             ↓
            Yes
             ↓
           PTA

If an organization requires a federation architecture:

Need federation?
      ↓
     Yes
      ↓
AD FS / Federation Provider

⸻

Exam Tips

Which method is generally the simplest?

Password Hash Synchronization (PHS)

⸻

Which method synchronizes password hash information?

Password Hash Synchronization (PHS)

⸻

Which method validates authentication using an on-premises PTA agent?

Pass-Through Authentication (PTA)

⸻

Which method commonly uses AD FS?

Federated Authentication

⸻

Which method has the least on-premises authentication dependency?

PHS

⸻

Which method requires on-premises authentication infrastructure?

PTA

⸻

Which method normally requires federation infrastructure?

Federated Authentication

⸻

Which method is generally preferred when there is no special requirement for another approach?

PHS

⸻

Common Interview Question

“What is the difference between PHS and PTA?”

A good junior-level answer:

PHS synchronizes password hash information from on-premises Active Directory to Microsoft Entra ID, allowing authentication to occur in the cloud. PTA does not synchronize the password hash for cloud authentication; instead, Microsoft Entra ID uses an on-premises authentication agent to validate the user’s credentials against Active Directory.

⸻

Common Interview Question

“Why would a company choose federation?”

A good answer:

A company may choose federation when it has specific authentication or identity-provider requirements that are better handled by a federation service such as AD FS. Federation can provide specialized authentication capabilities, but it also introduces additional infrastructure and operational complexity.

⸻

Common Interview Question

“What happens if the domain controllers go down?”

With PHS

Existing synchronized cloud identities can generally continue authenticating to cloud services.

With PTA

Authentication can be affected because PTA depends on on-premises authentication infrastructure.

With Federation

Authentication can be affected if the federation infrastructure is unavailable.

⸻

Final Comparison

PHS
│
├── Password hash information synchronized
├── Authentication in Microsoft Entra ID
├── Low infrastructure dependency
└── Simple and commonly preferred
PTA
│
├── No password hash synchronization for authentication
├── Authentication validated on-premises
├── Requires PTA agents
└── More dependent on on-premises infrastructure
Federation
│
├── Authentication delegated
├── Common example: AD FS
├── Requires federation infrastructure
└── Most complex of the three

⸻

Easy Memory Trick

PHS

Password Hash → Cloud

PTA

Pass-Through → Active Directory

Federation

Forward Authentication → Federation Provider

PHS = Cloud Authentication
PTA = On-Premises Validation
Federation = External Identity Provider

⸻

Final One-Line Summary

PHS authenticates users in the cloud using synchronized password hash information, PTA validates credentials through on-premises authentication agents, and Federation delegates authentication to a trusted identity provider such as AD FS.