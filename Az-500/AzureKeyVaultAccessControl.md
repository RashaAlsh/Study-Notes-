Azure Key Vault Access Control (RBAC)
1. What Is Azure RBAC?
Azure Role-Based Access Control (RBAC) is Azure’s authorization system.
It determines:
* Who can access a resource
* What they can do
* Where they can do it
Simple idea
The right person gets the right access to the right resource.
Security Principal
       |
       v
Role Assignment
       |
       v
Permission
       |
       v
Azure Resource
For Key Vault, RBAC can control access to:
* Secrets
* Keys
* Certificates
* The Key Vault resource itself
 
⸻
 
2. Why Use RBAC with Key Vault?
Key Vault supports two authorization models:
1. Azure RBAC
2. Key Vault access policies
For new designs, Azure RBAC is generally the preferred authorization model because it integrates with Azure’s centralized identity and access-control system.
Benefits
* Centralized permission management
* Consistent Azure authorization model
* Fine-grained roles
* Scope-based inheritance
* Better integration with Azure governance
* Easier management at scale
* Supports least-privilege access
Exam Memory: Key Vault RBAC = Centralized + Granular + Least Privilege
 
⸻
 
3. RBAC Scope
Azure RBAC assignments can be made at different scopes.
Management Group
       ↓
Subscription
       ↓
Resource Group
       ↓
Key Vault
       ↓
Supported resource/object scope
Permissions assigned at a higher scope can be inherited by resources below that scope.
Example
If a role is assigned at the subscription level:
Subscription
     |
     +---- Key Vault A
     |
     +---- Key Vault B
     |
     +---- Key Vault C
The assignment can affect multiple Key Vaults within that scope.
Best Practice: Use the smallest practical scope that satisfies the requirement.
 
⸻
 
4. Key Vault Organization
A common design approach is to separate Key Vaults by application and environment where appropriate.
Example:
Application 1
   |
   +-- App1-Dev-KV
   +-- App1-Test-KV
   +-- App1-Prod-KV
This can help with:
* Access isolation
* Environment separation
* Permission management
* Operational boundaries
However, the exact number of Key Vaults should be based on security, operational, and application requirements rather than treating “one vault per application” as a universal rule.
Memory: Separate environments when isolation requirements justify it.
 
⸻
 
5. Key Vault RBAC Roles You Should Know
The most important built-in data-plane roles include:
Role	Main Purpose
Key Vault Administrator	Full data-plane access to keys, secrets, and certificates
Key Vault Reader	Read Key Vault metadata
Key Vault Secrets Officer	Manage secrets
Key Vault Secrets User	Read secret contents
Key Vault Crypto Officer	Manage cryptographic keys
Key Vault Crypto User	Perform supported cryptographic operations using keys
Key Vault Crypto Service Encryption User	Allows supported Azure services to use keys for encryption
Key Vault Certificates Officer	Manage certificates
Key Vault Data Access Administrator	Manage access to Key Vault data-plane roles
Let’s examine the important roles.
 
⸻
 
6. Key Vault Administrator
Key Vault Administrator provides broad data-plane permissions over Key Vault objects.
It can manage:
* Keys
* Secrets
* Certificates
Concept
Key Vault Administrator
        |
        +-- Keys
        |
        +-- Secrets
        |
        +-- Certificates
Important
This role is about Key Vault data-plane access.
It does not automatically mean the user can manage Azure RBAC role assignments.
Exam Memory: Key Vault Administrator = Full Key Vault data access
 
⸻
 
7. Key Vault Reader
Key Vault Reader provides read access to Key Vault metadata.
For example, it can allow visibility into information such as:
* Secret names/metadata
* Key metadata
* Certificate metadata
It does not provide access to secret values or key material.
Example
Key Vault Reader

Can see:
    DatabasePassword
    AppKey
    TLSCertificate

Cannot read:
    Secret Value
    Private Key Material
Exam Memory: Reader = Metadata, not secret contents.
 
⸻
 
8. Key Vault Secrets User
Key Vault Secrets User allows a principal to read secret contents for supported scenarios.
Example
An application needs:
* Database password
* API key
* Connection string
The application can be assigned the appropriate Key Vault secret-reading role.
Application
     |
     | RBAC
     v
Key Vault Secrets User
     |
     v
Secret Value
Exam Memory: Secrets User = Read secret contents
This is a common role for applications that need to retrieve secrets without managing them.
 
⸻
 
9. Key Vault Secrets Officer
Key Vault Secrets Officer is used to manage secrets.
It can perform supported management operations such as:
* Create secrets
* Update secrets
* Delete secrets
* Manage secret versions
Example
Security Team
      |
      v
Secrets Officer
      |
      +-- Create
      +-- Update
      +-- Delete
      +-- Manage secrets
It is not intended to provide broad permissions over keys or certificates.
Exam Memory: Secrets Officer = Manage secrets
 
⸻
 
10. Key Vault Crypto Officer
Key Vault Crypto Officer is used to manage cryptographic keys.
It can perform supported key-management operations such as:
* Create keys
* Import keys
* Delete keys
* Rotate keys
* Manage key versions
Example
Crypto Officer
      |
      v
    Keys
      |
      +-- Create
      +-- Manage
      +-- Rotate
      +-- Delete
Exam Memory: Crypto Officer = Manage keys
 
⸻
 
11. Key Vault Crypto User
Key Vault Crypto User is intended for principals that need to use cryptographic keys rather than manage them.
Depending on the key type and supported operation, this can include operations such as:
* Encrypt
* Decrypt
* Sign
* Verify
* Wrap
* Unwrap
Difference
Crypto Officer
      ↓
Manages the key

Crypto User
      ↓
Uses the key
Exam Memory: Officer = Manage User = Use
 
⸻
 
12. Key Vault Crypto Service Encryption User
This is a specialized role for supported Azure services that need to use Key Vault keys for encryption.
For example, an Azure service using a Customer-Managed Key (CMK) may need appropriate Key Vault permissions.
Concept
Azure Service
      |
      | CMK
      v
Azure Key Vault
      |
      v
Encryption Key
The exact role required depends on the Azure service and its current CMK integration.
Exam Memory: Crypto Service Encryption User = Azure service uses a Key Vault key for encryption
 
⸻
 
13. Key Vault Certificates Officer
Key Vault Certificates Officer manages certificates.
Supported operations can include:
* Create certificates
* Import certificates
* Renew certificates
* Manage certificates
* Delete certificates
Concept
Certificates Officer
        |
        v
   Certificates
        |
   +----+----+
   |         |
 Create    Renew
   |
 Import / Manage
Exam Memory: Certificates Officer = Manage certificates
 
⸻
 
14. Key Vault Data Access Administrator
Key Vault Data Access Administrator is a specialized role for managing access to Key Vault data-plane roles.
It can be used to:
* Assign appropriate Key Vault data roles
* Remove Key Vault data roles
This role is useful when separating:
Data access management
from:
Data usage
Example
Data Access Administrator
          |
          v
   Manage Key Vault
    Role Assignments
          |
          v
+---------+---------+
|         |         |
Reader   Secrets   Crypto
         User      User
Memory: Data Access Administrator = Manage access to Key Vault data
 
⸻
 
15. Key Vault Contributor — Important Exam Trap
This is one of the most common points of confusion.
Key Vault Contributor is primarily a management-plane role.
It can manage the Key Vault Azure resource, but it does not automatically provide access to the secrets, keys, or certificates stored inside it.
Example
Key Vault Contributor
        |
        +-- Manage vault resource
        |
        +-- Configure resource
        |
        X-- Read secret value
        X-- Read key material
        X-- Read certificate contents
Critical Exam Memory: Key Vault Contributor ≠ access to Key Vault data
 
⸻
 
16. Management Plane vs Data Plane
This distinction is extremely important.
Management Plane
The management plane controls the Azure Key Vault resource itself.
Examples:
* Create a Key Vault
* Delete a Key Vault
* Configure resource settings
* Configure networking
* Configure diagnostic settings
* Manage Azure resource properties
Azure Subscription
       |
       v
Key Vault Resource
       |
       +-- Create
       +-- Delete
       +-- Configure
 
⸻
 
Data Plane
The data plane controls the objects stored inside Key Vault.
Examples:
* Read a secret
* Create a secret
* Manage a key
* Rotate a key
* Manage a certificate
Key Vault
    |
    +-- Secrets
    |
    +-- Keys
    |
    +-- Certificates
Easy Memory
Management Plane = Manage the vault
Data Plane = Manage the contents
 
⸻
 
17. Key Vault Contributor vs Key Vault Administrator
Role	Resource Management	Secrets	Keys	Certificates
Key Vault Contributor	✅	❌	❌	❌
Key Vault Administrator	Not its primary purpose	✅	✅	✅
Exam Scenario
A user can:
Create and configure a Key Vault
but cannot:
Read a secret stored inside it.
That can be explained by the difference between management-plane permissions and data-plane permissions.
 
⸻
 
18. Access Policies vs Azure RBAC
Key Vault historically supported access policies.
Older model
Key Vault
    |
    v
Access Policies
    |
    v
Object Permissions
RBAC model
Azure RBAC
    |
    v
Role Assignment
    |
    v
Key Vault
    |
    v
Data Access
Azure RBAC is generally the preferred authorization model for new Key Vault deployments.
Exam Memory: Access Policies = Legacy authorization model Azure RBAC = Preferred modern authorization model
 
⸻
 
19. Least Privilege
Do not give every application Key Vault Administrator.
Instead, assign the smallest role that satisfies the requirement.
Example
Application only needs to read a database password:
Application
     |
     v
Key Vault Secrets User
     |
     v
Secret
It does not need:
Key Vault Administrator
Another example
Security team manages secrets:
Security Team
     |
     v
Key Vault Secrets Officer
Key-management application
Application / Service
       |
       v
Crypto User
       |
       v
Key
Golden security principle: Give identities only the permissions they actually need.
 
⸻
 
20. Common Scenarios
Scenario 1 — Application Reads a Secret
Requirement: An application needs to retrieve a database password.
Typical role:
Key Vault Secrets User
Application
    ↓
Secrets User
    ↓
Secret Value
 
⸻
 
Scenario 2 — Security Team Manages Secrets
Requirement: A security administrator needs to create, update, and delete secrets.
Typical role:
Key Vault Secrets Officer
 
⸻
 
Scenario 3 — Administrator Needs Broad Key Vault Data Access
Requirement: An administrator needs broad access to keys, secrets, and certificates.
Role:
Key Vault Administrator
 
⸻
 
Scenario 4 — Application Uses a Customer-Managed Key
Requirement: An Azure service needs to use a Key Vault key for encryption.
Relevant concept:
Key Vault Crypto Service Encryption User
The exact role and configuration depend on the Azure service’s CMK integration.
 
⸻
 
Scenario 5 — Auditor Needs Visibility
Requirement: An auditor needs to view Key Vault metadata but must not read secret values.
Role:
Key Vault Reader
 
⸻
 
Scenario 6 — Administrator Manages the Vault Resource
Requirement: An administrator needs to create or configure the Key Vault resource but does not need access to the stored secrets.
Relevant role:
Key Vault Contributor
Remember: Contributor manages the resource, not the protected data.
 
⸻
 
21. Role Comparison Cheat Sheet
Requirement	Appropriate Role
Full data-plane access	Key Vault Administrator
View Key Vault metadata	Key Vault Reader
Read secret contents	Key Vault Secrets User
Manage secrets	Key Vault Secrets Officer
Manage keys	Key Vault Crypto Officer
Use keys for cryptographic operations	Key Vault Crypto User
Azure service uses CMK for encryption	Key Vault Crypto Service Encryption User
Manage certificates	Key Vault Certificates Officer
Manage Key Vault data-role assignments	Key Vault Data Access Administrator
Manage Key Vault Azure resource	Key Vault Contributor
 
⸻
 
22. How RBAC Works with Key Vault
The complete authorization model can be remembered as:
Security Principal
(User / Group / App / Managed Identity)
             |
             v
      Role Assignment
             |
             v
      Key Vault Role
             |
             v
           Scope
             |
             v
       Allowed Action
Formula
Who + Role + Scope = Access
For example:
Application
    +
Key Vault Secrets User
    +
Production Key Vault
    =
Read Secret Contents
 
⸻
 
23. Common Exam Questions
Q1. What is the recommended authorization model for new Azure Key Vault deployments?
Answer: Azure RBAC
 
⸻
 
Q2. Which role can read secret values?
Answer: Key Vault Secrets User
 
⸻
 
Q3. Which role manages secrets?
Answer: Key Vault Secrets Officer
 
⸻
 
Q4. Which role manages cryptographic keys?
Answer: Key Vault Crypto Officer
 
⸻
 
Q5. Which role uses keys for cryptographic operations without managing the keys?
Answer: Key Vault Crypto User
 
⸻
 
Q6. Which role provides broad data-plane access to keys, secrets, and certificates?
Answer: Key Vault Administrator
 
⸻
 
Q7. Can Key Vault Reader read secret values?
Answer: No.
It provides metadata/read visibility, not secret contents.
 
⸻
 
Q8. Can Key Vault Contributor read secrets?
Answer: No.
Key Vault Contributor primarily manages the Key Vault resource at the management plane.
 
⸻
 
Q9. What is the difference between Key Vault Secrets User and Secrets Officer?
Answer:
Secrets User
     ↓
Read secret contents

Secrets Officer
     ↓
Manage secrets
 
⸻
 
Q10. What is the difference between Crypto User and Crypto Officer?
Answer:
Crypto User
     ↓
Use keys

Crypto Officer
     ↓
Manage keys
 
⸻
 
Q11. What is the difference between management plane and data plane?
Answer:
Management Plane
     ↓
Manage the Key Vault resource

Data Plane
     ↓
Access/manage keys, secrets,
and certificates
 
⸻
 
24. Final Exam Cheat Sheet
Azure RBAC
= Who can do what?

Key Vault Administrator
= Broad data-plane access

Key Vault Reader
= Metadata only

Secrets User
= Read secret values

Secrets Officer
= Manage secrets

Crypto User
= Use cryptographic keys

Crypto Officer
= Manage cryptographic keys

Crypto Service Encryption User
= Supported Azure services use CMKs

Certificates Officer
= Manage certificates

Data Access Administrator
= Manage Key Vault data-role assignments

Key Vault Contributor
= Manage Key Vault resource
  NOT the secrets/keys/certificates
 
⸻
 
25. The Most Important Distinction
             KEY VAULT
                 |
       +---------+---------+
       |                   |
       v                   v
 Management Plane      Data Plane
       |                   |
       v                   v
 Manage Vault          Manage Contents
       |                   |
       |             +-----+-----+
       |             |     |     |
       |           Keys Secrets Certs
       |
       v
Key Vault Contributor
Remember
Management Plane = Manage the vault
Data Plane = Access the contents
RBAC = Control who gets that access
 
⸻
 
26. Golden Rule
Use Azure RBAC and least privilege for Key Vault access. Give each user, application, or managed identity only the role required for its task.
One-line exam memory
Key Vault Contributor manages the vault resource; Key Vault data roles manage or use the keys, secrets, and certificates stored inside it.
