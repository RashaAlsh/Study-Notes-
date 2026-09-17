
Microsoft Sentinel Log Retention Plans
Quick Summary
Microsoft Sentinel collects security data for:
* Threat detection
* Investigation
* Hunting
* Correlation
* Compliance
But storing and querying large amounts of data can become expensive.
The basic trade-off is:
More Security Data
       ↓
Better Visibility
       ↓
Higher Storage / Query Cost
Sentinel provides different log plans so organizations can balance security value, performance, and cost.
Memory: Important and frequently queried data → Analytics. High-volume, less frequently queried data → Auxiliary or Basic.
 
⸻
 
1. Primary vs Secondary Security Data
A useful way to understand the plans is to divide security data into two broad categories.
Primary Security Data
High-value data that security teams frequently use for detection and investigation.
Examples:
* Microsoft Defender alerts
* EDR data
* Antivirus logs
* Authentication logs
* Microsoft Entra sign-in logs
* Threat intelligence
* Cloud audit logs
Typical use:
Primary Security Data
        ↓
Threat Detection
        ↓
Hunting
        ↓
Correlation
        ↓
Investigation
Typical Plan
Analytics Logs
 
⸻
 
Secondary Security Data
Useful contextual data that may be high-volume and queried less frequently.
Examples:
* Firewall logs
* Network flow logs
* Proxy logs
* TLS/SSL logs
* Storage access logs
* IoT logs
These logs can help answer:
“What happened before and after the attack?”
Typical Plans
Auxiliary Logs or Basic Logs, depending on requirements and current feature availability.
 
⸻
 
2. Microsoft Sentinel Log Plans
The three plans to remember are:
Microsoft Sentinel
│
├── Analytics Logs
├── Auxiliary Logs
└── Basic Logs
Each plan has different capabilities, performance, and cost characteristics.
 
⸻
 
3. Analytics Logs
Purpose
Analytics Logs are designed for security data that requires strong querying and analytics capabilities.
Think:
Hot security data used by the SOC every day.
Analytics Logs
      ↓
Fast Queries
      ↓
Detection + Hunting + Investigation
Common Examples
* Entra sign-in logs
* Defender alerts
* EDR/security telemetry
* Important audit logs
Capabilities
Analytics Logs support the broadest Sentinel analytics capabilities, including:
* Analytics rules
* Hunting
* Workbooks
* Dashboards
* Interactive investigation
* UEBA-related scenarios
Interactive Retention
Your notes use:
90 days by default
Interactive retention can be extended depending on the workspace/service configuration.
Cost
Generally the most expensive of the three plans because it provides the richest analytics capabilities and fast interactive querying.
 
⸻
 
4. Auxiliary Logs
Purpose
Auxiliary Logs are intended for high-volume data that has useful security or operational context but doesn’t need the full capabilities of Analytics Logs.
Think:
Large-volume contextual data that you don’t search constantly.
Auxiliary Logs
      ↓
Large Volume
      ↓
Lower Storage Cost
      ↓
Occasional Investigation
Examples
* Firewall logs
* Proxy logs
* Network flow data
Characteristics
Compared with Analytics Logs:
* Lower cost
* More limited query capabilities
* Less suitable for real-time analytics
* Useful during investigations
Your notes identify Auxiliary Logs as a Preview capability. Preview status and exact capabilities can change, so verify current Microsoft documentation before relying on this for production architecture.
 
⸻
 
5. Basic Logs
Basic Logs provide a lower-cost option for data that doesn’t require the full capabilities of Analytics Logs.
Think:
Useful data, but not data that needs premium analytics performance.
They are commonly considered when:
* Data volume is high
* Queries are less frequent
* Cost optimization is important
* Full Analytics capabilities aren’t required
Basic Logs have more query/capability limitations than Analytics Logs.
 
⸻
 
6. Analytics vs Auxiliary vs Basic
Feature	Analytics	Auxiliary	Basic
Security value	High	Contextual	Contextual
Cost	Higher	Lower	Lower than Analytics
Query performance/capabilities	Broadest	More limited	More limited
Analytics rules	✅	Limited/Not supported for many scenarios	Limited
Frequent hunting	✅	❌	Limited
High-volume data	Possible	✅	✅
Typical use	Primary security data	Secondary/context data	Cost-sensitive data
Important: Exact query capabilities, pricing, retention, and feature availability can change. Always check the current Sentinel documentation for production decisions.
 
⸻
 
7. Interactive Retention
Interactive retention means the data is available for normal querying.
Think:
🔥 Hot data
Example:
Today's Sign-in Logs
        ↓
Interactive Retention
        ↓
Analyst searches immediately
Interactive data is where SOC analysts normally perform day-to-day investigation and hunting.
 
⸻
 
8. Long-Term Retention
Older data can be retained for longer periods at a lower storage cost.
Think:
❄️ Cold/archive data
New Logs
   ↓
Interactive Retention
   ↓
Long-Term Retention
   ↓
Historical / Compliance Data
Useful for:
* Compliance
* Auditing
* Historical investigations
* Forensics
* Regulatory requirements
Your notes use a maximum of 12 years for long-term retention. Exact retention limits and pricing should be verified against the current Microsoft Sentinel documentation.
 
⸻
 
9. Interactive vs Long-Term Retention
State	Purpose	Access
Interactive	Daily analysis and investigation	Normal queries
Long-term	Historical/compliance storage	Search/retrieval mechanisms
Easy Memory
Interactive = Hot 🔥 = Fast access Long-term = Cold ❄️ = Cheap historical storage
 
⸻
 
10. Search Job
A Search Job can be used to search data that is stored outside normal interactive querying.
Typical use cases:
* Historical investigations
* Compliance reviews
* Forensics
* Searching older data
Archived Data
     ↓
Search Job
     ↓
Search Historical Logs
Think:
Search Job = “Find something in the archive.”
 
⸻
 
11. Restore
Restore is different from a Search Job.
It can temporarily make archived Analytics data available in an interactive form so that richer queries can be performed.
Archived Analytics Data
          ↓
       Restore
          ↓
Interactive Data
          ↓
Detailed Queries
Important Exam Distinction
Search Job
= Search archived data

Restore
= Bring archived Analytics data back
  for interactive querying
Your notes identify Restore as available for Analytics Logs, not Auxiliary or Basic Logs.
 
⸻
 
12. Complete Log Lifecycle
A simplified lifecycle looks like this:
Logs Collected
      ↓
Interactive Retention
      ↓
Frequently Queried
      ↓
Long-Term Retention
      ↓
Historical / Compliance Data
      ↓
Search Job
or
Restore (where supported)
 
⸻
 
13. Choosing the Right Plan
The most important question is:
How important is the data, and how often will we query it?
Scenario 1 — Entra Sign-in Logs
Security analysts frequently investigate sign-in activity.
Entra Sign-in Logs
       ↓
High Security Value
       ↓
Frequent Queries
       ↓
Analytics Logs
Scenario 2 — Firewall Logs
Large volume, but analysts may only need them during an investigation.
Firewall Logs
      ↓
High Volume
      ↓
Occasional Queries
      ↓
Auxiliary / Basic
Scenario 3 — Historical Compliance Data
Data is rarely queried but must be retained.
Historical Logs
      ↓
Rarely Accessed
      ↓
Long-Term Retention
 
⸻
 
14. Cost vs Security Visibility
There is no single plan for every type of data.
             Security Value
                  ↑
                  │
       Analytics  │
                  │
                  │
       Auxiliary  │
                  │
       Basic      │
                  │
                  └────────────────→
                    Query Frequency
The design goal is to put the right data in the right tier.
Don’t automatically put every log into the most expensive plan.
 
⸻
 
Exam & Interview Questions
Why does Sentinel provide different log plans?
To balance security visibility, query capabilities, performance, retention requirements, and cost.
Which plan is designed for frequently queried security data?
Analytics Logs.
Which plan is suitable for large volumes of less frequently queried data?
Auxiliary Logs or Basic Logs, depending on the required capabilities and current availability.
What is interactive retention?
The period during which data remains available for normal interactive querying.
What is long-term retention?
Lower-cost retention for historical data that is accessed less frequently.
What is a Search Job?
A mechanism for searching data that is outside normal interactive querying, particularly historical data.
What is Restore?
A mechanism that can temporarily make supported archived Analytics data available for interactive querying.
What is the key difference between Search Job and Restore?
Search Job searches the archive; Restore brings supported archived Analytics data back for interactive analysis.
Which logs would typically use Analytics?
High-value security data such as sign-in, Defender, EDR, and important audit logs.
Which logs would typically use Auxiliary or Basic?
High-volume contextual data such as firewall, proxy, and network-flow logs when the full Analytics capabilities aren’t required.
 
⸻
 
🧠 One-Minute Revision
Analytics
= Active Security
= High Value
= Frequently Queried
= Broadest Analytics
= Higher Cost

Auxiliary
= Context
= High Volume
= Lower Cost
= Less Frequent Queries
= Preview in the study scenario

Basic
= Lower-Cost Log Option
= More Limited Capabilities

Interactive
= Hot 🔥
= Fast / Normal Queries

Long-Term
= Cold ❄️
= Cheap Historical Storage

Search Job
= Search the archive

Restore
= Bring supported archived Analytics data
  back for interactive queries
Exam Formula
Primary / Frequently Used Security Data
                 ↓
          Analytics Logs


High-Volume / Less Frequently Used Data
                 ↓
      Auxiliary / Basic Logs


Older Historical Data
                 ↓
        Long-Term Retention
Golden Rule
Analytics = active security data. Auxiliary/Basic = lower-cost contextual data. Interactive = hot and quickly queryable. Long-term = cold historical retention.
