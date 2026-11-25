Discretionary Access Control (DAC)

1. What Is Discretionary Access Control?

Discretionary Access Control (DAC) is an access control model in which the owner of a resource determines who can access it and what permissions they receive.

A resource can be:

* A file.
* A folder.
* A document.
* A database.
* A shared project.
* Another digital resource.

The resource owner has the discretion to grant, modify, or revoke access for other users, subject to the permissions and restrictions imposed by the operating system or organization.

Unlike some centralized access control models, DAC gives individual resource owners more control over their own resources.

2. How Does DAC Work?

The process is straightforward:

1. A user owns or controls a resource.
2. Another user requests access to that resource.
3. The owner decides whether to grant access.
4. The owner selects the appropriate permission level.
5. The system enforces the permissions.

For example, the owner might allow one user to read a document while allowing another user to read and modify it.

3. Practical Example: Shared Project Folder

Imagine Muhammad is working on a company project.

He needs access to a shared project folder containing documents and project information.

The folder belongs to a project manager.

The project manager decides to grant different permissions depending on the user’s responsibilities.

User	Role	Permission
Project manager	Folder owner	Full control
Muhammad	Project team member	Read and Write
External reviewer	Reviewer	Read Only

Understanding the permissions

Project manager – Full Control

The project manager owns the folder and can manage its contents and permissions, subject to the system’s controls.

Muhammad – Read and Write

Muhammad can:

* Open and read files.
* Create new files, if permitted.
* Edit existing documents.
* Save changes.

External reviewer – Read Only

External reviewers can:

* Open documents.
* View project information.
* Read the contents.

They cannot modify the documents under the assigned read-only permissions.

What makes this DAC?

The project manager decides who receives access and which permissions they receive.

The access decision is made at the discretion of the resource owner.

4. Common DAC Permissions

DAC commonly uses permissions such as:

Permission	Meaning
Read	View or open a resource
Write	Modify or update a resource
Execute	Run a file or program
Delete	Remove a resource
Full Control	Perform all permitted operations, including managing permissions

The exact permissions depend on the operating system or application.

For example, Windows file systems use access control lists (ACLs) to define which users and groups can perform particular actions on files and folders.

5. How Does DAC Manage Access?

DAC often uses an Access Control List (ACL).

An ACL is a list associated with a resource that specifies which users or groups can access it and what operations they are allowed to perform.

For example:

Resource	User	Permission
Project folder	Project manager	Full Control
Project folder	Muhammad	Read and Write
Project folder	External reviewer	Read Only

When someone attempts to access the folder, the system checks the relevant permissions before allowing the requested operation.

Important distinction: DAC describes the access control model, while an ACL is one common mechanism used to implement it.

6. Advantages of DAC

1. Flexibility

Resource owners can decide who needs access without requiring an administrator to manage every individual permission change.

2. Simple sharing

Users can share files and folders with colleagues or external collaborators.

3. Individual permission management

Different users can receive different permission levels for the same resource.

4. Suitable for collaborative environments

DAC is useful when teams need to share documents, folders, and project resources with different people.

7. Disadvantages of DAC

1. Less centralized control

Because resource owners can manage permissions, organizations may find it harder to maintain consistent access policies.

2. Accidental permission sharing

A user might accidentally grant access to the wrong person or share sensitive information too broadly.

3. Permission sprawl

Over time, resources may accumulate unnecessary permissions as users share them with more people.

4. Risk of unauthorized sharing

If an account is compromised, an attacker may be able to use the owner’s sharing privileges to grant themselves or others access to additional resources.

5. Difficult to manage at scale

In large organizations with many users and resources, manually managing individual permissions can become complicated.

8. DAC vs. Other Access Control Models

DAC is one of several access control models.

Here is how it compares with the models covered in previous lessons:

Model	Main basis for access	Who or what determines access?
DAC	Resource ownership	Resource owner
MAC	Security classifications and clearances	Central authority
RBAC	Organizational roles	Assigned roles and their permissions
ABAC	Attributes	Attribute-based policies
PBAC	Predefined policies	Organizational access policies

Understanding the differences

DAC – Discretionary Access Control

The resource owner decides who can access the resource.

Example: A project manager gives Muhammad read and write access to a folder.

MAC – Mandatory Access Control

Access is determined by centrally defined security classifications and user clearances.

Example: A user with the appropriate security clearance can access a classified document.

RBAC – Role-Based Access Control

Access is assigned according to a user’s organizational role.

Example: Data Analysts receive predefined permissions for analytics applications.

ABAC – Attribute-Based Access Control

Access is determined by evaluating attributes such as department, location, and employment type.

Example: Access is granted only when the user’s department and location satisfy the applicable rules.

PBAC – Policy-Based Access Control

Access is determined according to predefined organizational policies.

Example: Access is permitted only during working hours from an approved device and network.

9. Connection to the Principle of Least Privilege

DAC can support the Principle of Least Privilege (PoLP) when resource owners assign only the permissions users need.

For example:

* Muhammad needs to edit project documents, so he receives Read and Write permissions.
* An external reviewer only needs to inspect the documents, so they receive Read Only permissions.

Giving the reviewer unnecessary editing or deletion permissions would increase the risk of accidental or unauthorized changes.

Resource owners should regularly review permissions and remove access that is no longer necessary.

10. Key Takeaways

* DAC stands for Discretionary Access Control.
* The owner of a resource determines who can access it.
* Resource owners can assign different permissions to different users.
* Common permissions include Read, Write, Execute, Delete, and Full Control.
* DAC commonly uses Access Control Lists (ACLs).
* ACLs specify which users or groups can perform particular actions on a resource.
* DAC provides flexibility and makes resource sharing easier.
* Poor permission management can lead to accidental sharing and permission sprawl.
* DAC can support the Principle of Least Privilege when permissions are assigned carefully.

11. Final Summary

Discretionary Access Control is an access control model that gives resource owners the ability to decide who can access their files, folders, and other resources.

In Muhammad’s example, the project manager owns the shared project folder and decides that Muhammad receives Read and Write access, while external reviewers receive Read Only access.

The decision is discretionary because the resource owner controls the sharing permissions, subject to the system’s security restrictions.

The key principle: In DAC, the resource owner decides who gets access and what they are allowed to do.

