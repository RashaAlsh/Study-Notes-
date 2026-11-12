Identity and Access Management (IAM)

1. What is IAM?

IAM stands for Identity and Access Management.

IAM is a framework of policies, processes and technologies that organizations use to manage digital identities and control access to systems, applications, networks and data.

In simple terms, IAM answers two important questions:

1. Identity: Who are you?
2. Access: What are you allowed to do?

IAM ensures that the right people have access to the right resources at the right time, with the appropriate permissions.

⸻

2. Understanding Identity Management

What is an identity?

Your identity is who you are. It describes the characteristics and information that distinguish you from other people.

In cybersecurity, an identity represents a user or entity that needs to be recognized by a system.

Example: John Doe

Imagine John Doe lives in Houston, Texas, and works as a cybersecurity analyst in the IT department.

His identity may include:

Identifier	Example
Full name	John Doe
Phone number	His unique phone number
Employee ID	His company identification number
Date of birth	His birth date
Job title	Cybersecurity Analyst
Department	IT Department
Fingerprint	Biometric identifier
Face recognition	Biometric identifier
Retina scan	Biometric identifier

Together, these attributes help establish and distinguish John’s identity.

Common identity attributes

* Name.
* Username.
* Email address.
* Employee ID.
* Phone number.
* Job title.
* Department.
* Biometric characteristics.

Important: Not every identifier is unique or sufficient by itself. Systems use appropriate combinations of identity attributes to identify users.

Identity Management in IAM

Identity management is about creating, maintaining and managing digital identities.

It includes:

* Creating user identities.
* Updating user information.
* Managing identity attributes.
* Disabling or deleting identities when necessary.
* Managing the identity lifecycle.

Remember: Identity Management = Knowing who you are.

⸻

3. Understanding Access Management

Knowing someone’s identity does not automatically mean they should have access to every system.

This is where access management comes in.

What is Access Management?

Access management determines which systems, applications, resources and data a user is allowed to access.

It also determines what actions the user can perform within those resources.

It answers:

What are you allowed to access and what can you do?

Example: Company Access Table

Imagine John Doe works in the IT department.

The company maintains an access management table:

Employee	System	Access rights
John Doe	Email	Read and send
John Doe	HR System	No access
John Doe	Security Dashboard	Read and manage
John Doe	GitHub	Read and write
John Doe	Payroll System	No access

This table demonstrates that John only receives access to the systems necessary for his job.

If a system is not assigned to him, he should not have access to it.

Access Management involves:

* Granting access.
* Modifying permissions.
* Removing access.
* Managing user roles.
* Enforcing access policies.
* Controlling access to sensitive resources.

Remember: Access Management = Deciding what you can do.

⸻

4. How Identity and Access Management Work Together

Identity management and access management are grouped together because they are two essential parts of securely granting access.

They work in a logical sequence.

Step-by-step example

Imagine John wants to access his company’s security dashboard.

Step 1: Identity Management

John enters his username and password.

The system verifies his identity.

It confirms that he is the registered user John Doe.

Step 2: Access Management

After verifying his identity, the system checks his permissions.

It determines whether John is allowed to access the security dashboard.

Step 3: Access Granted or Denied

* If John has the appropriate permissions, access is granted.
* If John does not have the appropriate permissions, access is denied.

Simple IAM workflow

       User attempts to log in
                 |
                 v
        Identity Management
         Who are you?
                 |
                 v
       Identity Verification
                 |
          Identity valid?
           /          \
         No            Yes
         |              |
         v              v
      Denied      Access Management
                   What can you do?
                         |
                         v
                  Check Permissions
                         |
                  Permission valid?
                    /       \
                  No         Yes
                  |           |
                  v           v
              Access       Access
               Denied      Granted

Key difference

Identity Management	Access Management
Identifies the user	Controls user access
Manages digital identities	Manages permissions
Answers who you are	Answers what you can do
Verifies identity information	Checks access rights

Remember: Identity = Who you are. Access = What you can do.

⸻

5. Why Do We Need IAM?

In the past, many organizations managed user accounts manually.

For example:

* Employee information was stored in Excel spreadsheets.
* PowerShell scripts were used to create user accounts.
* IT administrators manually assigned permissions.
* Accounts were manually disabled when employees left.

This approach might work for a small company.

However, as organizations grow, manual access management becomes increasingly difficult.

The problem: Managing 10,000+ employees

Imagine a company with more than 10,000 employees.

Every day, the organization experiences three types of employee changes:

1. Joiners

New employees join the organization.

IT administrators must:

* Create user accounts.
* Provide email access.
* Assign appropriate system permissions.
* Configure security settings.

2. Movers

Existing employees change departments, roles or locations.

IT administrators must:

* Update employee information.
* Remove permissions no longer required.
* Grant new permissions.
* Ensure access matches the new job responsibilities.

3. Leavers

Employees leave the organization or their contracts expire.

IT administrators must:

* Disable user accounts.
* Revoke access to company systems.
* Remove unnecessary permissions.
* Protect company information.

This process is commonly known as Joiner, Mover, Leaver (JML).

⸻

6. What Happens Without IAM?

Without proper IAM processes, organizations face several security risks.

Security risks

1. Unauthorized access

Employees may access systems or information they should not be able to access.

2. Orphaned accounts

Former employees may still have active accounts after leaving the organization.

3. Excessive permissions

Employees may have more privileges than necessary to perform their jobs.

4. Human error

Manual account creation and permission management can result in mistakes.

5. Data breaches

Attackers or former employees may exploit improperly managed accounts to access sensitive company information.

Example: Terminated employee

Imagine an employee leaves a company but their account is never disabled.

That former employee could potentially:

* Access confidential company information.
* Download sensitive customer data.
* Steal intellectual property.
* Misuse administrative privileges.
* Damage company systems.

This could result in financial losses, legal consequences and reputational damage.

⸻

7. How IAM Solutions Solve These Problems

IAM solutions automate and centralize identity and access management processes.

They help organizations manage the entire user lifecycle.

Main IAM capabilities

Capability	Purpose
User Provisioning	Create user accounts
User Deprovisioning	Disable or remove accounts
Access Management	Control access permissions
Authentication	Verify user identities
Authorization	Determine permitted actions
Role-Based Access Control (RBAC)	Assign permissions based on roles
Multi-Factor Authentication (MFA)	Add extra identity verification
Access Reviews	Review whether permissions are still needed
Audit Logging	Record user and administrative activities

Example: Automated Joiner, Mover, Leaver process

New employee joins:

* HR creates the employee record.
* IAM receives the relevant information.
* A user account is created.
* Appropriate access is assigned based on the employee’s role.

Employee changes department:

* HR updates the employee record.
* IAM identifies the role change.
* Old permissions are removed.
* New permissions are assigned.

Employee leaves:

* HR records the termination.
* IAM initiates the offboarding process.
* Accounts are disabled.
* Access is revoked according to company policies.

This reduces manual work and helps prevent unnecessary access.

⸻

8. Benefits of IAM

IAM provides several important benefits:

1. Improved Security – Ensures only authorized users can access resources.
2. Reduced Human Error – Automates repetitive account management tasks.
3. Time Savings – Reduces manual work for IT administrators.
4. Better Access Control – Ensures employees receive appropriate permissions.
5. Reduced Data Breach Risk – Helps prevent unauthorized access.
6. Regulatory Compliance – Supports organizations in meeting security and data protection requirements.
7. Accountability – Provides records of user access and activities.

⸻

9. Important IAM Concepts to Remember

Concept	Meaning
IAM	Identity and Access Management
Identity	Information representing who a user is
Authentication	Verifying who a user claims to be
Authorization	Determining what a user can access
Provisioning	Creating and assigning user access
Deprovisioning	Removing or disabling user access
RBAC	Assigning permissions based on job roles
MFA	Using multiple authentication factors
JML	Joiner, Mover, Leaver lifecycle
Least Privilege	Giving users only the access they need

⸻

10. Final Summary

IAM (Identity and Access Management) is essential for protecting an organization’s systems, applications and data.

It combines two important functions:

Identity Management

* Identifies users.
* Creates and manages digital identities.
* Maintains user information.
* Manages identity lifecycles.

Access Management

* Determines which resources users can access.
* Assigns appropriate permissions.
* Controls what users can do.
* Removes unnecessary access.

Why IAM Matters

As organizations grow, manually managing thousands of user accounts becomes inefficient and risky.

IAM solutions automate the process of creating, updating and disabling accounts.

They improve security, reduce human error, save time and help organizations protect sensitive information.

The Most Important Thing to Remember

IAM ensures that the right people have the right access to the right resources at the right 

