Introduction to Authentication Methods

1. What is Authentication?

Authentication is the process of verifying that a user is who they claim to be before allowing them to access a system, application or resource.

In simple terms:

Authentication = Proving your identity.

For example, when you log in to GitHub using your username and password, GitHub checks whether the credentials are valid.

Authentication methods use different factors to verify a user’s identity.

These factors are commonly grouped into:

1. Primary Authentication Factors.
2. Secondary Authentication Factors.

⸻

2. Primary Authentication Factors

Primary authentication factors are the main categories of evidence used to verify someone’s identity.

There are three traditional primary authentication factors:

1. Something You Know.
2. Something You Have.
3. Something You Are.

These are also known as the three traditional authentication factors.

2.1 Something You Know – Knowledge-Based Authentication

This authentication factor relies on information that only the user should know.

Examples:

* Passwords.
* PIN codes.
* Security question answers.

Real-Life Example

Imagine you want to log in to your online banking account.

You enter your username and password.

The banking system checks whether your password matches the stored authentication information.

If the credentials are correct, authentication can succeed.

Advantages

* Easy to implement.
* Widely supported.
* Relatively inexpensive.
* Does not require specialized hardware.

Disadvantages

* Passwords can be stolen.
* Users may reuse passwords.
* Weak passwords can be guessed.
* Users can fall victim to phishing attacks.

Remember: Something You Know = Password, PIN or Secret Information.

⸻

2.2 Something You Have – Possession-Based Authentication

This authentication factor relies on something the user physically possesses.

Examples:

* Mobile phones.
* Smart cards.
* Hardware security keys.
* Authentication tokens.
* One-Time Password (OTP) generators.

Real-Life Example

Imagine you log in to your company account.

After entering your password, the system sends a verification code to your mobile phone.

You enter the code to prove that you have access to the registered device.

Another example is using a physical security key to authenticate to GitHub.

Advantages

* Adds another layer of security.
* Requires possession of a registered device or token.
* Can reduce the risk of password-only account compromise.

Disadvantages

* Devices can be lost or stolen.
* Hardware tokens can be expensive.
* SMS verification can be vulnerable to SIM-swapping attacks.
* Users may lose access to their authentication device.

Remember: Something You Have = Phone, Smart Card or Security Token.

⸻

2.3 Something You Are – Biometric-Based Authentication

This authentication factor relies on unique physical or biological characteristics of an individual.

Examples:

* Fingerprints.
* Facial recognition.
* Iris scans.
* Retina scans.
* Voice recognition.

Real-Life Example

Imagine unlocking your smartphone using your fingerprint.

The device compares your fingerprint with the biometric information enrolled on the device.

If the verification succeeds, access is granted.

Advantages

* Convenient and quick.
* Difficult to replicate compared with ordinary passwords.
* Does not require remembering a password.
* Can provide strong identity verification.

Disadvantages

* Requires compatible hardware.
* Biometric information is sensitive.
* Biometric systems can produce false matches or false rejections.
* Unlike passwords, compromised biometric characteristics cannot simply be changed.

Remember: Something You Are = Fingerprint, Face or Iris.

⸻

3. Secondary Authentication Factors

Secondary factors provide additional context that can help security systems identify suspicious access attempts.

They can make it harder for attackers to misuse compromised credentials.

Two examples covered in this lecture are:

1. Somewhere You Are.
2. Something You Do.

Important: These are often described as contextual or behavioral authentication signals rather than universally recognized primary authentication factors. They can support risk-based authentication but do not automatically prove identity on their own.

3.1 Somewhere You Are – Location-Based Authentication

This factor uses information about the user’s geographical location to evaluate an access attempt.

Examples:

* IP address.
* GPS location.
* Country.
* City.
* Network location.

Real-Life Example

Imagine you normally log in to your company account from the Netherlands.

Suddenly, someone attempts to access your account from another country.

The security system identifies an unusual location.

It may:

* Trigger an additional verification step.
* Require MFA.
* Block the login attempt.
* Generate a security alert.

This helps identify potentially suspicious login attempts.

Advantages

* Helps detect unusual login locations.
* Provides additional security context.
* Supports risk-based authentication.
* Can identify impossible or unusual travel patterns.

Disadvantages

* VPNs can change apparent locations.
* IP geolocation is not always accurate.
* Employees may travel internationally.
* Legitimate users can be incorrectly flagged.

Remember: Somewhere You Are = Your Location.

⸻

3.2 Something You Do – Behavioral-Based Authentication

This factor analyzes patterns in how a person interacts with a device or system.

Examples:

* Typing speed.
* Typing rhythm.
* Mouse movement patterns.
* Device usage habits.
* Interaction patterns.

Real-Life Example

Imagine you normally type at a particular speed and follow a consistent typing pattern.

Suddenly, your account starts showing completely different typing behavior.

A security system may identify this as unusual behavior.

It could trigger additional verification or generate an alert.

This is an example of behavioral authentication.

Advantages

* Can continuously analyze user behavior.
* Helps detect unusual account activity.
* Can operate in the background.
* Provides additional security context.

Disadvantages

* Behavior can change naturally.
* Requires data collection and analysis.
* Can generate false alerts.
* Raises privacy considerations.

Remember: Something You Do = Your Behavior and Habits.

⸻

4. Authentication Factors – Comparison Table

Authentication Factor	Meaning	Examples
Something You Know	Knowledge	Password, PIN
Something You Have	Possession	Phone, smart card, security key
Something You Are	Biometrics	Fingerprint, face, iris
Somewhere You Are	Location	IP address, GPS
Something You Do	Behavior	Typing speed, mouse movements

⸻

5. Primary vs Secondary Factors

Primary Factors	Contextual / Behavioral Factors
Something You Know	Somewhere You Are
Something You Have	Something You Do
Something You Are	
Traditional authentication factors	Additional risk and identity signals

The three primary factors are the traditional categories used to establish multi-factor authentication.

Location and behavioral signals can strengthen authentication decisions, particularly in risk-based and continuous authentication systems.

⸻

6. Understanding Multi-Factor Authentication (MFA)

Multi-Factor Authentication (MFA) requires users to provide evidence from at least two different authentication factor categories.

For example:

* Password = Something You Know.
* Security key = Something You Have.

Using both provides two different authentication factors.

Example: Logging in to GitHub

Imagine you log in to GitHub using:

1. Your password.
2. A registered security key.

The password proves knowledge.

The security key proves possession.

Together, they provide Multi-Factor Authentication.

MFA vs Two-Step Verification

These terms are related but not identical.

* MFA: Requires two or more different authentication factor categories.
* Two-Step Verification: Requires two separate verification steps, which may or may not use different factor categories.

For example, a password followed by a PIN is two steps but both are knowledge-based factors.

⸻

7. How Authentication Factors Connect to IAM

Authentication is an essential part of Identity and Access Management (IAM).

IAM uses authentication to verify users before access decisions are made.

Example:

1. A user enters their username and password.
2. The system verifies their identity.
3. Additional authentication may be requested.
4. Authorization checks their permissions.
5. Access is granted or denied.
6. User activity may be recorded for auditing.

Authentication answers:

Who are you?

Authorization answers:

What are you allowed to do?

⸻

8. Final Summary

Authentication methods help organizations verify the identity of users before granting access to systems and resources.

The three traditional primary authentication factors are:

Something You Know

* Passwords.
* PINs.
* Security questions.

Something You Have

* Mobile phones.
* Smart cards.
* Security keys.
* Authentication tokens.

Something You Are

* Fingerprints.
* Facial recognition.
* Iris scans.
* Voice recognition.

Additional contextual and behavioral signals include:

Somewhere You Are

* IP address.
* GPS location.
* Geographical location.

Something You Do

* Typing speed.
* Mouse movement.
* Device usage habits.

Key Takeaway

Remember the five concepts:

1. Something You Know = Knowledge.
2. Something You Have = Possession.
3. Something You Are = Biometrics.
4. Somewhere You Are = Location.
5. Something You Do = Behavior.

The three traditional factors form the foundation of authentication, while location and behavioral signals can provide additional security context.
