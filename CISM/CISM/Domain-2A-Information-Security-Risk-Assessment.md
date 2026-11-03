CISM Domain 2A – Information Security Risk Assessment

Overview

CISM Domain 2 focuses on Information Security Risk Management.

Part A – Information Security Risk Assessment – covers the identification, analysis, and evaluation of information security risks.

The objective is to ensure that information security risks are understood, prioritized, and evaluated against organizational risk appetite and tolerance.

Core Objectives

1. Understand fundamental risk terminology.
2. Identify information assets, threats, and vulnerabilities.
3. Evaluate vulnerabilities and control deficiencies.
4. Perform qualitative and quantitative risk assessments.
5. Develop realistic risk scenarios.
6. Evaluate and prioritize risks.
7. Select appropriate risk treatment options.

Key Principle: Risk management must support business objectives and remain aligned with organizational risk appetite.

⸻

1. Fundamental Risk Terminology and Boundaries

Understanding risk terminology is essential before conducting a risk assessment.

Risk Definitions

Term	Definition
Inherent Risk	Risk that exists before considering security controls or mitigation measures.
Residual Risk	Risk remaining after controls and mitigation measures have been applied.
Risk Capacity	Maximum amount of risk an organization can absorb without threatening its survival or viability.
Risk Tolerance	Acceptable level of variation around specific risk objectives or activities.
Risk Appetite	Overall amount and type of risk an organization is willing to pursue or retain.

Inherent vs. Residual Risk

* Inherent Risk: Risk before controls.
* Residual Risk: Risk after controls.

             INHERENT RISK
                   |
            Apply Controls
                   |
                   v
             RESIDUAL RISK
                   |
           Management Decision
                   |
         Accept or Further Treat

Risk Appetite vs. Risk Tolerance vs. Risk Capacity

Concept	Meaning	Example
Risk Appetite	Overall willingness to accept risk.	Organization accepts moderate operational risk to innovate.
Risk Tolerance	Acceptable deviation or variation for a particular objective.	Maximum acceptable system downtime is four hours.
Risk Capacity	Maximum risk the organization can survive.	Financial losses beyond a certain threshold threaten business continuity.

Exam Tip:

* Appetite = How much risk are we willing to take?
* Tolerance = How much variation is acceptable?
* Capacity = How much risk can we withstand?

Risk acceptance must remain within approved organizational boundaries.

⸻

2. Risk Identification (2A1)

Risk identification is the foundation of information security risk management.

The objective is to identify assets, threats, vulnerabilities, and potential events that could negatively affect business objectives.

Key Elements of Risk Identification

1. Assets: What needs protection?
2. Threats: What could cause harm?
3. Vulnerabilities: What weaknesses could be exploited?
4. Threat Actors: Who or what could initiate the threat?
5. Business Impact: What happens if the event occurs?

Consider all organizational dependencies, including:

* Internal systems.
* Employees.
* Business processes.
* Cloud providers.
* Third-party vendors.
* Supply chain partners.
* External service providers.

Common Risk Categories

Risk Category	Description	Example
Strategic	Threatens business objectives and long-term direction.	Failure to adapt to emerging technology.
Operational	Results from failed processes, people, or systems.	Human error or system failure.
Reputational	Damages organizational trust and brand value.	Public data breach.
Compliance	Violates legal, regulatory, or contractual requirements.	GDPR non-compliance.
Technology & Data	Affects IT systems, information, and availability.	Ransomware or data leakage.
Human Resources	Results from employee behavior or workforce issues.	Insider threats or insufficient training.

Threat Actors and Their Motivations

Threat Actor	Typical Motivation
Script Kiddies	Curiosity, experimentation, or notoriety.
Hacktivists	Political or ideological objectives.
Cybercriminals	Financial gain and extortion.
Organized Crime	Large-scale financial operations.
Nation-State Actors	Espionage, disruption, or geopolitical advantage.
Insiders	Financial gain, revenge, negligence, or unauthorized activity.
Competitors	Corporate espionage or competitive advantage.

Advanced Persistent Threats (APTs)

APTs are sophisticated, targeted, and persistent attacks, often associated with well-resourced threat actors.

Typical characteristics:

* Long-term access.
* Advanced attack techniques.
* Stealth and persistence.
* Targeted intelligence gathering.
* Potential nation-state involvement.

Threat Vectors vs. Attack Surface

Concept	Definition	Example
Threat Vector	The pathway or method used to exploit a system.	Phishing email or malicious attachment.
Attack Surface	The total number of potential entry points and weaknesses.	Internet-facing servers, APIs, endpoints, and user accounts.

Remember:

* Vector = How an attacker gets in.
* Attack Surface = All the possible ways in.

Threat Intelligence

Threat intelligence provides information about threats, vulnerabilities, indicators, and attacker behavior.

Important sources and technologies:

Source / Technology	Purpose
OSINT	Open-source intelligence gathered from publicly available information.
NVD	National Vulnerability Database containing vulnerability information.
CVE	Common Vulnerabilities and Exposures identifier system.
IoC	Indicators of Compromise used to identify potentially malicious activity.
STIX	Standardized format for describing and sharing cyber threat intelligence.
TAXII	Protocol for exchanging cyber threat intelligence.

STIX vs. TAXII

* STIX: Defines what threat intelligence information looks like.
* TAXII: Defines how threat intelligence is exchanged.

Exam Tip: STIX = Information format; TAXII = Transportation mechanism.

⸻

3. Vulnerability and Control Deficiency Analysis (2A2)

What is a Vulnerability?

A vulnerability is a weakness in technology, processes, people, or policies that can be exploited by a threat.

Examples:

* Unpatched operating systems.
* Weak authentication.
* Misconfigured cloud storage.
* Excessive user privileges.
* Missing security policies.
* Insufficient employee awareness.

Vulnerability Scanning

Vulnerability scanning uses automated tools to identify known weaknesses.

Common characteristics:

Scan Type	Description
Credentialed Scan	Uses authenticated access to inspect systems more deeply.
Non-Credentialed Scan	Evaluates systems from an unauthenticated perspective.
Intrusive Scan	May interact aggressively with systems and potentially affect operations.
Non-Intrusive Scan	Attempts to identify weaknesses with minimal operational impact.

Vulnerability scanning helps:

* Identify missing patches.
* Detect insecure configurations.
* Find known vulnerabilities.
* Prioritize remediation.
* Support compliance assessments.

Penetration Testing

Penetration testing simulates real-world attacks to evaluate whether vulnerabilities can actually be exploited.

Common objectives:

* Validate security defenses.
* Identify attack paths.
* Test lateral movement.
* Evaluate privilege escalation.
* Assess persistence opportunities.
* Determine potential business impact.

Vulnerability Scanning vs. Penetration Testing

Vulnerability Scanning	Penetration Testing
Identifies known weaknesses.	Attempts to exploit weaknesses.
Often automated.	Usually combines automated and manual techniques.
Broad coverage.	Focuses on exploitable attack paths.
Identifies potential exposure.	Demonstrates practical security impact.
Generally less intrusive.	Can be intrusive and requires authorization.

Penetration Testing Approaches

Approach	Knowledge Available to Tester
White-box	Full or extensive system knowledge.
Black-box	Little or no internal knowledge.
Grey-box	Partial system knowledge.

Exam Tip: Penetration testing goes beyond identifying vulnerabilities by validating whether they can be exploited and what impact they may have.

Security Control Baselines (SCBs)

A Security Control Baseline defines a minimum set of security controls that systems must implement.

Baselines provide:

* Standardized security configurations.
* Consistent control implementation.
* Minimum acceptable security requirements.
* Measurable compliance.
* Alignment with risk tolerance.
* Support for regulatory obligations.

Common sources:

* NIST frameworks and publications.
* ISO 27001 and ISO 27002.
* CIS Controls and benchmarks.

Key Principle: Baselines establish minimum security expectations, not necessarily the complete security requirements for every system.

⸻

4. Risk Assessment, Analysis, and Scenarios (2A3)

Risk assessment evaluates identified risks to determine their likelihood, impact, and significance to the organization.

Three Core Risk Assessment Phases

Phase	Purpose
Identification	Identify assets, threats, vulnerabilities, and potential events.
Analysis	Determine likelihood and potential impact.
Evaluation	Compare risk levels against organizational criteria and prioritize treatment.

Risk Analysis Methods

There are three common approaches:

Qualitative Risk Analysis

Uses descriptive categories rather than precise financial values.

Typical classifications:

* High
* Medium
* Low
* Critical

Common tool: Risk Matrix / Heat Map.

Advantages:

* Easy to understand.
* Quick to implement.
* Useful when financial data is unavailable.
* Supports management discussions.

Limitations:

* Subjective.
* Different assessors may produce different results.
* Less precise for financial comparisons.

Quantitative Risk Analysis

Uses numerical values, probabilities, and financial estimates to measure risk.

Typical concepts:

Term	Definition
SLE	Single Loss Expectancy: Estimated financial loss from one occurrence.
ARO	Annualized Rate of Occurrence: Expected frequency of an event per year.
ALE	Annualized Loss Expectancy: Expected annual financial loss.

Formulas:

[
SLE = Asset\ Value \times Exposure\ Factor
]

[
ALE = SLE \times ARO
]

Example:

* Asset Value = €100,000
* Exposure Factor = 40%
* ARO = 2

[
SLE = 100,000 \times 0.40 = €40,000
]

[
ALE = 40,000 \times 2 = €80,000
]

Expected annual loss = €80,000.

Advantages:

* Supports financial decision-making.
* Helps compare security investments.
* Provides measurable financial estimates.

Limitations:

* Requires reliable data.
* Estimates may be difficult to establish.
* Can create a false sense of precision.

Semi-Quantitative Risk Analysis

Combines qualitative descriptions with numerical scoring.

Example:

Rating	Score
Very Low	1
Low	2
Medium	3
High	4
Very High	5

Risk Score:

[
Risk\ Score = Likelihood \times Impact
]

Example:

* Likelihood = 4
* Impact = 5

[
Risk\ Score = 4 \times 5 = 20
]

This approach supports more consistent prioritization while remaining easier to implement than a fully quantitative assessment.

Qualitative vs. Quantitative vs. Semi-Quantitative

Method	Measurement	Best Used For
Qualitative	High / Medium / Low	Initial assessments and prioritization.
Quantitative	Financial values and probabilities	Business cases and financial risk analysis.
Semi-Quantitative	Numerical scoring based on categories	Consistent prioritization across departments.

Exam Tip: Choose the assessment method based on available data, business needs, and decision-making requirements.

Risk Scenarios

A risk scenario describes how a threat could cause harm to an organizational asset.

A complete scenario should consider:

1. Threat Actor – Who or what initiates the event?
2. Threat Type – What kind of threat is involved?
3. Asset – What is being targeted?
4. Event – What happens?
5. Frequency – How often might it occur?
6. Loss Magnitude – What is the potential business impact?

Example:

Threat Actor:
Cybercriminal group
Threat Type:
Ransomware
Asset:
Customer database
Event:
Unauthorized encryption and data exfiltration
Frequency:
Estimated likelihood of occurrence
Loss Magnitude:
Operational disruption, recovery costs,
regulatory penalties, and reputational damage

Cascading Risks

Cascading risks occur when one event triggers multiple subsequent failures.

Example:

Cloud Provider Outage
        |
        v
Critical Application Unavailable
        |
        v
Business Operations Disrupted
        |
        v
Customer Transactions Fail
        |
        v
Financial and Reputational Damage

Exam Tip: Evaluate dependencies and interconnected business processes, not just isolated technical systems.

Specialized Risk Analysis Frameworks

FAIR – Factor Analysis of Information Risk

FAIR provides a structured model for quantifying information security risk in financial terms.

It helps organizations:

* Estimate probable financial losses.
* Analyze threat event frequency.
* Evaluate vulnerability and resistance.
* Support risk-based investment decisions.
* Communicate cyber risk in business language.

HARM

HARM is another specialized approach referenced in the training material for analyzing information security risk.

Exam Tip: Understand the purpose of specialized risk frameworks and why organizations may use them to improve risk analysis.

⸻

5. Risk Treatment Options

After risks have been analyzed and evaluated, management must decide how to address them.

There are four primary risk treatment options.

1. Risk Avoidance

Eliminates the risk by stopping or changing the activity that creates it.

Example:

* Discontinue a high-risk business application.
* Stop collecting unnecessary sensitive information.
* Avoid entering a market with unacceptable regulatory exposure.

2. Risk Mitigation

Reduces the likelihood or impact of a risk through security controls.

Example:

* Implement MFA.
* Deploy endpoint protection.
* Encrypt sensitive information.
* Improve backup and recovery capabilities.

3. Risk Transference

Transfers or shares part of the financial impact with another party.

Example:

* Purchase cyber insurance.
* Outsource specific risk-related services under contractual arrangements.

Important: Transference does not eliminate the organization’s accountability or all associated risks.

4. Risk Acceptance

Management deliberately decides to retain the risk without implementing additional treatment.

This may be appropriate when:

* Risk is within approved appetite and tolerance.
* Mitigation costs exceed expected benefits.
* The risk is sufficiently low.
* Management formally approves the decision.

Acceptance should be documented, authorized, and periodically reviewed.

Risk Treatment Comparison

Option	Action	Example
Avoidance	Eliminate the activity creating the risk.	Stop using a vulnerable application.
Mitigation	Reduce likelihood or impact.	Implement MFA and encryption.
Transference	Share or transfer financial consequences.	Cyber insurance.
Acceptance	Retain the risk knowingly.	Accept low-impact residual risk.

Risk Treatment Decision Flow

       IDENTIFIED RISK
              |
              v
       Analyze and Evaluate
              |
              v
     Compare Against Appetite
              |
       +------+------+
       |      |      |
       v      v      v
    Avoid  Mitigate Transfer
              |
              v
          Acceptance
        (If Approved)

Exam Tip: Risk acceptance is a management decision, not simply a security team’s decision.

⸻

6. CISM Domain 2A – Quick Exam Revision

Topic	Key Takeaway
Inherent Risk	Risk before controls.
Residual Risk	Risk remaining after controls.
Risk Appetite	Overall willingness to accept risk.
Risk Tolerance	Acceptable variation around objectives.
Risk Capacity	Maximum risk the organization can withstand.
Risk Identification	Identify assets, threats, and vulnerabilities.
Strategic Risk	Threatens business objectives.
Operational Risk	Failed processes, people, or systems.
Reputational Risk	Damages trust and brand value.
Compliance Risk	Violates laws, regulations, or contracts.
Threat Actor	Individual or group responsible for a threat.
Threat Vector	Method used to reach a target.
Attack Surface	All possible entry points.
OSINT	Publicly available intelligence.
CVE	Common Vulnerabilities and Exposures.
NVD	National Vulnerability Database.
IoC	Indicator of Compromise.
STIX	Threat intelligence format.
TAXII	Threat intelligence exchange protocol.
Vulnerability Scan	Identifies known weaknesses.
Penetration Test	Attempts to exploit weaknesses.
White-box	Full or extensive knowledge.
Black-box	No or minimal knowledge.
Grey-box	Partial knowledge.
Security Baseline	Minimum mandatory controls.
Qualitative Analysis	High / Medium / Low.
Quantitative Analysis	Financial values and probabilities.
Semi-Quantitative	Numerical scoring of categories.
SLE	Financial loss from one event.
ARO	Expected annual occurrence frequency.
ALE	Expected annual financial loss.
FAIR	Quantitative information risk analysis.
Cascading Risk	One failure triggers further failures.
Avoidance	Stop the risky activity.
Mitigation	Reduce risk.
Transference	Share financial consequences.
Acceptance	Retain risk with approval.

⸻

7. CISM Exam Mindset

When answering Domain 2A questions, remember these principles:

1. Start with business objectives: Risk assessments must support organizational priorities.
2. Identify assets first: Understand what needs protection and its business value.
3. Consider the complete threat landscape: Include internal, external, and third-party threats.
4. Understand vulnerabilities: A threat becomes a significant risk when it can exploit a weakness and cause business impact.
5. Assess likelihood and impact: Risk prioritization must consider both.
6. Use appropriate assessment methods: Select qualitative or quantitative techniques based on available data and business needs.
7. Evaluate residual risk: Controls reduce risk but rarely eliminate it.
8. Respect risk appetite: Risks outside approved boundaries require further treatment or escalation.
9. Management owns risk decisions: Security professionals provide assessments and recommendations.
10. Treat risk continuously: Reassess risks whenever business conditions, technology, or threats change.

⸻

8. Final Memory Aids

* Inherent = Before controls
* Residual = After controls
* Appetite = Willingness
* Tolerance = Acceptable variation
* Capacity = Maximum survivable risk
* Threat Vector = Attack pathway
* Attack Surface = All possible entry points
* STIX = What is shared
* TAXII = How it is shared
* Vulnerability Scan = Find weaknesses
* Penetration Test = Exploit weaknesses
* Qualitative = High / Medium / Low
* Quantitative = Financial values
* Semi-Quantitative = Numerical scores
* SLE = Single loss
* ARO = Annual frequency
* ALE = Annual loss
* FAIR = Financial information risk analysis
* Avoidance = Stop
* Mitigation = Reduce
* Transference = Share
* Acceptance = Retain

⸻

9. Final Exam Takeaways

The most important Domain 2A principles:

* Risk management must align with business objectives.
* Risk appetite is established at the organizational level.
* Risk tolerance defines acceptable variation around specific objectives.
* Inherent risk exists before controls; residual risk remains after controls.
* Risk identification must include assets, threats, vulnerabilities, and third parties.
* Threat intelligence improves awareness of emerging threats.
* Vulnerability scanning identifies weaknesses; penetration testing validates exploitability.
* Security baselines establish minimum protection requirements.
* Risk assessment includes identification, analysis, and evaluation.
* Qualitative assessments use descriptive ratings; quantitative assessments use financial estimates.
* Risk scenarios should consider threat actors, events, frequency, and loss magnitude.
* Risk treatment includes avoidance, mitigation, transference, and acceptance.
* Risk acceptance requires appropriate management authorization.
* Risk management is continuous and must adapt to changing business and threat environments.

⸻

