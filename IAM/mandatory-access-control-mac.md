Mandatory Access Control (MAC)

1. What Is Mandatory Access Control?

Mandatory Access Control (MAC) is an access control model in which a central authority defines and enforces security policies.

Users are assigned security clearance levels, while resources such as files and documents are assigned security classification labels.

A user can access a resource only when their clearance satisfies the applicable security policy.

Unlike Discretionary Access Control (DAC), individual resource owners cannot freely decide who receives access. The system enforces the rules centrally.

2. How MAC Works

MAC is based on two important concepts:

* Security clearance: The level of authorization assigned to a user.
* Security classification: The sensitivity level assigned to a resource.

The system compares the user’s clearance with the resource’s classification before allowing access.

Example: Muhammad in a high-security agency

Suppose Muhammad works for a high-security government agency.

The agency has three files:

File	Classification
File A	Public
File B	Confidential
File C	Secret

Muhammad has a Confidential security clearance.

Under the simplified hierarchical model used in this example:

Resource	Required classification	Muhammad’s clearance	Result
File A	Public	Confidential	Allowed
File B	Confidential	Confidential	Allowed
File C	Secret	Confidential	Denied

Muhammad can access File A and File B, but he cannot access File C because his clearance is below the required classification.

3. Typical Security Classification Levels

A hierarchical classification system might look like this:

1. Public
2. Confidential
3. Secret
4. Top Secret

In this simplified hierarchy, higher clearance levels can satisfy lower classification requirements.

However, real-world MAC systems may also enforce additional restrictions, such as compartments, security categories, and need-to-know rules.

Having a high clearance does not necessarily mean a user can access every resource at that level.

4. Who Controls Access in MAC?

Access decisions are controlled by a central security authority or system policy.

For example:

* The organization defines classification levels.
* Security administrators assign user clearances.
* Resources receive classification labels.
* The system evaluates access requests.
* Users cannot override the security policy simply because they own or created a file.

This makes MAC particularly useful when an organization needs consistent, centrally enforced security rules.

5. Advantages of MAC

* Strong security: Access is governed by strict, centrally enforced policies.
* Centralized control: Individual users cannot freely change security permissions.
* Consistent enforcement: The same security rules apply throughout the environment.
* Protection of sensitive information: Users cannot access information above their authorized clearance.
* Suitable for high-security environments: Useful when protecting classified or highly sensitive information is essential.

6. Disadvantages of MAC

* Less flexibility: Users cannot freely share resources with other users.
* Administrative overhead: Assigning clearances and maintaining classifications requires careful administration.
* Complexity: Security policies can become complicated, particularly when additional categories and compartments are introduced.
* Slower collaboration: Users may need administrators to approve changes to access or classification.
* Strict policy requirements: Incorrect classifications or clearance assignments can prevent legitimate access.

7. MAC vs. DAC

The most important difference is who controls access.

Feature	DAC	MAC
Full name	Discretionary Access Control	Mandatory Access Control
Access controlled by	Resource owner	Central authority and system policy
Permission management	Owners can grant permissions, subject to system restrictions	Centrally defined security rules
Flexibility	More flexible	More rigid
Security enforcement	Depends partly on owner decisions	Centrally enforced
Common use cases	File sharing and collaboration	Government, military, and high-security environments

Simple way to remember

* DAC: The resource owner decides who can access the resource.
* MAC: The central security policy decides who can access the resource.

8. MAC and the Principle of Least Privilege

MAC supports the Principle of Least Privilege (PoLP) by restricting users to information that their security clearance and applicable policies permit them to access.

For example, if Muhammad has Confidential clearance, the system prevents him from accessing Secret information.

However, clearance alone does not necessarily establish that he needs access to every Confidential resource. Additional need-to-know restrictions can further limit access.

9. Key Takeaways

1. MAC stands for Mandatory Access Control.
2. It enforces centrally defined security policies.
3. Users receive security clearance levels.
4. Resources receive security classification labels.
5. Access depends on whether the user’s clearance satisfies the resource’s classification and other applicable rules.
6. Individual resource owners cannot freely override MAC policies.
7. MAC is especially useful in environments where protecting sensitive information is a priority.
8. MAC is less flexible than DAC but provides stronger centralized control.

