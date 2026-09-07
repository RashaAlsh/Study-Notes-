Azure Encryption
Complete Beginner-Friendly Summary
What is Azure Encryption?
Azure encryption protects data throughout its lifecycle.
There are three important areas to understand:
Azure Encryption
│
├── Data at Rest
│   └── Stored data
│
├── Data in Transit
│   └── Moving data
│
└── Key Management
    └── Protecting encryption keys
Easy Memory
At Rest = Stored In Transit = Moving Key Management = Protecting the keys
 
⸻
 
1. Encryption of Data at Rest
What is Data at Rest?
Data at rest is information stored on a physical or logical storage system.
Examples include:
* Virtual machine disks
* Managed disks
* Databases
* Azure Storage
* Files
* Backups
* Snapshots
* Data lakes
Example:
Application
    ↓
Stored Data
    ↓
Encryption at Rest
The goal is to protect stored data if someone gains unauthorized access to the underlying storage.
 
⸻
 
Azure Encryption at Rest
Most Azure services provide encryption at rest by default.
Azure services can use encryption across:
* IaaS
* PaaS
* SaaS
Azure commonly uses AES-256 encryption for data at rest, although the exact implementation can vary by service.
Memory
Data at Rest = Protect stored data
 
⸻
 
Encryption Models
Azure supports different approaches to encryption and key management.
Client-Side Encryption
With client-side encryption, the application encrypts the data before sending it to Azure.
Application
    ↓
Encrypt Data
    ↓
Encrypted Data
    ↓
Azure
The customer controls the encryption process and keys.
Benefits
* Customer-controlled encryption
* Encryption occurs before data reaches Azure
* Useful when the application must maintain control of plaintext data
 
⸻
 
Server-Side Encryption
With server-side encryption, the Azure service encrypts the data after receiving it.
Application
    ↓
Azure Service
    ↓
Encryption
    ↓
Encrypted Storage
The service manages the encryption process.
Azure supports different key-management models depending on the service.
 
⸻
 
Service-Managed Keys
With service-managed keys, Microsoft manages the encryption keys on behalf of the customer.
Azure Service
      ↓
Microsoft-Managed Key
      ↓
Encrypted Data
Advantages
* Simplest option
* Minimal administration
* Usually enabled by default
* No customer key-management infrastructure required
Memory
Service-Managed Key = Microsoft manages the key
 
⸻
 
Customer-Managed Keys
With Customer-Managed Keys (CMK), the customer controls the encryption key.
Keys are commonly stored in:
Azure Key Vault
Architecture:
Customer
   ↓
Azure Key Vault
   ↓
Customer-Managed Key
   ↓
Azure Service
   ↓
Encrypted Data
Benefits
* Greater control
* Key rotation control
* Key lifecycle management
* Ability to disable or revoke key access
* Supports compliance requirements that require customer control
Memory
CMK = Customer controls the encryption key
 
⸻
 
Bring Your Own Key (BYOK)
Bring Your Own Key (BYOK) allows customers to generate or import their own encryption keys for supported Azure services.
The key can then be used as a customer-managed key.
Customer Key
     ↓
Azure Key Vault
     ↓
Azure Service
     ↓
Encrypted Data
 
⸻
 
Host Your Own Key (HYOK)
Host Your Own Key (HYOK) refers to scenarios where encryption keys remain under customer-controlled infrastructure rather than being maintained entirely in Azure.
This provides a high degree of control but generally introduces greater complexity.
Customer-Controlled Infrastructure
             ↓
          Key
             ↓
       Azure Workload
Important: HYOK is a specialized architecture and is not the standard encryption model for most Azure services.
 
⸻
 
Encryption Model Comparison
Model	Who Controls the Key?	Complexity	Typical Use
Service-Managed Key	Microsoft	Low	Standard encryption
Customer-Managed Key	Customer	Medium	Compliance/control
Client-Side Encryption	Customer/application	High	Application-controlled encryption
HYOK	Customer-controlled infrastructure	High	Specialized requirements
 
⸻
 
2. Azure Storage and Disk Encryption
Azure Managed Disks
Azure provides encryption for managed disks and related storage resources.
Encryption can apply to:
* Managed disks
* Snapshots
* Images
Customer-managed encryption keys can be used for supported disk encryption scenarios.
 
⸻
 
Azure Storage Encryption
Azure Storage supports encryption at rest for services such as:
* Blob Storage
* Azure Files
* Queue Storage
* Table Storage
Azure Storage uses Storage Service Encryption (SSE).
Encryption and decryption are handled automatically by the service.
Application
    ↓
Azure Storage
    ↓
Automatic Encryption
    ↓
Encrypted Data
Important
Applications normally do not need to manually encrypt and decrypt data simply to use Storage Service Encryption.
 
⸻
 
Client-Side Blob Encryption
Applications can also encrypt data before uploading it to Azure Blob Storage.
A common envelope-encryption model uses:
Content Encryption Key (CEK)
Encrypts the actual data.
Key Encryption Key (KEK)
Protects or encrypts the CEK.
Example:
Data
 ↓
CEK
 ↓
Encrypted Data

CEK
 ↓
KEK
 ↓
Protected CEK
The KEK can be stored in Azure Key Vault.
 
⸻
 
3. Database Encryption
Different Azure database services provide different encryption mechanisms.
 
⸻
 
Azure SQL Database
Azure SQL Database supports several encryption technologies.
Transparent Data Encryption (TDE)
TDE encrypts data stored on disk.
It protects:
* Database files
* Transaction logs
* Backups
Conceptually:
Azure SQL Database
       ↓
      TDE
       ↓
Encrypted Database Storage
TDE is designed to protect data at rest.
Memory
TDE = Encrypt the database at rest
 
⸻
 
Always Encrypted
Always Encrypted is designed to protect sensitive values from unauthorized access, including access by database administrators in scenarios where the application controls the encryption keys.
The client application performs encryption before sensitive values are sent to the database.
Client Application
       ↓
Encrypt Sensitive Value
       ↓
Azure SQL Database
       ↓
Encrypted Value
Use Cases
Useful for highly sensitive information such as:
* Personal identifiers
* Financial information
* Confidential customer data
Memory
Always Encrypted = Protect sensitive column values from database-side plaintext access
 
⸻
 
Column-Level Encryption
Column-level encryption encrypts selected columns rather than encrypting the entire database.
Example:
Customer Table

Name       → Normal
Email      → Normal
SSN        → Encrypted
CardNumber → Encrypted
This provides more granular protection.
 
⸻
 
TDE vs Always Encrypted
Feature	TDE	Always Encrypted
Main purpose	Protect data at rest	Protect sensitive values
Encryption location	Database/storage layer	Client/application side
Protects database files	Yes	Not its primary purpose
Protects plaintext from DB administrators	No	Yes, when properly configured
Best for	Storage encryption	Highly sensitive columns
Easy Memory
TDE
= Encrypt the database at rest

Always Encrypted
= Encrypt sensitive values before they reach SQL
 
⸻
 
Azure Cosmos DB
Azure Cosmos DB provides encryption at rest by default.
Supported configurations can also use Customer-Managed Keys (CMK) for additional customer control.
Cosmos DB
    ↓
Encryption at Rest
    ↓
Microsoft-Managed Key
        OR
Customer-Managed Key
 
⸻
 
Azure Data Lake Storage
Azure Data Lake Storage provides encryption at rest.
Depending on the service configuration, encryption can use:
* Microsoft-managed keys
* Customer-managed keys
Encryption helps protect stored data from unauthorized access.
 
⸻
 
4. Encryption of Data in Transit
What is Data in Transit?
Data in transit is information moving between systems.
Examples:
User → Application

Application → Database

VM → VM

On-Premises → Azure

Azure Region → Azure Region
The goal is to prevent unauthorized parties from:
* Reading traffic
* Modifying traffic
* Intercepting communications
 
⸻
 
Common Encryption Technologies
Azure networking and services can use technologies such as:
* TLS
* HTTPS
* IPsec/IKE
* SSH
* RDP with TLS
* MACsec
 
⸻
 
MACsec
MACsec is a Layer 2 encryption technology.
Azure uses MACsec to protect certain traffic between Microsoft datacenters and network infrastructure.
It is based on:
IEEE 802.1AE
The encryption is handled by Microsoft’s infrastructure and does not normally require customer configuration.
Security Benefits
MACsec helps protect against:
* Network sniffing
* Traffic interception
* Wiretapping
* Certain man-in-the-middle scenarios
Memory
MACsec = Link-layer protection
 
⸻
 
TLS
Transport Layer Security (TLS) protects application-level communications.
It provides:
* Confidentiality
* Integrity
* Authentication
Example:
Client
  │
  │ HTTPS / TLS
  ↓
Azure Service
TLS is widely used by Azure services to secure communication.
 
⸻
 
HTTPS
HTTPS is HTTP protected by TLS.
HTTP
 +
TLS
 ↓
HTTPS
It protects web traffic from unauthorized interception and tampering.
 
⸻
 
TLS Cryptography
Modern TLS deployments can use cryptographic technologies such as:
* RSA
* Elliptic Curve Cryptography (ECC)
* AES
* SHA-2 family algorithms
The exact algorithms and cipher suites depend on the service and TLS configuration.
Important
Do not memorize a single cipher suite as universally applicable to all Azure services. Supported cryptographic algorithms can change as Microsoft improves security.
 
⸻
 
5. Azure Storage Secure Transfer
Azure Storage supports secure transport using HTTPS.
Organizations should configure storage accounts to require secure transfer where appropriate.
Conceptually:
Client
  │
  │ HTTPS
  ↓
Azure Storage
 
⸻
 
Secure Transfer Requirement
A storage account can be configured to require secure transfer.
This helps prevent clients from using insecure HTTP connections.
HTTP
 ↓
Blocked

HTTPS
 ↓
Allowed
 
⸻
 
Shared Access Signatures and HTTPS
When using Shared Access Signatures (SAS), organizations can require HTTPS for requests.
This helps ensure that SAS-protected resources are accessed through encrypted transport.
 
⸻
 
SMB Encryption
Azure Files supports secure SMB communication.
Modern SMB versions provide encryption capabilities, helping protect file-sharing traffic from:
* Eavesdropping
* Tampering
* Unauthorized inspection
Example:
Client
  │
  │ SMB
  │ Encrypted
  ↓
Azure Files
 
⸻
 
6. Secure Access to Virtual Machines
Windows Virtual Machines
Windows VMs are commonly accessed using:
Remote Desktop Protocol (RDP)
RDP connections can use TLS to protect the session.
Administrator
     │
     │ RDP / TLS
     ↓
Windows VM
 
⸻
 
Linux Virtual Machines
Linux VMs are commonly accessed using:
Secure Shell (SSH)
SSH provides encrypted communication.
SSH can use public/private key authentication.
SSH Client
    │
    │ Encrypted SSH
    ↓
Linux VM
SSH Keys
A typical configuration uses:
Private Key
    ↓
Client

Public Key
    ↓
Linux VM
The private key should remain protected on the client side.
 
⸻
 
7. Azure VPN Encryption
Azure VPN provides encrypted connectivity between Azure and external networks.
 
⸻
 
Site-to-Site VPN
A Site-to-Site VPN connects:
On-Premises Network
        │
        │ IPsec / IKE
        │
        ↓
Azure VPN Gateway
        │
        ↓
Azure VNet
Common technologies include:
* IPsec
* IKEv1
* IKEv2
The VPN tunnel encrypts traffic between the VPN endpoints.
 
⸻
 
Point-to-Site VPN
Point-to-Site VPN connects individual clients or devices to an Azure VNet.
User Device
     │
     │ VPN
     ↓
Azure VPN Gateway
     │
     ↓
Azure VNet
Depending on the VPN configuration, supported protocols and authentication methods can include certificate-based authentication and other supported VPN protocols.
 
⸻
 
8. Data Lake Encryption in Transit
Azure Data Lake Storage uses secure transport for communication with clients and applications.
HTTPS/TLS protects data while it moves between:
Client
  │
  │ HTTPS / TLS
  ↓
Data Lake Storage
This protects communication from interception and unauthorized modification.
 
⸻
 
9. Key Management with Azure Key Vault
What is Azure Key Vault?
Azure Key Vault is a managed Azure service for securely storing and managing:
* Encryption keys
* Secrets
* Certificates
It is commonly used when organizations need centralized control over cryptographic material.
 
⸻
 
Key Vault Architecture
                Azure Key Vault
                /      |      \
               /       |       \
            Keys     Secrets   Certificates
              |
              ↓
       Azure Services
              |
              ↓
       Encrypted Data
 
⸻
 
Benefits of Azure Key Vault
Key Vault provides capabilities such as:
* Secure key storage
* Centralized key management
* Access control
* Microsoft Entra ID integration
* Key generation
* Key import
* Key rotation
* Hardware-backed protection for supported configurations
 
⸻
 
Hardware Security Modules
Azure Key Vault supports hardware-backed key protection through supported Hardware Security Module (HSM) capabilities.
This provides stronger protection for highly sensitive cryptographic keys.
Organizations do not need to deploy and maintain their own physical HSM infrastructure when using supported managed HSM capabilities.
 
⸻
 
Key Vault Access Control
Access to Key Vault resources can be controlled using Azure identity and authorization mechanisms.
Important concepts include:
User / Application
       ↓
Microsoft Entra ID
       ↓
Authorization
       ↓
Azure Key Vault
       ↓
Key / Secret / Certificate
This allows organizations to control which identities can access cryptographic material.
 
⸻
 
Defense in Depth
Azure encryption should be understood as a layered security model.
                 Azure Data
                     │
        ┌────────────┼────────────┐
        ↓            ↓            ↓
    Data at       Data in      Key Management
      Rest         Transit
        │            │            │
        ↓            ↓            ↓
   AES / SSE      TLS / VPN     Key Vault
   TDE / Disk     SSH / SMB     CMK / HSM
   Encryption     Encryption
Multiple security controls can work together.
 
⸻
 
Encryption Across the Data Lifecycle
A complete Azure security architecture protects data at different stages.
Data Created
     ↓
Data in Transit
     ↓
Azure Service
     ↓
Data at Rest
     ↓
Backup / Archive
     ↓
Data Access
Encryption should be considered at each stage.
 
⸻
 
Encryption Technology Cheat Sheet
Technology	Protects	Main Purpose
AES	Data	Symmetric encryption
TDE	Database at rest	Encrypt database storage
Always Encrypted	Sensitive SQL values	Client-side protection
SSE	Azure Storage	Storage encryption
TLS	Network/application traffic	Secure communications
HTTPS	Web traffic	HTTP over TLS
MACsec	Network links	Link-layer encryption
SSH	Linux administration	Secure remote access
RDP/TLS	Windows administration	Secure remote access
IPsec/IKE	VPN traffic	Encrypted network tunnels
Azure Key Vault	Keys/secrets/certificates	Key and secret management
CMK	Encryption keys	Customer-controlled key management
 
⸻
 
Encryption Decision Guide
“I need to protect stored Azure data.”
Use:
Encryption at Rest
Examples:
* Storage encryption
* Disk encryption
* TDE
 
⸻
 
“I need to protect sensitive SQL values from database-side plaintext access.”
Consider:
Always Encrypted
 
⸻
 
“I need to protect traffic between applications.”
Use:
TLS / HTTPS
 
⸻
 
“I need secure remote access to Linux.”
Use:
SSH
 
⸻
 
“I need secure remote access to Windows.”
Use:
RDP with TLS
 
⸻
 
“I need an encrypted connection between on-premises and Azure.”
Use:
VPN Gateway with IPsec/IKE
 
⸻
 
“I need customer control over encryption keys.”
Use:
Customer-Managed Keys (CMK) with a supported key-management service such as Azure Key Vault.
 
⸻
 
“I need centralized key management.”
Use:
Azure Key Vault
 
⸻
 
Service-Managed Key vs Customer-Managed Key
Service-Managed Key

Azure Service
      ↓
Microsoft manages key
      ↓
Encrypted Data
versus:
Customer-Managed Key

Customer
    ↓
Azure Key Vault
    ↓
Customer controls key
    ↓
Azure Service
    ↓
Encrypted Data
Easy Memory
SMK
= Microsoft controls

CMK
= Customer controls
 
⸻
 
Client-Side vs Server-Side Encryption
CLIENT-SIDE

Application
    ↓
Encrypt
    ↓
Azure
    ↓
Encrypted Data
SERVER-SIDE

Application
    ↓
Azure Service
    ↓
Encrypt
    ↓
Encrypted Data
Easy Memory
Client-side = encrypted before Azure receives the data. Server-side = Azure service performs the encryption.
 
⸻
 
Common Mistakes
Mistake 1: Thinking ExpressRoute Automatically Provides IPsec Encryption
ExpressRoute provides private connectivity, but it does not automatically mean IPsec encryption.
ExpressRoute
= Private connectivity

IPsec
= VPN encryption
 
⸻
 
Mistake 2: Confusing TDE with Always Encrypted
TDE
= Protect database storage

Always Encrypted
= Protect sensitive values from database-side plaintext access
 
⸻
 
Mistake 3: Confusing Encryption with Key Management
Encryption protects data.
Key management protects and controls the keys used for encryption.
Encryption
= Protect the data

Key Management
= Protect and control the keys
 
⸻
 
Mistake 4: Assuming All Azure Services Use Exactly the Same Encryption Implementation
Azure services can implement encryption differently.
Always verify the specific service documentation when exact algorithms, key types, protocols, or configuration requirements matter.
 
⸻
 
Exam and Interview Key Takeaways
What is Data at Rest?
Data stored on disks, databases, storage services, backups, and other persistent storage.
What is Data in Transit?
Data moving between users, applications, services, networks, or datacenters.
What is TDE?
Transparent Data Encryption protects database data at rest.
What is Always Encrypted?
A client-side SQL encryption technology designed to protect sensitive values from unauthorized database-side access.
What is CMK?
A customer-managed encryption key that gives the customer greater control over key lifecycle and usage.
What is Azure Key Vault?
A managed service for securely storing and managing keys, secrets, and certificates.
What is TLS?
A security protocol used to protect communications with confidentiality, integrity, and authentication.
What is IPsec?
A protocol suite used to secure network traffic, commonly used by VPNs.
What is MACsec?
A Layer 2 encryption technology used to protect supported network links.
 
⸻
 
🧠 Easy Memory Formula
AZURE ENCRYPTION
│
├── AT REST
│   ├── AES
│   ├── TDE
│   ├── Disk Encryption
│   └── Storage Encryption
│
├── IN TRANSIT
│   ├── TLS / HTTPS
│   ├── SSH
│   ├── RDP / TLS
│   ├── IPsec / IKE
│   └── MACsec
│
└── KEY MANAGEMENT
    ├── Key Vault
    ├── SMK
    ├── CMK
    ├── BYOK
    └── HSM
 
⸻
 
Quick Exam Cheat Sheet
Question:
"Protect stored Azure data."
→ Encryption at Rest

Question:
"Encrypt Azure SQL database files."
→ TDE

Question:
"Protect sensitive SQL values from database-side plaintext access."
→ Always Encrypted

Question:
"Encrypt Azure Storage data."
→ Storage Service Encryption

Question:
"Protect web/application traffic."
→ TLS / HTTPS

Question:
"Secure Linux remote administration."
→ SSH

Question:
"Secure Windows remote administration."
→ RDP / TLS

Question:
"Create an encrypted Azure-to-on-premises tunnel."
→ VPN Gateway + IPsec/IKE

Question:
"Protect supported network links."
→ MACsec

Question:
"Customer controls encryption keys."
→ Customer-Managed Keys

Question:
"Centralized key and secret management."
→ Azure Key Vault
 
⸻
 
Final Takeaway
Azure encryption protects data at rest, data in transit, and the cryptographic keys used to protect that data. Azure provides built-in encryption for many services, while technologies such as TLS, HTTPS, IPsec, SSH, RDP/TLS, and MACsec protect data in transit. Azure Key Vault provides centralized management of keys, secrets, and certificates, while Customer-Managed Keys provide greater control over encryption-key lifecycle and access.
Golden Rule
DATA AT REST
      ↓
Protect Stored Data

DATA IN TRANSIT
      ↓
Protect Moving Data

KEY MANAGEMENT
      ↓
Protect the Keys

AZURE KEY VAULT
      ↓
Centralize Key Management

CMK
      ↓
Customer Controls the Key
Encryption = Protect the data. Key Management = Protect and control the keys.
