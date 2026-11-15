Identity Lifecycle Management (ILM)

1. What is Identity Lifecycle Management?

Identity Lifecycle Management (ILM) is the process of managing a user’s digital identity throughout their relationship with an organization.

It covers the creation, modification, maintenance and removal of user identities and their access rights.

In simple terms:

Identity Lifecycle Management = Managing a user’s identity and access from the moment they join an organization until they leave.

An identity has a lifecycle because a person’s relationship with an organization changes over time.

For example:

* Someone applies for a job.
* They become an employee.
* They change departments.
* They get promoted.
* They relocate to another country.
* Eventually, they leave the organization.

Each change can affect their digital identity and access permissions.

⸻

2. The Three Main Stages of Identity Lifecycle Management

The identity lifecycle is commonly divided into three main stages:

1. Joiner – A new person joins the organization.
2. Mover – An existing person changes roles, responsibilities or locations.
3. Leaver – A person leaves the organization.

This is commonly known as the Joiner, Mover, Leaver (JML) process.

⸻

3. Stage One: Joiner – Creating a New Identity

A Joiner is someone who starts a new relationship with an organization.

This could be:

* A new employee.
* A contractor.
* A temporary worker.
* An intern.

Example: Patrick Gets a New Job

Imagine Patrick is a recent Business Informatics graduate looking for a job in the United States.

He creates a CV and applies for jobs through platforms such as LinkedIn.

Eventually, he finds a company he likes and submits his application through its HR portal.

Step 1: Job Application

Patrick enters his personal information into the company’s HR system.

This may include:

* Full name.
* Address.
* Email address.
* Phone number.
* Date of birth.
* CV.
* Educational qualifications.

At this point, Patrick is still an applicant, not an employee.

Step 2: Job Offer

Patrick successfully passes the interviews and receives a job offer.

He accepts the offer and becomes an employee.

His status changes from applicant to employee.

Step 3: Identity Creation (Aggregation)

The HR system communicates the relevant employee information to the company’s Identity Management system.

The Identity Management system creates Patrick’s digital identity.

This process is called Identity Aggregation in the context described in the lecture.

Patrick now has a digital identity within the organization.

This is sometimes described as his digital birth.

Step 4: Access Provisioning

Once Patrick’s identity has been created, the organization assigns the appropriate access based on his job role.

For example:

* Company email account.
* HR portal access.
* Internal applications.
* Collaboration tools.
* Department-specific systems.

This process is called User Provisioning.

Joiner Summary

Process	Description
Recruitment	Patrick applies for a job
HR Registration	His personal information is recorded
Employment	Patrick accepts the job offer
Identity Aggregation	His digital identity is created
Provisioning	Appropriate accounts and permissions are assigned

Remember: Joiner = Create identity + Grant appropriate access.

⸻

4. Stage Two: Mover – Modifying an Existing Identity

A Mover is an employee whose role, department, responsibilities or location changes within the organization.

Examples include:

* Changing departments.
* Getting promoted.
* Moving to another country.
* Changing job responsibilities.
* Transferring to another branch.

These changes often require adjustments to access permissions.

Example 1: Patrick Relocates to the UK

After working for the company for several years, Patrick is offered a position at the company’s UK branch.

His responsibilities and location change.

As a result, his access requirements also change.

He may no longer need:

* Certain US-specific applications.
* US branch resources.
* Systems associated with his previous location.

He may now need:

* UK-specific applications.
* UK branch resources.
* Local business systems.

The organization must update his permissions accordingly.

Example 2: Patrick Gets Promoted

Later, Patrick gets promoted to a managerial position.

His responsibilities increase.

He now needs access to:

* Management dashboards.
* Team management applications.
* Approval systems.
* Additional reporting tools.

However, some permissions from his previous position may no longer be necessary.

The organization should:

1. Retain permissions he still needs.
2. Grant new permissions required for management.
3. Revoke permissions that are no longer necessary.

This ensures Patrick has the correct access for his new responsibilities.

Mover Summary

Action	Description
Retain	Keep permissions that are still required
Add	Grant permissions needed for the new role
Remove	Revoke permissions that are no longer necessary

Remember: Mover = Modify identity attributes + Adjust access permissions.

⸻

5. Stage Three: Leaver – Removing an Identity’s Access

A Leaver is someone who ends their relationship with an organization.

Examples include:

* Employees who resign.
* Employees who retire.
* Employees whose contracts expire.
* Employees who are terminated.
* Contractors whose assignments end.

When someone leaves, their access must be removed to protect organizational systems and information.

Example 1: Simon Gets Terminated

Patrick’s colleague Simon becomes involved in fraudulent activities.

After the investigation, the company terminates Simon’s employment.

Because Simon represents a security risk, the organization must act quickly.

The IT and IAM teams should:

* Disable his user accounts.
* Revoke application access.
* Terminate active sessions.
* Revoke authentication credentials and tokens where appropriate.
* Remove unnecessary privileges.
* Preserve relevant audit records.

This process is called Deprovisioning.

The objective is to prevent Simon from accessing company systems after his employment ends.

Example 2: Patrick Resigns

Patrick is deeply affected by Simon’s actions and decides to resign.

He informs his manager and HR department and serves a two-month notice period.

During this period, Patrick remains an employee and may continue to need access to perform his job.

On his final working day, the organization initiates the offboarding process.

His accounts are disabled and his access is revoked according to company policy.

Patrick now becomes a Leaver.

Leaver Summary

Process	Description
Resignation or Termination	Employment relationship ends
Offboarding	Organization manages the departure
Deprovisioning	User access and accounts are removed or disabled
Access Revocation	Permissions and credentials are withdrawn
Audit Records	Relevant activity records are retained

Remember: Leaver = Remove access + Disable accounts.

⸻

6. Understanding the Complete JML Process

The three stages work together to manage a user’s identity throughout their relationship with an organization.

Stage	What Happens?	IAM Action
Joiner	A new employee joins	Create identity and provision access
Mover	An employee changes roles	Update identity and permissions
Leaver	An employee leaves	Revoke access and deprovision accounts

Simple JML Workflow

             NEW EMPLOYEE
                  |
                  v
                JOINER
                  |
          Create Digital Identity
                  |
          Assign Appropriate Access
                  |
                  v
             ACTIVE EMPLOYEE
                  |
                  v
                MOVER
                  |
          Update Identity Details
                  |
          Adjust Access Permissions
                  |
                  v
             ACTIVE EMPLOYEE
                  |
                  v
                LEAVER
                  |
          Revoke Access Permissions
                  |
          Disable User Accounts
                  |
                  v
          IDENTITY DEACTIVATED

An employee can experience multiple Mover events during their employment.

For example, Patrick relocates to the UK and later gets promoted. Both events make him a Mover.

⸻

7. Important Technical Concepts

Concept	Meaning
Identity Lifecycle Management (ILM)	Managing identities throughout their lifecycle
JML	Joiner, Mover, Leaver process
Identity Aggregation	Collecting identity information from authoritative sources into an identity management system
Provisioning	Creating accounts and assigning access
Deprovisioning	Disabling or removing accounts and access
Access Revocation	Withdrawing permissions or access rights
Offboarding	Managing an employee’s departure
HR System	System that manages employee information
Identity Management System	System that manages digital identities
Identity Governance	Managing and controlling identities, access and related policies

Important distinction:

Identity aggregation, provisioning and deprovisioning are related but different processes.

* Aggregation = Collecting identity information.
* Provisioning = Creating accounts and granting access.
* Deprovisioning = Removing or disabling accounts and access.

⸻

8. Why Is Identity Lifecycle Management Important?

Without proper identity lifecycle management, organizations can face serious security problems.

1. Unauthorized Access

Former employees may retain access to sensitive company information.

2. Excessive Permissions

Employees may keep permissions from previous roles even when they no longer need them.

3. Orphaned Accounts

Accounts may remain active even though the associated employee has left.

4. Human Error

Manually creating and updating thousands of accounts can lead to mistakes.

5. Security Breaches

Attackers may exploit outdated or improperly managed accounts to gain access to company systems.

Benefits of ILM

* Improves access security.
* Automates account management.
* Reduces manual work.
* Supports the Principle of Least Privilege.
* Improves employee onboarding and offboarding.
* Reduces unauthorized access risks.
* Supports compliance and auditing.

⸻

9. Connection to Other IAM Concepts

Identity Lifecycle Management connects directly to several concepts we have already studied.

IAM Concept	Connection to Identity Lifecycle
IAM	Manages identities and access throughout the lifecycle
Authentication	Verifies users when they access systems
Authorization	Determines what users can access
AAA	Records user activities through Accounting
Least Privilege	Ensures users receive only necessary permissions
Continuous Monitoring	Detects suspicious identity and access activities
Zero Trust	Requires access to be verified and controlled

For example, when Patrick changes roles:

* Identity Management updates his employee information.
* Authorization determines his new permissions.
* Least Privilege ensures unnecessary permissions are removed.
* Accounting records relevant access activities.

⸻

10. Final Summary

Identity Lifecycle Management (ILM) is the process of managing digital identities and their access rights from the moment someone joins an organization until they leave.

It consists of three main stages:

JOINER

* New employee joins.
* HR registers employee information.
* Digital identity is created.
* Appropriate accounts and permissions are assigned.

MOVER

* Employee changes department, role or location.
* Identity information is updated.
* New permissions are granted.
* Unnecessary permissions are revoked.

LEAVER

* Employee resigns, retires or is terminated.
* Accounts are disabled.
* Access is revoked.
* Offboarding is completed.

Key Takeaway

JML = Joiner + Mover + Leaver.

* Joiner = Create.
* Mover = Modify.
* Leaver = Remove.

The main purpose is to ensure that users always have the correct access based on their current relationship and responsibilities within an organization.

