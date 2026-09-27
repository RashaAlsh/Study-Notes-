

Azure Key Vault — Configure Key Rotation

1. What Is Key Rotation?

Key rotation means creating a new version of an existing Key Vault key with new cryptographic material.

Example

CustomerKey v1

      ↓

CustomerKey v2

      ↓

CustomerKey v3

The key name stays the same, while Azure creates a new key version.

Exam Memory:

Key Rotation = New Version of the Same Key

⸻

2. Why Rotate Keys?

Regular key rotation is a security best practice because it can:

* Reduce the impact of a compromised key

* Support compliance requirements

* Improve cryptographic hygiene

* Provide automated key lifecycle management

The exact rotation interval should be based on the organization’s security policy, compliance requirements, and the current Microsoft guidance for the specific workload.

Important: Do not treat 730 days / 2 years as a universal Azure Key Vault requirement. Rotation periods are configurable and can depend on organizational or service requirements.

⸻

3. Automatic Key Rotation

Azure Key Vault can automatically rotate supported keys according to a rotation policy.

Simplified flow

Azure Service

     |

     | Customer-Managed Key

     v

Azure Key Vault

     |

     | Rotation Policy

     v

New Key Version

For supported scenarios, this allows organizations to reduce manual key-management work.

Example

AppKey v1

   |

   | Automatic rotation

   v

AppKey v2

   |

   | Automatic rotation

   v

AppKey v3

Memory:

Automatic Rotation = Key Vault creates new key versions according to policy.

⸻

4. Key Rotation Policy

A rotation policy defines how the key lifecycle should be managed.

A policy can include settings related to:

* Rotation frequency

* Key expiration

* Rotation before expiration

* Expiration notifications

Each key can have its own rotation policy.

Concept

Rotation Policy

      |

      +-- Rotation schedule

      |

      +-- Expiration

      |

      +-- Pre-expiration rotation

      |

      +-- Notification

⸻

5. Expiration Time

The expiration setting determines when a key version expires.

For example:

Key Version

    |

    | Valid

    |

    v

Expiration Date

An expiration policy can be used together with rotation to manage the key lifecycle.

Important:

Expiration and rotation are related but are not the same thing.

* Rotation → creates a new key version.

* Expiration → makes a key version no longer valid after its expiration time.

⸻

6. Rotation Schedule

A rotation policy can specify how frequently new key versions should be created.

Conceptually:

Key v1

  |

  | Rotation interval

  v

Key v2

  |

  | Rotation interval

  v

Key v3

The exact minimum and maximum values supported by Azure Key Vault can change, so check the current Microsoft documentation when an exact limit is required.

Exam Tip:

Focus on the concept: the rotation policy controls when new versions are created.

⸻

7. Rotate Before Expiration

A rotation policy can also be designed to rotate a key before the current version expires.

Example

Key expiration

      |

      |<--- 30 days --->|

      |

      v

Expiration date

The service can create a new version before the existing version reaches its expiration date.

This helps avoid situations where a key reaches expiration without a replacement being available.

⸻

8. Notification Before Expiration

Key Vault rotation policies can include notification settings for upcoming expiration.

Example

Key Expiration

     ^

     |

Notification

     |

30 days before

Notifications can be integrated with Azure eventing and automation capabilities, such as Azure Event Grid, depending on the scenario.

Possible uses

* Notify administrators

* Trigger automation

* Start a custom rotation workflow

* Alert teams about expiring keys

Memory:

Rotation creates a new version. Notification warns that a key is approaching expiration.

⸻

9. What Happens During Rotation?

Suppose the vault contains:

EncryptionKey

     |

     +-- v1  ← Current

After rotation:

EncryptionKey

     |

     +-- v1

     |

     +-- v2  ← New version

Important points

* The key name remains the same.

* A new version is created.

* The new version contains new cryptographic material.

* Older versions can remain available for operations that still require them.

Exam Memory:

Rotation does NOT mean creating a completely different key name.

⸻

10. Versionless vs Versioned Key URI

This is an important Azure concept.

Versionless Key URI

Example:

https://contoso-kv.vault.azure.net/keys/AppKey

A versionless reference identifies the key without specifying a particular version.

This can allow supported Azure services to use the current/latest key version according to their integration behavior.

Memory

Versionless URI = Key without specifying a version

⸻

Versioned Key URI

Example:

https://contoso-kv.vault.azure.net/keys/AppKey/123456789

This explicitly identifies a particular key version.

Memory

Versioned URI = Exact key version

⸻

11. Why Versioning Matters

Imagine:

AppKey

  |

  +-- v1

  +-- v2

  +-- v3

If an application references:

/keys/AppKey/v1

it explicitly references v1.

If it references:

/keys/AppKey

it does not specify a particular version.

This distinction is important when designing applications and Azure services that use customer-managed keys.

Important:

Whether a specific Azure service automatically follows a newly rotated key version depends on that service’s CMK integration. Do not assume that every service behaves identically.

⸻

12. Customer-Managed Keys (CMK)

Key rotation is commonly used with Customer-Managed Keys.

Architecture

Azure Service

      |

      | Customer-Managed Key

      v

Azure Key Vault

      |

      v

Key Version

      |

      | Rotation Policy

      v

New Key Version

Examples of Azure services that can use customer-managed keys include services such as:

* Azure Storage

* Azure SQL

* Azure Managed Disks

The exact rotation behavior and requirements depend on the service.

⸻

13. Event Grid and Key Expiration

Azure Event Grid can be used to react to Key Vault events, including relevant key lifecycle events.

Example automation

Key Approaching Expiration

          |

          v

      Event Grid

          |

     +----+----+

     |         |

     v         v

  Alert     Automation

               |

               v

        Custom Workflow

Use cases

* Notify security administrators

* Trigger an Azure Function

* Start a custom automation workflow

* Integrate with an incident-management system

Memory:

Event Grid = React to Key Vault events.

⸻

14. Imported Keys and Special Scenarios

Not every key-management scenario can use the same automatic rotation mechanism.

For example, organizations may have keys that originate outside Azure or have special lifecycle requirements.

In such cases, event-driven notifications and custom automation can help administrators manage the lifecycle.

Concept

Key Expiration Event

        |

        v

    Event Grid

        |

        v

Custom Automation

        |

        v

Replacement / Rotation Process

Exam Memory:

Automatic Key Vault rotation is not identical to every possible key lifecycle scenario.

⸻

15. Manual / On-Demand Rotation

Sometimes a key needs to be rotated immediately.

Examples

* Suspected key compromise

* Security incident

* Emergency key replacement

* Organizational security requirement

The administrator can perform an on-demand rotation using supported Azure management tools.

Azure CLI

az keyvault key rotate \

  --vault-name MyVault \

  --name MyKey

PowerShell

Invoke-AzKeyVaultKeyRotation `

  -VaultName MyVault `

  -Name MyKey

Result

MyKey v1

   |

   | Manual rotation

   v

MyKey v2

Memory:

Manual rotation = Create a new key version immediately.

⸻

16. Configure Rotation Policy

Rotation policies can be configured using Azure management tools.

Azure CLI

az keyvault key rotation-policy update \

  --vault-name MyVault \

  --name MyKey \

  --value policy.json

The policy file defines the desired lifecycle behavior.

PowerShell

Azure PowerShell also provides Key Vault commands for configuring key rotation policies.

Tip:

Command syntax and supported parameters can change between Azure CLI/PowerShell versions. For production automation, check the current Microsoft documentation.

⸻

17. Key Rotation Governance with Azure Policy

Organizations can use Azure Policy to enforce or audit key-management requirements.

For example:

Azure Policy

     |

     v

Check Key Rotation Configuration

     |

     +---- Compliant

     |

     +---- Non-Compliant

A policy can help organizations identify keys that do not meet their required rotation configuration.

Example governance requirement

Organization Policy

        |

        v

Keys must have an approved

rotation policy

        |

        v

Azure Policy evaluates resources

Memory:

Key Vault Rotation Policy = Defines how a key rotates.

Azure Policy = Governs whether resources meet organizational requirements.

⸻

18. Key Rotation vs Azure Policy

These two concepts are easy to confuse.

Feature	Purpose
Key Rotation Policy	Defines the lifecycle and rotation behavior of a key
Azure Policy	Audits/enforces organizational configuration requirements
Event Grid	Reacts to Key Vault events
Manual Rotation	Immediately creates a new key version
CMK Integration	Allows supported Azure services to use customer-controlled keys

Easy memory

Rotation Policy

      ↓

How should the key rotate?

Azure Policy

      ↓

Does the environment follow our rule?

Event Grid

      ↓

What should happen when an event occurs?

Manual Rotation

      ↓

Rotate now!

⸻

19. Required Permissions

Managing Key Vault keys requires appropriate authorization.

For role-based access control, a role such as:

Key Vault Crypto Officer

provides key-management permissions for supported cryptographic operations and lifecycle management.

The exact permissions available depend on the Key Vault authorization model and role definition.

Exam Memory:

Crypto Officer → Key management

Do not confuse this with roles intended primarily for:

* Reading secrets

* Managing vault resources

* Managing access permissions

⸻

20. End-to-End Key Rotation Architecture

                 Azure Service

                      |

                      | CMK

                      v

                Azure Key Vault

                      |

                      v

                  AppKey v1

                      |

              Rotation Policy

                      |

                      v

                  AppKey v2

                      |

              Rotation Policy

                      |

                      v

                  AppKey v3

                      |

          +-----------+-----------+

          |                       |

          v                       v

     Event Grid              Azure Policy

          |                       |

          v                       v

   Notifications /          Governance /

    Automation              Compliance

⸻

21. Common Exam Questions

Q1. What does key rotation create?

Answer:

A new version of the same key containing new cryptographic material.

⸻

Q2. Does key rotation change the key name?

Answer:

No.

The key name remains the same while the version changes.

⸻

Q3. What is the difference between rotation and expiration?

Answer:

* Rotation → creates a new key version.

* Expiration → determines when a key version is no longer valid.

⸻

Q4. What does a rotation policy define?

Answer:

It defines key lifecycle behavior such as rotation scheduling, expiration, and notifications.

⸻

Q5. What can Azure Policy do for key rotation?

Answer:

It can help organizations audit or enforce key-management requirements, such as requiring keys to have appropriate rotation policies.

⸻

Q6. What service can react to Key Vault events?

Answer:

Azure Event Grid

⸻

Q7. What is a versionless key URI?

Answer:

A key reference that identifies the key without specifying a particular version.

Example:

/keys/AppKey

⸻

Q8. What is a versioned key URI?

Answer:

A key reference that identifies a specific version.

Example:

/keys/AppKey/123456789

⸻

Q9. When might manual rotation be useful?

Answer:

During a security incident, suspected key compromise, emergency replacement, or another situation requiring immediate rotation.

⸻

Q10. What is the purpose of Event Grid in key management?

Answer:

It can deliver Key Vault events to downstream services so organizations can trigger notifications or automation.

⸻

22. Quick Exam Cheat Sheet

Key Rotation

= Create a new version of the same key

Key Name

= Stays the same

Key Version

= Changes after rotation

Rotation Policy

= Defines lifecycle/rotation behavior

Expiration

= Determines when a key version expires

Versionless URI

= /keys/AppKey

Versioned URI

= /keys/AppKey/<version>

Event Grid

= React to Key Vault events

Azure Policy

= Govern/audit rotation requirements

Manual Rotation

= Rotate immediately

CMK

= Customer-Managed Key

Crypto Officer

= Key-management role

⸻

23. The Most Important Exam Distinction

                KEY LIFECYCLE

                     |

        +------------+------------+

        |            |            |

     Rotation     Expiration   Notification

        |            |            |

        v            v            v

   New version    Version      Event / Alert

                  expires

Remember

Rotation = New Version

Expiration = Version becomes invalid

 Event Grid = React to lifecycle events

Azure Policy = Govern the configuration

⸻

24. Golden Rule

Azure Key Vault key rotation keeps the same key name but creates new cryptographic versions according to a lifecycle policy.

Final Exam Sentence

Key rotation creates a new version of an existing Key Vault key. Rotation policies define the key lifecycle, Event Grid can support event-driven notifications and automation, and Azure Policy can help govern rotation requirements.