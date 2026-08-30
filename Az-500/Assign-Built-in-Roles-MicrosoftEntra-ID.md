Assign Built-in Roles in Microsoft Entra ID
Overview
Microsoft Entra ID uses built-in administrative roles to delegate identity and directory management tasks.
Examples include:
* User Administrator
* Application Administrator
* Authentication Administrator
* Global Administrator
Microsoft Entra roles can be assigned to:
* Users
* Groups
The goal is to give administrators the permissions they need without giving them unnecessary privileges.
 
⸻
 
Zero Trust and Privileged Access
Microsoft recommends reducing standing administrative privileges.
Two important concepts are:
Just-In-Time (JIT)
Just-In-Time access means privileged access is activated only when it is needed.
Instead of giving an administrator permanent active access:
Administrator
     ↓
Eligible Role
     ↓
Activate When Needed
     ↓
Temporary Privileged Access
 
⸻
 
Just-Enough-Access (JEA)
Just-Enough-Access means users receive only the permissions required to perform their tasks.
Example:
If an administrator only needs to manage authentication methods, don’t automatically give them:
Global Administrator
Instead, assign an appropriate specialized role.
 
⸻
 
Microsoft Entra Privileged Identity Management (PIM)
Microsoft Entra Privileged Identity Management (PIM) helps organizations manage privileged access.
PIM can support:
* Just-In-Time access
* Eligible role assignments
* Temporary role activation
* Approval workflows
* MFA during activation
* Access reviews
* Auditing
Basic Flow
Eligible Role
      ↓
Activation Request
      ↓
MFA / Approval
      ↓
Temporary Access
      ↓
Role Expires
 
⸻
 
Who Can Assign Microsoft Entra Roles?
The roles commonly used to assign Microsoft Entra administrative roles include:
* Global Administrator
* Privileged Role Administrator
Exam Tip
If the question asks:
“Which role can assign Microsoft Entra roles?”
Remember:
Global Administrator
Privileged Role Administrator
 
⸻
 
Role Assignment Process
The role assignment process can be understood as two major phases:
1. Select the Role
        ↓
2. Configure Assignment Settings
 
⸻
 
Step 1 — Select the Role
A typical workflow in the Microsoft Entra admin center is:
Microsoft Entra Admin Center
        ↓
Identity
        ↓
Users
        ↓
All Users
        ↓
Select User
        ↓
Assigned Roles
        ↓
Add Assignments
        ↓
Choose Role
        ↓
Next
The exact portal interface can change over time, but the underlying concept remains the same:
Select the identity, select the role, then configure the assignment.
 
⸻
 
Step 2 — Configure Assignment Type
When assigning a privileged role, you may choose between:
* Active
* Eligible
These are extremely important exam concepts.
 
⸻
 
Active Assignment
An Active assignment means the role is immediately available to the user.
User
 ↓
Active Role
 ↓
Immediate Access
Example
A user receives:
Global Administrator
+
Active
The role is immediately active.
Advantages
* Immediate access
* No activation required
Disadvantage
The user has standing privileged access.
If the account is compromised, the attacker may immediately have the privileges of that active role.
 
⸻
 
Eligible Assignment
An Eligible assignment means the user is allowed to activate the role when needed, but the role is not continuously active.
User
 ↓
Eligible Role
 ↓
Activate Through PIM
 ↓
Temporary Privileged Access
Example
Global Administrator
        ↓
Eligible
The user does not continuously operate as Global Administrator.
When administrative work is required, the user activates the role through PIM.
 
⸻
 
Active vs Eligible
Feature	Active	Eligible
Access immediately available	✅	❌
Activation required	❌	✅
Temporary activation	❌	✅
Supports JIT access	❌	✅
Reduces standing privilege	❌	✅
Preferred for privileged access	Usually not	✅
Easy Memory Trick
Active
=
Use Now

Eligible
=
Activate When Needed
 
⸻
 
Why Is Eligible Better for Privileged Roles?
Consider an administrator who only needs Global Administrator permissions for 30 minutes.
Active Assignment
Global Administrator
        ↓
Always Active
The privilege exists even when the administrator is not performing administrative work.
Eligible Assignment
Global Administrator
        ↓
Eligible
        ↓
Activate
        ↓
Temporary Access
        ↓
Expires
This reduces the amount of time that highly privileged access is exposed.
 
⸻
 
Permanent Eligibility
An eligible assignment can be configured so that the user remains eligible indefinitely.
Conceptually:
User
 ↓
Permanently Eligible
 ↓
Can Activate Whenever Needed
Important:
Permanently Eligible does not mean permanently Active.
The user is eligible to activate the role, but still needs to activate it when administrative access is required.
 
⸻
 
Time-Limited Eligibility
Eligibility can also be limited to a specific period.
Example:
Project Start
01-Jan-2026
      ↓
Project End
31-Mar-2026
The administrator can be eligible for the role during the project period.
After the end date:
Eligibility Expires
This is useful for temporary projects and contractors.
 
⸻
 
Complete Assignment Flow
A simplified role assignment process looks like this:
Microsoft Entra ID
       ↓
Users
       ↓
Select User
       ↓
Assigned Roles
       ↓
Add Assignment
       ↓
Choose Role
       ↓
Choose Assignment Type
       ↓
Active or Eligible
       ↓
Configure Duration / Settings
       ↓
Assign
 
⸻
 
Updating Existing Role Assignments
Existing role assignments can be modified when requirements change.
Examples include:
* Change assignment settings
* Modify duration
* Change from Active to Eligible
* Change eligibility period
A simplified workflow:
Identity
 ↓
Users
 ↓
Select User
 ↓
Assigned Roles
 ↓
Update
 ↓
Save
 
⸻
 
Removing Role Assignments
A role assignment can also be removed.
Typical workflow:
Identity
 ↓
Users
 ↓
Select User
 ↓
Assigned Roles
 ↓
Remove
 ↓
Confirm
After removal:
Role Assignment Removed
        ↓
Permissions Lost
 
⸻
 
Example: Administrator Needs Temporary Access
Imagine Sara is an IT administrator.
She normally does not need Global Administrator permissions.
She receives:
Global Administrator
        ↓
Eligible
When she needs to perform a tenant-wide administrative task:
Sara
 ↓
PIM
 ↓
Activate Role
 ↓
MFA / Approval if configured
 ↓
Temporary Global Administrator Access
After the activation period ends:
Global Administrator
        ↓
No Longer Active
Sara remains eligible if the assignment itself has not expired.
 
⸻
 
Example: Project-Based Administrator
A company hires an administrator for a three-month project.
Instead of:
Global Administrator
 ↓
Permanent Active
a better approach is:
Appropriate Role
 ↓
Eligible
 ↓
01-Jan → 31-Mar
The eligibility automatically ends after the defined period.
This follows the principles of:
* Least privilege
* Just-In-Time access
* Zero Trust
 
⸻
 
Least Privilege
One of the most important security principles is:
Give users only the permissions they need.
For example:
Task:
Manage Authentication Methods

Better:
Authentication Administrator

Avoid:
Global Administrator
The goal is to avoid unnecessarily broad permissions.
 
⸻
 
Zero Trust
The Zero Trust approach can be summarized as:
Never assume trust. Continuously verify and limit access.
For privileged identity management, two important ideas are:
Zero Trust
    ↓
Least Privilege
    +
Just-In-Time Access
And:
JIT
↓
Access only when needed

JEA
↓
Only the permissions required
 
⸻
 
PIM and Zero Trust
PIM helps implement these principles for privileged roles.
Privileged Role
       ↓
Eligible
       ↓
PIM
       ↓
Activate
       ↓
MFA / Approval
       ↓
Temporary Access
       ↓
Expiration
This reduces standing administrative privileges.
 
⸻
 
Active vs Eligible — Real-World Example
Active
Ahmed
 ↓
Security Administrator
 ↓
Active
Ahmed can use the role immediately.
 
⸻
 
Eligible
Ahmed
 ↓
Security Administrator
 ↓
Eligible
 ↓
PIM Activation
 ↓
Temporary Access
Ahmed receives the privilege only when required.
 
⸻
 
Important Exam Distinctions
Active
The role is active immediately.
Active = Immediate
 
⸻
 
Eligible
The user can activate the role when needed.
Eligible = Activate
 
⸻
 
PIM
Microsoft Entra service for managing privileged access and supporting Just-In-Time activation.
PIM = Privileged Access Management
 
⸻
 
JIT
Provide privileged access only when needed.
JIT = Just-In-Time
 
⸻
 
JEA
Provide only the minimum permissions required.
JEA = Just-Enough-Access
 
⸻
 
Exam Scenarios 🚀
Question 1
Which roles can assign Microsoft Entra administrative roles?
Answer:
* Global Administrator
* Privileged Role Administrator
 
⸻
 
Question 2
What are the two main assignment types?
Answer:
* Active
* Eligible
 
⸻
 
Question 3
A user needs immediate access to a role without activation.
Answer:
Active
 
⸻
 
Question 4
A user should activate a privileged role only when needed.
Answer:
Eligible
 
⸻
 
Question 5
Which Microsoft service provides Just-In-Time privileged role activation?
Answer:
Microsoft Entra Privileged Identity Management (PIM)
 
⸻
 
Question 6
Which assignment type best supports Just-In-Time privileged access?
Answer:
Eligible
 
⸻
 
Question 7
An administrator needs Global Administrator permissions for only 30 minutes.
Best approach:
Global Administrator
        ↓
Eligible
        ↓
PIM
        ↓
Temporary Activation
 
⸻
 
Question 8
An administrator only needs permission to manage users. Should you assign Global Administrator?
Answer:
No.
Use an appropriate lower-privileged role such as User Administrator, assuming it provides everything required for the task.
 
⸻
 
Quick Exam Table
Concept	Meaning
Active	Role is immediately available
Eligible	Role can be activated when needed
PIM	Manages privileged access
JIT	Access only when needed
JEA	Only required permissions
Least Privilege	Minimum permissions necessary
Global Administrator	Broad Microsoft Entra administrative control
Privileged Role Administrator	Can manage privileged role assignments
 
⸻
 
Quick Memory Formula
Active
=
Immediate Access
Eligible
=
Activate When Needed
Zero Trust
    ↓
JIT + JEA
    ↓
PIM
 
⸻
 
Golden Rules
Rule 1
Avoid Global Administrator when a more specific role is sufficient.
Rule 2
Use Eligible assignments for privileged roles when possible.
Rule 3
Use PIM to activate privileged roles Just-In-Time.
Rule 4
Least Privilege = only the permissions required.
Rule 5
Eligible ≠ Active.
An eligible user can activate the role, but the role is not continuously active.
 
⸻
 
Final Mental Model
When you see a Microsoft Entra role assignment question, ask:
1. WHO?
   ↓
   Which user/group?

2. WHAT?
   ↓
   Which Entra role?

3. HOW?
   ↓
   Active or Eligible?

4. HOW LONG?
   ↓
   Permanent or Time-Limited?

5. HOW IS IT ACTIVATED?
   ↓
   PIM / JIT
Then apply:
Least Privilege
       +
Eligible Access
       +
PIM
       +
JIT
       ↓
More Secure Privileged Access
One-Line Summary
Microsoft Entra built-in roles delegate identity administration, while PIM allows privileged roles to be assigned as Eligible and activated Just-In-Time, reducing standing administrative access and supporting Zero Trust and least-privilege principles.

 
