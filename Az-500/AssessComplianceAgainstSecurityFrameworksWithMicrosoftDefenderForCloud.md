Assess Compliance Against Security Frameworks with Microsoft Defender for Cloud
Quick Summary
Regulatory Compliance in Microsoft Defender for Cloud helps organizations assess their cloud environments against supported security standards, regulatory requirements, and benchmarks.
Think of it as a:
🏢 Security Auditor Dashboard
It helps answer:
* Are our resources meeting the required security controls?
* Which controls are failing?
* Which resources are affected?
* What should we fix?
* What evidence or attestation is required?
The basic process is:
Security Standard
       ↓
Controls
       ↓
Assessments
       ↓
Compliance Results
       ↓
Recommendations
       ↓
Remediation
 
⸻
 
1. What Is Regulatory Compliance?
Regulatory Compliance is a capability in Defender for Cloud that helps organizations monitor their compliance posture against supported standards and benchmarks.
Examples include:
Microsoft Cloud Security Benchmark (MCSB)
NIST
CIS
PCI DSS
ISO/IEC 27001
SOC 2
The exact standards available depend on the cloud environment and current Defender for Cloud offerings.
Defender for Cloud continuously assesses resources against assigned standards and shows compliant and non-compliant results. (Microsoft Learn⁠)
 
⸻
 
2. Why Is Regulatory Compliance Important?
Organizations may need to demonstrate compliance with security or industry requirements.
For example:
Organization
     |
     +-- Security requirements
     |
     +-- Industry requirements
     |
     +-- Regulatory requirements
     |
     +-- Internal policies
Without a centralized system, security teams would have to manually inspect large numbers of resources.
Defender for Cloud helps automate the technical assessment process.
Example
PCI DSS Requirement
        ↓
Assess Azure resources
        ↓
Find failing controls
        ↓
Identify affected resources
        ↓
Provide remediation guidance
Important: Defender for Cloud helps assess technical controls. It does not automatically make an organization legally compliant with a regulation.
 
⸻
 
3. Microsoft Cloud Security Benchmark (MCSB)
The Microsoft Cloud Security Benchmark (MCSB) is Microsoft’s cloud security benchmark.
When Defender for Cloud is enabled for an Azure subscription, MCSB automatically starts assessing resources in scope. Microsoft describes MCSB as building on the security principles of the Azure Security Benchmark and providing technical implementation guidance for Azure and other supported cloud environments. (Microsoft Learn⁠)
Memory
MCSB = Microsoft’s cloud security baseline
 
⸻
 
4. MCSB Is Not the Same as Every External Framework
Do not memorize that MCSB is simply a combination of NIST + CIS + PCI DSS.
A better way to remember it is:
MCSB
 =
Microsoft's cloud security benchmark
It provides Microsoft-specific cloud security guidance and mappings that can help organizations address common security and compliance requirements.
External frameworks such as:
NIST
ISO 27001
PCI DSS
CIS
remain separate standards that can also be assessed when supported and assigned.
 
⸻
 
5. Regulatory Compliance Dashboard
A typical navigation path is:
Azure Portal
    ↓
Microsoft Defender for Cloud
    ↓
Regulatory Compliance
The dashboard provides information such as:
* Assigned compliance standards
* Compliance controls
* Assessment status
* Passed assessments
* Failed assessments
* Affected resources
* Recommendations
* Manual assessments and attestations
* Compliance reports
Microsoft currently describes the dashboard as the place where organizations can manage compliance requirements and review automatic, manual, and shared-responsibility assessments. (Microsoft Learn⁠)
 
⸻
 
6. Compliance Standards → Controls → Assessments
This relationship is extremely important for exams.
Compliance Standard
        ↓
Controls
        ↓
Assessments
        ↓
Resources
        ↓
Compliance Result
Example
Standard:
NIST

        ↓

Control:
Protect Data

        ↓

Assessment:
Are VM disks appropriately encrypted?

        ↓

Resource:
VM01

        ↓

Result:
Failed
Defender for Cloud can then provide a recommendation for addressing the issue.
 
⸻
 
7. What Is a Compliance Control?
A control represents a security requirement within a standard.
For example:
PCI DSS
   |
   +-- Protect sensitive payment information
or:
NIST
   |
   +-- Protect data
A control can contain one or more assessments.
 
⸻
 
8. What Is an Assessment?
An assessment checks whether a specific requirement is being met.
Example:
Control:
Data Protection

        ↓

Assessment:
VM disks must be encrypted

        ↓

VM01:
Encryption not configured

        ↓

Result:
❌ Failed
After remediation:
Enable encryption
        ↓
Assessment runs again
        ↓
✅ Passed
 
⸻
 
9. Automated Assessments
An automated assessment can be evaluated by Defender for Cloud using available resource and configuration information.
Examples may include checks for:
* Encryption
* Network configuration
* Identity/security configuration
* Vulnerabilities
* Public exposure
* Security configurations
Example:
Policy / Security Control
        ↓
Resource configuration
        ↓
Automated assessment
        ↓
Pass / Fail
No manual attestation is required for the technical check itself.
 
⸻
 
10. Manual Assessments
Some requirements cannot be verified automatically because they involve organizational processes, documentation, or evidence.
Examples:
Security awareness training
Security policies
Risk-management procedures
Internal processes
Organizational controls
For these assessments, the customer may need to provide an attestation and supporting evidence.
Example:
Requirement:
Employees receive security awareness training.

        ↓

Microsoft cannot directly verify
your internal training program.

        ↓

Customer provides:
- Attestation
- Comments
- Supporting evidence
Microsoft’s current documentation explicitly supports manual attestation and attaching evidence for these assessments. (Microsoft Learn⁠)
 
⸻
 
11. Automated vs Manual Assessments
Automated	Manual
Evaluated using available technical data	Requires customer input
Resource/configuration based	Organization/process based
Encryption checks	Training documentation
Network configuration checks	Security policy evidence
Vulnerability checks	Internal procedure evidence
Can produce remediation recommendations	Can require attestation/evidence
Memory
Automated = Defender checks
Manual    = Customer proves
 
⸻
 
12. Investigating a Compliance Issue
Suppose a compliance control has failed.
A typical investigation flow is:
Defender for Cloud
       ↓
Regulatory Compliance
       ↓
Select Standard
       ↓
Select Control
       ↓
Control Details
The control details provide different types of information.
 
⸻
 
13. Control Details
Microsoft currently documents three important areas:
Overview
Explains:
* What the control is
* Why it matters
* Compliance information
* Relevant requirements
Your Actions
Shows actions that the customer may need to perform.
Examples:
Enable encryption
Restrict network access
Configure security controls
Remediate affected resources
Microsoft Actions
Shows actions Microsoft performs as part of the shared responsibility model.
Examples can include:
* Platform security
* Infrastructure protections
* Microsoft service controls
* Relevant Microsoft certifications
Microsoft documents these three views as Overview, Your Actions, and Microsoft Actions. (Microsoft Learn⁠)
 
⸻
 
14. Remediating an Automated Assessment
Suppose Defender for Cloud identifies:
VM01
  ↓
Disk encryption requirement
  ↓
❌ Assessment failed
A typical process is:
Open failed assessment
        ↓
Review recommendation
        ↓
Select affected resource
        ↓
Review remediation guidance
        ↓
Take Action
        ↓
Fix resource
        ↓
Wait for reassessment
For example:
Problem:
VM disk is not encrypted.

        ↓

Action:
Enable the required encryption configuration.

        ↓

Reassessment:

✅ Assessment passes
Defender for Cloud provides remediation information for failing automated assessments. (Microsoft Learn⁠)
 
⸻
 
15. Remediating a Manual Assessment
For a manual assessment:
Regulatory Compliance
        ↓
Select Standard
        ↓
Select Control
        ↓
Manual Attestation / Evidence
        ↓
Select Assessment
        ↓
Select Subscription
        ↓
Attest
        ↓
Add Information
        ↓
Attach Evidence
        ↓
Save
Examples of evidence might include:
* Security policies
* Audit reports
* Training records
* Internal procedures
* Other relevant documentation
The exact evidence required depends on the assessment.
 
⸻
 
16. Assessment Timing
Important Exam Point ⚠️
Compliance results do not necessarily update immediately after you fix a resource.
Microsoft currently states that regulatory compliance assessments run approximately every 12 hours. Therefore, after remediation, you may need to wait for the next assessment cycle before the dashboard reflects the change. (Microsoft Learn⁠)
Memory
Fix resource
     ↓
Wait for assessment
     ↓
Compliance result updates
Exam memory: Regulatory Compliance assessments ≈ 12-hour cycle.
This is different from assuming every Defender for Cloud assessment across every feature and cloud has exactly the same refresh interval.
 
⸻
 
17. Azure, AWS, and GCP
Defender for Cloud supports multicloud compliance assessment for supported Azure, AWS, and GCP environments.
Standards and default benchmarks vary by cloud.
For example:
Azure
  ↓
MCSB

AWS
  ↓
AWS-specific default benchmarks
  ↓
Additional supported standards

GCP
  ↓
GCP-specific default benchmarks
  ↓
Additional supported standards
Microsoft documents separate default benchmarks for AWS and GCP, so do not assume that the exact Azure MCSB setup is identical across all clouds. (Microsoft Learn⁠)
 
⸻
 
18. Defender for Cloud + Microsoft Purview Compliance Manager
Defender for Cloud can integrate with Microsoft Purview Compliance Manager.
Think of the difference as:
Defender for Cloud
        ↓
Cloud security posture
        ↓
Cloud resource compliance

Purview Compliance Manager
        ↓
Organization-wide compliance management
        ↓
Broader digital estate
Compliance data from Defender for Cloud can be surfaced in Compliance Manager, providing a more centralized view of compliance across the organization’s digital estate. (Microsoft Learn⁠)
Simple Memory
Defender for Cloud = Cloud security and resource assessments Purview Compliance Manager = Broader compliance management
 
⸻
 
19. Compliance Does Not Mean “100% Secure”
This is an important security concept.
Compliance
     ≠
Complete Security
Compliance means that defined requirements are being met.
Security is broader and includes:
* Threat detection
* Vulnerability management
* Identity security
* Network security
* Data protection
* Incident response
* Continuous monitoring
An organization can satisfy a particular compliance requirement and still have other security risks.
 
⸻
 
20. How to Improve Compliance Posture
Use this process:
1. Review standards
        ↓
2. Identify failed controls
        ↓
3. Investigate assessments
        ↓
4. Remediate technical issues
        ↓
5. Provide evidence for manual controls
        ↓
6. Wait for reassessment
        ↓
7. Review updated compliance posture
Easy Memory
CHECK → FIX → PROVE → RECHECK
 
⸻
 
21. Exam & Interview Questions
Q1. What is the purpose of Regulatory Compliance in Defender for Cloud?
Answer:
It helps organizations assess and monitor their cloud security posture against supported security standards, regulatory requirements, and benchmarks.
 
⸻
 
Q2. What standard automatically starts assessing Azure resources when Defender for Cloud is enabled?
Answer:
Microsoft Cloud Security Benchmark (MCSB). (Microsoft Learn⁠)
 
⸻
 
Q3. What is the difference between a compliance standard and a control?
Answer:
Standard = Overall framework
Control  = Specific requirement within that framework
Example:
PCI DSS
   ↓
Data Protection Control
 
⸻
 
Q4. What is the difference between a control and an assessment?
Answer:
Control    = What security requirement must be met?
Assessment = Is this requirement currently being met?
 
⸻
 
Q5. What is the difference between automated and manual assessments?
Answer:
Automated = Defender evaluates technical information
Manual    = Customer provides attestation/evidence
 
⸻
 
Q6. How do you remediate an automated assessment?
Answer:
Review the failing assessment, follow its recommendation, fix the affected resource, and wait for the next assessment cycle.
 
⸻
 
Q7. How do you handle a manual assessment?
Answer:
Provide the required customer attestation and supporting evidence through the Regulatory Compliance experience.
 
⸻
 
Q8. How often do regulatory compliance assessments run?
Answer:
Approximately every 12 hours according to the current Microsoft documentation. (Microsoft Learn⁠)
 
⸻
 
Q9. Can Defender for Cloud assess AWS and GCP?
Answer:
Yes. Defender for Cloud supports multicloud security and compliance assessment for supported AWS and GCP environments, with cloud-specific default benchmarks and additional standards. (Microsoft Learn⁠)
 
⸻
 
Q10. What is the relationship between Defender for Cloud and Purview Compliance Manager?
Answer:
Compliance data from Defender for Cloud can be surfaced in Microsoft Purview Compliance Manager, providing a more centralized organization-wide compliance view. (Microsoft Learn⁠)
 
⸻
 
22. One-Minute Revision
                 Regulatory Compliance
                         |
                         v
                Select Standard
                         |
                         v
                     Controls
                         |
                         v
                    Assessments
                    /          \
                   /            \
            Automated          Manual
                |                 |
         Defender checks     Customer attests
                |                 |
                +--------+--------+
                         |
                         v
                 Compliance Result
                         |
                         v
                  Recommendations
                         |
                         v
                    Remediation
                         |
                         v
                   Reassessment
Core Memory Table
Term	Remember
Regulatory Compliance	Assess compliance against supported standards
MCSB	Microsoft’s cloud security benchmark
Standard	Overall security/compliance framework
Control	Specific requirement
Assessment	Test of a control
Automated Assessment	Defender evaluates technical information
Manual Assessment	Customer provides attestation/evidence
Recommendation	Guidance for remediation
Control Details	Overview + Your Actions + Microsoft Actions
Reassessment	Compliance results update after assessment runs
~12 hours	Current documented Regulatory Compliance assessment cycle
Purview Compliance Manager	Broader compliance management
 
⸻
 
23. Easy Exam Memory Trick
Think:
CHECK → FIX → PROVE → RECHECK
CHECK
Review:
Standards
Controls
Assessments
FIX
Remediate failing automated assessments.
PROVE
Provide evidence and attest to manual assessments.
RECHECK
Wait for the next assessment cycle and review the updated compliance results.
 
⸻
 
Golden Rule
Microsoft Defender for Cloud Regulatory Compliance uses standards, controls, and assessments to evaluate cloud security posture. Automated assessments check technical configurations, while manual assessments require customer attestation and evidence. Failed assessments lead to remediation guidance, and compliance results are updated when the relevant assessments run again.
This version corrects the main potentially confusing point in the original notes: MCSB should be remembered as Microsoft’s own cloud security benchmark, not simply as a combination of NIST/CIS/PCI DSS. It also distinguishes the Azure MCSB behavior from the cloud-specific default benchmarks used for AWS and GCP. 
