GitHub Triple A (AAA) – Authentication, Authorization & Accounting

Introduction

The Triple A (AAA) framework is a fundamental concept in Identity and Access Management (IAM).

It helps organizations control:

* Who can access their systems.
* What users are allowed to do.
* How users’ activities are monitored and recorded.

AAA stands for:

1. Authentication – Who are you?
2. Authorization – What are you allowed to access?
3. Accounting – What did you do?

⸻

1. Authentication – Who are you?

Authentication is the process of verifying a user’s identity.

It answers the question:

Are you really who you claim to be?

Examples

* Username and password.
* Fingerprint recognition.
* Face recognition.
* Multi-Factor Authentication (MFA).
* Security keys.

GitHub example

You enter your username and password to log in to GitHub.

GitHub verifies your credentials to confirm your identity.

Remember: Authentication = Identity verification.

⸻

2. Authorization – What are you allowed to do?

Authorization determines what resources and actions an authenticated user is permitted to access.

It answers the question:

What are you allowed to do?

Examples

* Read a repository.
* Create a repository.
* Push code.
* Delete files.
* Manage team members.

GitHub example

Imagine you work in a development team.

GitHub provides different repository roles:

Role	Permission
Read	View code
Triage	Manage issues and pull requests
Write	Push code
Maintain	Manage repository settings
Admin	Full repository control

Even if you successfully log in, you cannot automatically perform every action.

Your permissions determine what you can do.

Remember: Authorization = Permission management.

⸻

3. Accounting – What did you do?

Accounting tracks and records activities performed by authenticated users.

It answers the question:

What did you do, and when did you do it?

Examples

* Login and logout records.
* Repository access.
* Code changes.
* Permission changes.
* Failed login attempts.
* Administrative activities.

GitHub example

Suppose a developer deletes an important repository file.

GitHub activity records and audit logs can help administrators investigate:

* Who performed the action?
* When did it happen?
* What action was performed?
* Which resource was affected?

This is important for:

* Security investigations.
* Accountability.
* Compliance.
* Monitoring suspicious activity.

Remember: Accounting = Activity tracking and auditing.

⸻

4. Understanding AAA with a Simple Example

Imagine entering a secure office building.

AAA Concept	Office Example	Main Question
Authentication	Show your employee ID	Who are you?
Authorization	Check whether you can enter the server room	What can you access?
Accounting	Record when you entered and left	What did you do?

Easy way to remember

* Authentication = Identity
* Authorization = Permission
* Accounting = Activity

⸻

5. How AAA Connects to Zero Trust

AAA is important in the Zero Trust security model.

Zero Trust follows the principle:

Never trust, always verify.

Even after successfully logging in, users should not automatically receive access to everything.

The system applies access policies and monitors user activity.

Example

1. Verify the user’s identity.
2. Check their permissions before granting access.
3. Monitor their actions.
4. Record suspicious activity.
5. Re-evaluate access when necessary.

Why is this important?

* Prevents unauthorized access.
* Reduces security risks.
* Protects sensitive information.
* Improves visibility into user activities.
* Helps organizations investigate security incidents.

⸻

6. Quick Knowledge Check

Question 1

A developer enters their username and password to access GitHub. Which AAA concept is this?

Answer: Authentication.

It verifies the developer’s identity.

Question 2

A developer can view a repository but cannot push code. Which AAA concept determines this?

Answer: Authorization.

It determines what actions the developer is permitted to perform.

Question 3

GitHub records who changed repository permissions and when. Which AAA concept is this?

Answer: Accounting.

It records activities for monitoring and auditing.

⸻

7. Final Summary

Concept	Meaning	Key Question
Authentication	Identity verification	Who are you?
Authorization	Access permissions	What can you do?
Accounting	Activity monitoring and logging	What did you do?

Key Takeaway

The AAA framework is one of the foundations of Identity and Access Management (IAM).

Remember these three questions:

1. Who are you? → Authentication.
2. What can you access? → Authorization.
3. What did you do? → Accounting.

Together, these three concepts help organizations secure systems, manage access and monitor user activities.

⸻

