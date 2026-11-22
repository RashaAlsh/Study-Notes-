Single Sign-On (SSO)

1. What Is Single Sign-On?

Single Sign-On (SSO) is an authentication method that allows a user to access multiple applications or services using one set of login credentials and one authentication process.

Instead of signing in separately to every application, the user authenticates once and can then access other connected applications without repeatedly entering their username and password.

Simple example

Imagine signing in to your Google account through Gmail.

After signing in, you can also access other Google services, such as:

* Google Drive
* YouTube
* Google Calendar

You do not necessarily need to enter your password again for each service because Google manages authentication across its connected services.

SSO acts like a universal key that provides access to multiple connected applications after the user has been authenticated.

2. Why Is SSO Important?

Imagine working for a company that uses several applications:

* Email for communication.
* Project management software for tracking tasks.
* Time-tracking software for recording working hours.
* Cloud storage for sharing documents.
* HR software for employee information.

Without SSO, you might need to remember separate usernames and passwords for every application.

This creates several problems:

* Password fatigue: Users must remember too many passwords.
* Repeated logins: Employees waste time signing in to different applications.
* Password reuse: Users may reuse passwords across multiple services.
* IT support workload: Forgotten passwords can generate additional support requests.

SSO simplifies this experience by allowing employees to authenticate once and access multiple connected applications.

3. How Does SSO Work?

SSO generally uses a central identity provider (IdP) or authentication server to verify the user’s identity.

Here is the simplified process:

Step 1: User login

The user opens an application or an SSO portal and enters their login credentials.

For example:

* Username
* Password

Step 2: Identity verification

The identity provider checks the user’s credentials.

It determines whether the user is who they claim to be.

Depending on the organization’s security configuration, this process may also require MFA.

Step 3: Token generation

After successful authentication, the identity provider issues an authentication token or assertion.

This is a secure digital representation of the user’s authenticated identity.

The token allows connected applications to verify that the user has already authenticated.

Step 4: Automatic access to connected applications

When the user opens another connected application, that application can validate the token or obtain the necessary authentication information through the SSO protocol.

If the authentication is valid and the user is permitted to access the application, access is granted without requiring the user to enter their password again.

Simplified workflow

       User
         |
         v
  Opens an application
         |
         v
  Enters login credentials
         |
         v
  Identity Provider (IdP)
         |
         v
  Verifies the user's identity
         |
         v
  Issues authentication token
         |
         v
  Connected applications
         |
         v
  Access without repeated login

4. Technical Perspective: How Does SSO Work?

SSO relies on communication between an identity provider and the applications that trust it.

There are three important components:

Component	Responsibility
User	The person trying to access applications
Identity Provider (IdP)	Authenticates the user and issues authentication information
Service Provider (SP)	The application that relies on the IdP to authenticate users

For example:

* A company identity platform can act as the Identity Provider.
* An email or project management application can act as a Service Provider.
* The employee is the user.

The IdP verifies the employee’s identity, and the connected applications trust the authentication information provided through the configured SSO relationship.

Common SSO protocols

SSO can use different protocols to securely exchange authentication information.

Protocol	Full name	Main purpose
SAML	Security Assertion Markup Language	Exchanges authentication and authorization-related information, commonly in enterprise web SSO
OAuth 2.0	Open Authorization 2.0	Allows applications to obtain delegated access to resources
OpenID Connect (OIDC)	OpenID Connect	Adds an identity and authentication layer on top of OAuth 2.0

Important distinction:

OAuth 2.0 is primarily an authorization framework, not an authentication protocol by itself.

OpenID Connect builds on OAuth 2.0 and provides a standardized way to authenticate users.

SAML and OpenID Connect are commonly used for SSO.

5. What Is an Authentication Token?

An authentication token is a digital piece of information that helps an application verify an authenticated user’s identity.

Think of it as a digital passport.

Instead of sending the user’s password to every connected application, the identity provider supplies authentication information that the applications can validate.

A token or assertion can contain information such as:

* The user’s identity.
* The issuing identity provider.
* The intended recipient or application.
* The time the token was issued.
* Its expiration time.
* Other relevant authentication claims.

Applications must validate the token or assertion correctly, including its signature, issuer, audience, and validity period.

Security note: Tokens must be protected. If an attacker steals a valid session token, they may be able to impersonate the authenticated user without knowing the user’s password.

6. Practical Example: Google SSO

Consider a user who signs in to Gmail using a Google account.

After authentication, the user can access other connected Google services, such as:

* Google Drive.
* YouTube.
* Google Calendar.

The user does not need to enter their password separately for every service.

Google manages the authentication experience across its services.

This is a familiar example of the convenience of a shared sign-in experience.

7. Benefits of Single Sign-On

SSO provides several important benefits for organizations and users.

1. Convenience

Users authenticate once and can access multiple connected applications.

They do not need to repeatedly enter their credentials.

2. Improved security management

SSO can reduce the number of passwords users need to remember.

This can reduce password reuse and the temptation to use weak passwords.

It also allows organizations to centralize authentication policies, such as MFA requirements and login restrictions.

3. Increased productivity

Employees spend less time logging in and switching between applications.

This reduces login-related delays and interruptions.

4. Better user experience

SSO creates a smoother and more consistent login experience for employees and customers.

5. Centralized access control

Organizations can manage authentication through a central identity provider.

For example, when an employee leaves a company, administrators can disable their central identity account to prevent future SSO authentication to connected applications.

However, organizations should also verify that application-specific accounts, sessions, tokens, and other access paths are properly revoked.

8. SSO and Security: Important Considerations

Although SSO provides convenience and security benefits, it also introduces risks that organizations must manage.

Central point of failure

If the identity provider becomes unavailable, users may lose access to multiple connected applications.

High-value target

If an attacker compromises an employee’s central identity account, they may gain access to several connected applications.

Session and token theft

An attacker who steals a valid authentication token or session may be able to access an application without knowing the user’s password.

Recommended security measures

Organizations should combine SSO with:

* Multi-Factor Authentication (MFA).
* Strong password policies.
* Conditional or risk-based access policies.
* Session management and token protection.
* Monitoring and auditing.
* Least Privilege.
* Proper account deprovisioning when employees leave.

SSO should simplify authentication without removing the need for strong access controls.

9. SSO vs. MFA

SSO and MFA are related IAM concepts, but they solve different problems.

Feature	SSO	MFA
Main purpose	Simplifies access to multiple applications	Strengthens identity verification
Focus	One authentication process across connected apps	Multiple authentication factors
Main benefit	Convenience and centralized authentication	Reduced risk of account compromise
Example	Sign in once to access email and project tools	Password plus authenticator app

Can SSO and MFA work together?

Yes!

For example:

1. An employee opens the company’s SSO portal.
2. They enter their username and password.
3. The identity provider requests an MFA verification code.
4. The employee successfully completes MFA.
5. The identity provider authenticates the employee.
6. The employee can access connected applications without repeatedly signing in.

This combines the convenience of SSO with the additional security of MFA.

10. How SSO Fits into IAM

SSO is an important part of modern Identity and Access Management.

It helps organizations centralize authentication and simplify access to multiple applications.

A simplified IAM process looks like this:

1. Identification: The user claims an identity, usually by entering a username.
2. Authentication: The identity provider verifies the user’s identity.
3. SSO: The authentication result is used to provide access to connected applications.
4. Authorization: Each application determines what the user is allowed to access and do.
5. Accounting: User activities are recorded for monitoring and auditing.

Remember that authentication and authorization are different.

SSO helps establish that a user has authenticated. It does not automatically mean the user should have administrator privileges in every connected application.

Each application must still enforce appropriate permissions.

11. Key Takeaways

* SSO stands for Single Sign-On.
* SSO allows users to access multiple connected applications through one authentication process.
* Users do not need to repeatedly enter their credentials for every connected application.
* An Identity Provider (IdP) authenticates users.
* Service Providers (SPs) rely on the identity provider’s authentication information.
* Authentication tokens or assertions help applications verify authentication.
* Common SSO technologies include SAML and OpenID Connect.
* OAuth 2.0 is an authorization framework that OpenID Connect builds upon.
* SSO improves convenience, productivity, and centralized authentication management.
* SSO should be combined with MFA, least privilege, monitoring, and strong session security.
* SSO does not replace authorization.

12. Final Summary

Single Sign-On simplifies access to multiple applications by allowing users to authenticate once through a central identity provider.

After successful authentication, connected applications can trust the identity provider’s authentication information and allow access without requiring users to repeatedly enter their credentials.

For organizations, SSO improves the user experience, reduces password fatigue, and centralizes authentication management.

However, because one identity account can provide access to multiple applications, protecting that account is especially important.

The key principle: Authenticate once, access multiple trusted applications, and continue enforcing authorization for every application.

