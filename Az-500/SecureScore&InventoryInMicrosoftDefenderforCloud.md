Secure Score & Inventory in Microsoft Defender for Cloud
Quick Summary
Microsoft Defender for Cloud provides two useful ways to understand your cloud environment:
Secure Score → How secure is my environment?
Inventory    → What resources do I have?
Think of it like this
Secure Score
     ↓
Measure security posture
     ↓
Find weaknesses
     ↓
Prioritize improvements

Inventory
     ↓
See cloud resources
     ↓
View security state
     ↓
Investigate resources
 
⸻
 
1. What Is Secure Score?
Secure Score is a security posture measurement in Microsoft Defender for Cloud.
It helps you understand how well your environment meets recommended security practices and where improvements can increase your security posture.
Think of it as a security report card:
Higher Secure Score
        ↓
More recommended security improvements completed

Lower Secure Score
        ↓
More recommended improvements remain
Important: Secure Score is a security posture metric. It is not a percentage guarantee that an environment is secure.
 
⸻
 
2. Why Is Secure Score Important?
Secure Score helps security teams:
* Understand their current security posture
* Identify security weaknesses
* Prioritize recommendations
* Track improvement over time
* Focus on high-impact security controls
Example:
Before remediation
      ↓
Many unresolved recommendations
      ↓
Lower Secure Score

After remediation
      ↓
Fewer unresolved recommendations
      ↓
Higher Secure Score
 
⸻
 
3. What Does Defender for Cloud Analyze?
Defender for Cloud can evaluate security posture across supported cloud resources such as:
* Virtual machines
* Storage accounts
* Databases
* Containers
* Networking resources
* Identity and access configurations
* Other supported cloud resources
Example:
Azure Environment
      |
      +-- VM
      +-- Storage
      +-- Database
      +-- Network
      +-- Containers
             |
             v
      Defender for Cloud
             |
             v
       Recommendations
             |
             v
        Secure Score
 
⸻
 
4. Security Recommendations
Defender for Cloud generates security recommendations when it identifies security improvements that should be made.
Examples:
Enable endpoint protection
Apply missing security updates
Restrict management ports
Enable MFA
Enable vulnerability assessment
Protect storage from public exposure
A recommendation normally explains:
* What is wrong
* Which resources are affected
* Why it matters
* How to remediate it
 
⸻
 
5. Security Controls
Recommendations are grouped into Security Controls.
A security control represents a related group of security recommendations.
Example:
Security Control:
Secure Management Ports
        |
        +-- Restrict RDP access
        +-- Restrict SSH access
        +-- Use Just-In-Time VM access
Another example:
Security Control:
Remediate Vulnerabilities
        |
        +-- Install security updates
        +-- Address software vulnerabilities
        +-- Remediate vulnerable resources
Memory
Security Control = Group of related recommendations
 
⸻
 
6. Secure Score and Security Controls
Secure Score is calculated from security controls and their recommendations.
A security control can have:
* Maximum possible score
* Current score
* Potential score increase
Conceptually:
Security Control
      |
      +-- Healthy resources
      |
      +-- Unhealthy resources
      |
      v
Control Score
      |
      v
Secure Score
 
⸻
 
7. Important Secure Score Calculation Concept
A common misunderstanding is:
“If I fix one recommendation, I always receive the points immediately.”
That is not necessarily correct.
The scoring behavior depends on the specific security control and its recommendations.
For many resource-based controls, the score reflects the proportion of resources that satisfy the control’s requirements rather than simply counting individual recommendations.
Example
Suppose a control evaluates four resources:
VM01 → Healthy
VM02 → Healthy
VM03 → Unhealthy
VM04 → Unhealthy
The control’s score reflects the healthy/unhealthy resource calculation.
Do not memorize:
“Every recommendation must be fixed before any points are awarded.”
Instead remember:
Secure Score is calculated from the health of resources against security controls and their associated recommendations.
This distinction is important for AZ-500-style questions.
 
⸻
 
8. Maximum Score
Each security control contributes a defined number of points to the overall Secure Score.
For example:
Security Control
      |
      +-- Maximum score = 10
The maximum score represents the maximum contribution available from that control.
The exact scoring model and weighting are determined by Microsoft and can change over time.
Exam memory: Maximum score = maximum points available for the control.
 
⸻
 
9. Current Score
The current score represents the points currently earned based on the health of the resources evaluated by the control.
Conceptually:
Healthy resources
        ↓
Earned points
        ↓
Current score
Example:
Security Control
Maximum = 10 points

Current health
        ↓
Current score = 6 points
The exact calculation depends on the control.
 
⸻
 
10. Potential Score Increase
The potential score increase represents the improvement available if the remaining unhealthy resources are remediated.
Example:
Current Score
      ↓
      6

Potential Increase
      ↓
      +4

Maximum
      ↓
      10
Conceptually:
Current Score + Potential Increase
                    =
              Maximum Score
for a fully remediable control.
 
⸻
 
11. Preview Recommendations
Not every recommendation necessarily contributes to Secure Score.
Microsoft can introduce recommendations in Preview before they become generally available.
Important exam concept
Preview recommendations may be excluded from Secure Score calculations until they become generally available.
Therefore:
Preview Recommendation
        ↓
Still useful to investigate
        ↓
May not contribute to Secure Score
Memory: Preview ≠ necessarily scored.
Always verify the current Microsoft documentation when a question depends on the exact scoring status of a recommendation.
 
⸻
 
12. How to Improve Secure Score
There are several ways to remediate Defender for Cloud recommendations.
Option 1 — Fix Manually
Review the recommendation and make the required configuration change yourself.
Example:
Recommendation:
Enable MFA

        ↓

Configure appropriate
Microsoft Entra authentication controls

        ↓

Reassessment
        ↓
Security posture improves
 
⸻
 
Option 2 — Use “Fix”
Some Defender for Cloud recommendations provide automated remediation through a Fix or equivalent remediation action.
Example:
Recommendation
      ↓
Fix
      ↓
Required configuration applied
      ↓
Reassessment
The exact availability of automated remediation depends on the recommendation.
 
⸻
 
Option 3 — Use Enforce
Enforce uses Azure Policy capabilities to help ensure that required configurations remain compliant.
Example:
Requirement:
Storage resources must meet encryption requirements.

        ↓

Azure Policy
        ↓
Enforce requirement
        ↓
Resources remain compliant
Enforcement behavior depends on the policy definition and effect.
 
⸻
 
Option 4 — Use Deny
The Azure Policy Deny effect can prevent a deployment or update that violates a defined policy.
Example:
User deploys non-compliant resource
             ↓
         Azure Policy
             ↓
           Deny
             ↓
     Deployment blocked
Important distinction
Fix       → Remediate an existing issue
Enforce   → Help maintain required configuration
Deny      → Prevent non-compliant operations
These are Azure Policy/remediation concepts and should not be treated as interchangeable Secure Score features.
 
⸻
 
13. Secure Score Example
Imagine an environment contains:
VM01 → Missing security updates
VM02 → Secure
VM03 → Publicly exposed management port
Storage01 → Public access enabled
Defender for Cloud evaluates the environment:
Resources
    ↓
Security Assessments
    ↓
Recommendations
    ↓
Security Controls
    ↓
Secure Score
The administrator then remediates the issues:
Missing updates
       ↓
Apply updates

Public management port
       ↓
Restrict access

Public storage
       ↓
Remove unnecessary public access
After reassessment, the security posture can improve.
 
⸻
 
14. What Is Inventory?
Inventory provides a centralized view of resources and their security-related information.
Think of Inventory as:
“What’s in my cloud?”
It helps you discover and investigate resources across supported environments.
Example:
Inventory
   |
   +-- Virtual Machines
   +-- Storage Accounts
   +-- Databases
   +-- Containers
   +-- Networking Resources
   +-- Other supported resources
 
⸻
 
15. What Information Can Inventory Show?
Inventory can help you understand:
What resources exist?
20 Virtual Machines
10 Storage Accounts
5 Databases
Which resources have security issues?
VM01 → Missing updates
VM02 → Vulnerabilities
Storage01 → Public exposure
Which resources have Defender protection?
For example:
VM01
Defender for Servers → Enabled

VM02
Defender for Servers → Not enabled
The exact columns and filtering options depend on the resource type and current Defender for Cloud experience.
 
⸻
 
16. Why Is Inventory Useful?
Inventory provides a centralized way to investigate cloud assets and their security state.
It helps answer:
What resources do we have?
        ↓
Which resources are affected?
        ↓
Which recommendations apply?
        ↓
Which resources have Defender coverage?
        ↓
What should we investigate?
This is especially useful in large environments where manually checking individual subscriptions and resources would be inefficient.
 
⸻
 
17. Secure Score vs Inventory
This is one of the most important distinctions to remember.
Feature	Main Question	Purpose
Secure Score	How secure is my environment?	Measure security posture and track improvements
Inventory	What resources do I have?	Discover and investigate resources
Recommendations	What should I fix?	Identify security improvements
Security Controls	What security area needs attention?	Group related recommendations
Regulatory Compliance	Do we meet defined standards?	Assess compliance
Easy memory
Secure Score → How secure am I?
Inventory    → What do I have?
Recommendations → What should I fix?
Compliance   → Do I meet the standard?
 
⸻
 
18. Secure Score vs Regulatory Compliance
These two concepts are easy to confuse.
Secure Score
Focuses on:
Security posture
      ↓
Security recommendations
      ↓
Security controls
      ↓
Score
Regulatory Compliance
Focuses on:
Security standard
      ↓
Controls
      ↓
Assessments
      ↓
Compliance status
Memory
Secure Score = Security posture Regulatory Compliance = Compliance against a standard
 
⸻
 
19. Inventory Example
Imagine a company has:
Subscription A
    |
    +-- VM01
    +-- VM02
    +-- Storage01

Subscription B
    |
    +-- VM03
    +-- SQL01
    +-- Container01
Inventory gives the security team a centralized way to investigate these resources.
For example:
Inventory
    |
    +-- VM01 → Healthy
    +-- VM02 → Vulnerabilities
    +-- VM03 → Defender coverage missing
    +-- Storage01 → Public exposure
    +-- SQL01 → Recommendation
    +-- Container01 → Security finding
The administrator can then investigate the relevant resources and recommendations.
 
⸻
 
20. Common Interview & Exam Questions
Q1. What is Secure Score?
Answer:
Secure Score is a security posture measurement in Microsoft Defender for Cloud that helps organizations understand their security posture and prioritize security improvements.
 
⸻
 
Q2. How can you improve Secure Score?
Answer:
Review and remediate Defender for Cloud security recommendations, using manual remediation or available automated remediation capabilities.
 
⸻
 
Q3. What is a Security Control?
Answer:
A Security Control is a group of related security recommendations focused on a particular security objective.
 
⸻
 
Q4. What is Inventory?
Answer:
Inventory provides a centralized view for discovering and investigating cloud resources and their security-related information.
 
⸻
 
Q5. What is the difference between Secure Score and Inventory?
Answer:
Secure Score = Measure security posture
Inventory    = Discover and investigate resources
 
⸻
 
Q6. Do Preview recommendations affect Secure Score?
Answer:
Preview recommendations may be excluded from Secure Score calculations until they become generally available.
 
⸻
 
Q7. Does fixing one recommendation always give you the full control score?
Answer:
No. Secure Score is calculated according to the scoring model of the security control and the health of the resources it evaluates. Do not assume that each individual recommendation corresponds to a fixed number of points.
 
⸻
 
Q8. What is the difference between Fix and Deny?
Answer:
Fix  → Remediates an existing issue where supported.

Deny → Azure Policy effect that can prevent
       non-compliant operations.
 
⸻
 
Q9. What is the purpose of Inventory?
Answer:
To provide centralized visibility into cloud resources and help security teams investigate their security state, recommendations, and Defender coverage.
 
⸻
 
21. One-Minute Revision
                    Defender for Cloud
                           |
          +----------------+----------------+
          |                |                |
          v                v                v
     Secure Score     Recommendations    Inventory
          |                |                |
          |                |                |
   How secure?       What should I fix?   What do I have?
          |                |
          v                v
   Security Controls   Remediation
          |
          v
    Security Posture
Key Terms
Term	Memory
Secure Score	Measure security posture
Security Control	Group of related recommendations
Recommendation	Security improvement to investigate/remediate
Maximum Score	Maximum points available for a control
Current Score	Points currently earned
Potential Increase	Remaining score improvement
Preview	May not contribute to Secure Score
Fix	Remediate supported issues
Enforce	Use policy to maintain required configuration
Deny	Block non-compliant operations
Inventory	Discover and investigate resources
 
⸻
 
22. Easy Memory Trick
Think:
SECURE SCORE = "How secure am I?"
INVENTORY    = "What's in my cloud?"
Or:
                 Defender for Cloud
                        |
          +-------------+-------------+
          |             |             |
          v             v             v
      Inventory     Recommendations  Secure Score
          |             |             |
      What do I      What should     How secure
       have?          I fix?           am I?
 
⸻
 
