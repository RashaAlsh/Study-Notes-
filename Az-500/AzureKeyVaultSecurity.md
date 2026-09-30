Azure Key Vault Security
Azure Key Vault is a security service for securely storing and controlling access to:
* Secrets — passwords, API keys, tokens, connection strings
* Keys — cryptographic keys for encryption, decryption, and signing
* Certificates — SSL/TLS certificates and related private-key material
Think of Key Vault as a secure digital safe for sensitive information.
 
⸻
 
1. What Does Azure Key Vault Store?
Secrets
Secrets are sensitive values that applications should not hard-code into source code or configuration files.
Examples:
* Database passwords
* API keys
* Connection strings
* Access tokens
Application
    |
    | Request secret
    v
Azure Key Vault
    |
    v
Database Password
Keys
Cryptographic keys are used for operations such as:
* Encryption
* Decryption
* Signing
* Verification
Example:
Azure Storage
      |
      | Customer-managed key
      v
Azure Key Vault
Certificates
Key Vault can store and manage certificates used for:
* HTTPS
* SSL/TLS
* Application authentication
Example:
www.contoso.com
       |
       v
TLS Certificate
       |
       v
Azure Key Vault
 
⸻
 
2. Network Security
Key Vault network access can be restricted so that only approved networks or private connectivity paths can reach the vault.
Firewall and Network Rules
You can restrict access based on:
* IP addresses
* Virtual networks
* Network rules
Example:
Allowed:
10.10.1.0/24

Denied:
Everything else
This reduces unnecessary public exposure.
 
⸻
 
VNet Service Endpoints
A service endpoint can restrict Key Vault access to selected Azure virtual networks.
Production VNet
      |
      | Service Endpoint
      v
Azure Key Vault
The vault can be configured to accept traffic from specified VNets/subnets.
 
⸻
 
Private Endpoint / Azure Private Link
A Private Endpoint gives the Key Vault a private IP address in your virtual network.
Instead of:
Application
     |
 Public Network
     |
     v
Key Vault
you can use:
Application
     |
 Private IP
     |
     v
Private Endpoint
     |
     v
Azure Key Vault
Benefits:
* Reduces public network exposure
* Provides private connectivity
* Integrates with Azure Private Link
* Useful for highly restricted environments
Exam Memory
Private Endpoint = private network access to Key Vault
Do not treat “most secure” as an absolute ranking for every architecture; the correct choice depends on the network requirements.
 
⸻
 
3. Transport Security
Communication with Key Vault uses HTTPS/TLS to protect data in transit.
Application
    |
    | HTTPS / TLS
    v
Azure Key Vault
For exam questions involving Key Vault communication, remember:
Key Vault traffic is protected with TLS over HTTPS.
Exact currently supported TLS versions should be checked against the current Azure documentation when version-specific configuration matters.
 
⸻
 
4. Authentication
Authentication answers:
Who are you?
Azure Key Vault integrates with Microsoft Entra ID for identity-based authentication.
Common identities include:
* Users
* Groups
* Service principals
* Managed identities
 
⸻
 
Managed Identity
A managed identity is an Azure-managed identity that applications can use to authenticate to Azure services without storing credentials in application code.
Example:
Azure Web App
     |
     | Managed Identity
     v
Microsoft Entra ID
     |
     | Token
     v
Azure Key Vault
Advantages:
* No application password to store
* No client secret to rotate manually
* Identity is managed by Azure
* Works well with Azure services
Exam Memory
Azure service → Managed Identity → Entra ID → Key Vault
 
⸻
 
5. Security Principals
A security principal is an identity that can be granted permissions.
Common types include:
Principal	Represents	Example
User	Person	Administrator
Group	Collection of users	Security Team
Service Principal	Application identity	Web Application
Managed Identity	Azure-managed workload identity	Azure Function
Important
A managed identity is represented in Microsoft Entra ID and is commonly used by Azure workloads to access resources securely.
 
⸻
 
6. Authentication Scenarios
Application Access
An application accesses Key Vault using its own identity.
Web App
   |
   | Managed Identity
   v
Key Vault
This is a common Azure architecture.
 
⸻
 
User Access
A human user accesses Key Vault through tools such as:
* Azure Portal
* Azure CLI
* Azure PowerShell
The user authenticates through Microsoft Entra ID.
 
⸻
 
Application + User
In some architectures, an application acts on behalf of a signed-in user.
User
 |
 v
Application
 |
 | On-Behalf-Of / delegated flow
 v
Azure Resources
This is more advanced and is different from a workload simply using its own managed identity.
 
⸻
 
7. Authentication vs Authorization
This distinction is extremely important.
Authentication
Who are you?
Usually handled through Microsoft Entra ID.
Authorization
What are you allowed to do?
Controlled through:
* Azure RBAC
* Key Vault data-plane permissions
* Legacy Key Vault access policies
Memory
Authentication = Who?
Authorization  = What can they do?
 
⸻
 
8. Management Plane vs Data Plane
This is one of the most important Key Vault exam concepts.
Management Plane
The management plane controls the Key Vault resource itself.
Examples:
* Create a Key Vault
* Delete a Key Vault
* Configure networking
* Configure resource settings
* Configure diagnostic settings
Typical Azure Resource Manager endpoint:
management.azure.com
Management-plane authorization uses Azure RBAC.
 
⸻
 
Data Plane
The data plane controls the contents and operations inside the vault.
Examples:
* Read a secret
* Create a secret
* Delete a secret
* Read certificate information
* Perform supported cryptographic operations with keys
Conceptually:
Management Plane
      |
      v
Manage the Vault

Data Plane
      |
      v
Use the Vault Contents
Memory Trick
Management Plane = Manage the Vault Data Plane = Use the Vault
 
⸻
 
9. Azure RBAC vs Key Vault Access Policies
Key Vault supports two authorization approaches for data-plane access:
Azure RBAC
Modern Azure authorization model.
Benefits:
* Centralized role management
* Consistent Azure authorization model
* Supports least privilege
* Integrates with Entra identities
* Better separation of management and data access
Access Policies
The older Key Vault authorization model.
Access policies directly specify which identities can perform which Key Vault operations.
For new designs, Azure RBAC is generally preferred.
 
⸻
 
Important Security Consideration
With the legacy access-policy model, someone with sufficient permissions to manage the Key Vault resource could potentially manipulate access policies and grant data access.
Azure RBAC provides a clearer separation between:
Managing the Azure resource
        vs
Accessing Key Vault data
Exam Memory
Modern Key Vault authorization → Azure RBAC
 
⸻
 
10. Key Vault RBAC Roles
Different roles provide different levels of access.
Examples include:
Role	Purpose
Key Vault Contributor	Manage the Key Vault resource
Key Vault Reader	Read Key Vault metadata
Key Vault Secrets User	Read secret contents
Key Vault Secrets Officer	Manage secrets
Key Vault Crypto User	Use keys for cryptographic operations
Key Vault Crypto Officer	Manage cryptographic keys
Key Vault Certificates Officer	Manage certificates
Common Exam Trap
Key Vault Contributor ≠ permission to read secrets.
Management-plane permissions and data-plane permissions are different.
 
⸻
 
11. Least Privilege
Give identities only the permissions they actually need.
Bad design:
Application
     |
     v
Key Vault Administrator
Better design:
Application
     |
     v
Key Vault Secrets User
if the application only needs to read secrets.
Memory
Give the smallest role at the smallest practical scope.
 
⸻
 
12. Conditional Access
Microsoft Entra Conditional Access can be used as part of the identity security layer for Key Vault access scenarios.
Possible conditions can include:
* Require MFA
* Require a compliant device
* Restrict access based on location
* Apply risk-based access controls
Conceptually:
User
 |
 v
Microsoft Entra ID
 |
 | Conditional Access
 | MFA / Device / Risk
 v
Key Vault
The exact Conditional Access behavior depends on the client, identity, and access scenario.
 
⸻
 
13. Logging and Monitoring
Key Vault should be monitored for security-sensitive activity.
Examples include:
* Secret access
* Key operations
* Certificate operations
* Configuration changes
* Failed requests
* Authentication/authorization failures
Azure monitoring services can help collect and analyze this information.
Key Vault
    |
    v
Diagnostic Logs
    |
    +----> Log Analytics
    |
    +----> Azure Monitor
    |
    +----> Microsoft Sentinel
 
⸻
 
14. Event Grid Integration
Azure Event Grid can react to supported Key Vault events.
Examples include events related to:
* Key changes
* Secret expiration
* Certificate expiration
This can support automation.
Example:
Certificate Nearing Expiration
            |
            v
        Event Grid
            |
            v
    Automation / Function
            |
            v
      Notify / Remediate
Memory
Key Vault + Event Grid = react to security/lifecycle events
 
⸻
 
15. Backup and Recovery
Key Vault provides several protections against accidental or malicious deletion.
Soft Delete
Soft Delete allows deleted Key Vault objects to remain recoverable during the configured retention period.
Example:
Secret
  |
Delete
  |
  v
Soft Deleted
  |
  | Recover
  v
Secret Restored
 
⸻
 
Purge Protection
Purge Protection helps prevent permanently purging soft-deleted objects before the protected retention period has elapsed.
This provides stronger protection against destructive actions.
Memory
Soft Delete
    =
Recover deleted objects

Purge Protection
    =
Prevent permanent purge
Best Practice
For security-sensitive environments:
* Enable Soft Delete
* Enable Purge Protection
 
⸻
 
16. Backup vs Soft Delete
These features solve different problems.
Feature	Purpose
Soft Delete	Recover deleted objects
Purge Protection	Prevent permanent purge
Backup	Create a recoverable backup of supported objects
Do not treat them as interchangeable.
 
⸻
 
17. Key Vault Security Architecture
A secure design combines multiple layers.
                 Users / Applications
                         |
                         v
                Microsoft Entra ID
                         |
                  Authentication
                         |
                         v
                Conditional Access
                         |
                         v
                  Azure RBAC
                         |
                   Authorization
                         |
                         v
              Private Endpoint / Network
                         |
                         v
                 Azure Key Vault
                /        |        \
           Secrets      Keys    Certificates
                         |
                         v
               Logging / Monitoring
                         |
                         v
             Azure Monitor / Sentinel
This is defense in depth.
No single control should be expected to provide complete protection.
 
⸻
 
18. Key Vault Security Best Practices
Authentication
* Use Microsoft Entra ID
* Prefer managed identities for Azure workloads
* Avoid storing long-lived application secrets where possible
* Use MFA and Conditional Access where appropriate
Authorization
* Prefer Azure RBAC for new designs
* Follow least privilege
* Assign roles at the smallest practical scope
* Separate management-plane and data-plane permissions
Networking
* Use Private Endpoints where private connectivity is required
* Restrict public network access where appropriate
* Use firewall/network rules
* Use VNet integration/service-endpoint options where appropriate
Monitoring
* Enable appropriate diagnostic logging
* Monitor access and configuration changes
* Use Azure Monitor and Log Analytics
* Integrate with Microsoft Sentinel when centralized security monitoring is required
* Use Event Grid for supported lifecycle events
Recovery
* Enable Soft Delete
* Enable Purge Protection
* Use backups where appropriate
 
⸻
 
19. Quick Exam Cheat Sheet
Topic	Remember
Key Vault stores	Secrets, Keys, Certificates
Identity provider	Microsoft Entra ID
Recommended workload identity	Managed Identity
Authentication	Who are you?
Authorization	What can you do?
Management plane	Manage the vault resource
Data plane	Access/use vault contents
Management authorization	Azure RBAC
Data authorization	Azure RBAC or legacy Access Policies
Modern authorization model	Azure RBAC
Private network access	Private Endpoint
Transport security	HTTPS/TLS
Deleted objects	Soft Delete
Prevent permanent purge	Purge Protection
Event automation	Event Grid
Monitoring	Azure Monitor / Log Analytics / Sentinel
Security principle	Least Privilege
 
⸻
 
20. Common Exam Questions
Q1. What does Azure Key Vault store?
Answer: Secrets, cryptographic keys, and certificates.
 
⸻
 
Q2. What identity service does Key Vault use for authentication?
Answer: Microsoft Entra ID.
 
⸻
 
Q3. An Azure Web App needs to access a secret. What authentication approach should you consider first?
Answer: Use the Web App’s managed identity rather than storing a client secret in the application.
 
⸻
 
Q4. What is the difference between the management plane and data plane?
Answer:
* Management plane: manages the Key Vault resource.
* Data plane: accesses and operates on the vault’s contents.
 
⸻
 
Q5. Which authorization model is generally preferred for new Key Vault deployments?
Answer: Azure RBAC.
 
⸻
 
Q6. Does Key Vault Contributor automatically allow an identity to read secrets?
Answer: No. Managing the Key Vault resource is different from accessing secret data.
 
⸻
 
Q7. How can an application access Key Vault privately?
Answer: Use a Private Endpoint / Azure Private Link when private network connectivity is required.
 
⸻
 
Q8. What protects against accidental deletion?
Answer: Soft Delete.
 
⸻
 
Q9. What provides stronger protection against permanent purge?
Answer: Purge Protection.
 
⸻
 
Q10. What service can react to supported Key Vault lifecycle events?
Answer: Azure Event Grid.
 
⸻
 
21. Final Memory Map
                    AZURE KEY VAULT
                           |
        +------------------+------------------+
        |                  |                  |
     Stores            Identity          Networking
        |                  |                  |
 Secrets / Keys       Entra ID          Private Endpoint
 Certificates         Managed ID        Firewall / Rules
        |                  |                  |
        +------------------+------------------+
                           |
                      Authorization
                           |
                       Azure RBAC
                           |
             +-------------+-------------+
             |                           |
       Management Plane             Data Plane
       Manage Vault                Use Contents
             |                           |
             +-------------+-------------+
                           |
                    Security & Recovery
                           |
       +-------------------+-------------------+
       |                   |                   |
    Monitoring          Soft Delete      Purge Protection
       |
 Azure Monitor /
 Log Analytics /
 Sentinel
Golden Rule
Azure Key Vault securely stores secrets, keys, and certificates. Use Microsoft Entra ID for identity, managed identities for Azure workloads, Azure RBAC and least privilege for authorization, Private Endpoints when private network access is required, and Soft Delete + Purge Protection for recovery protection.
