Cybersecurity Risks in AI Systems

1. Introduction

Artificial Intelligence (AI) and Machine Learning (ML) introduce new cybersecurity challenges.

Traditional cybersecurity focuses on protecting systems, networks, applications, hardware, and data. These protections are still essential for AI systems, but they are not enough.

AI systems have additional components that attackers can target:

* Training data
* Machine learning models
* Model repositories
* Model training and testing processes
* Production data
* Model outputs and predictions

The key difference is that AI systems learn patterns from data. If an attacker manipulates the data or model, the AI system may learn incorrect behavior and make incorrect decisions.

For example, manipulating a facial recognition model could cause it to fail to recognize a particular person.

2. Three Ways AI Creates Security Risks

AI can create or contribute to cybersecurity risks in three main ways.

Risk category	Explanation	Example
Unintentional risk	AI creates security problems unintentionally because of errors, weaknesses, or poor implementation.	An AI system makes an unsafe decision because of biased or incorrect training data.
Malicious use of AI	Attackers use AI as a tool to improve or automate cyberattacks.	Criminals use AI to generate convincing phishing messages.
AI system compromise	Attackers directly compromise the AI system, its data, model, or supporting infrastructure.	An attacker inserts a backdoor into a machine learning model.

These categories can overlap. For example, an attacker could compromise an AI model and then use it to cause harmful decisions.

3. Why AI Changes the Threat Landscape

As AI becomes more powerful and widely adopted, the cybersecurity threat landscape changes.

The lecture refers to the 2017 report The Malicious Use of Artificial Intelligence, which explored how advances in AI could affect security.

The report highlighted several important developments:

3.1 Existing threats can expand

AI can make existing cyberattacks more effective, scalable, and automated.

For example:

* Phishing messages can become more convincing.
* Malware development and modification can be assisted by AI.
* Attackers can automate parts of their operations.
* DDoS attacks and other existing threats may evolve as attackers adopt AI techniques.

3.2 The cost of attacks can decrease

AI can automate tasks that previously required significant human effort.

This could make sophisticated attacks cheaper and more accessible to less-skilled attackers.

3.3 New threats can emerge

AI introduces attack possibilities that may not have been practical with traditional systems.

For example:

* Manipulating training data to influence model behavior.
* Inserting hidden backdoors into machine learning models.
* Creating inputs that deliberately confuse an AI model.
* Extracting information about a model through repeated queries.

3.4 Existing attacks can change

Traditional attacks may be adapted to exploit AI-specific weaknesses.

This means cybersecurity professionals need to understand both traditional security threats and threats associated with machine learning.

4. Two Categories of AI Security Risks

AI security risks can be divided into two broad categories.

Category	Meaning	Example
Risks not unique to AI	Traditional cybersecurity attacks against the infrastructure, applications, or data supporting an AI system.	A hacker exploits a vulnerable server hosting an AI application.
Risks unique to AI	Attacks that exploit the behavior, data, training process, or models of AI systems.	An attacker poisons training data so the model learns incorrect patterns.

4.1 Risks that are not unique to AI

These are familiar cybersecurity problems that also affect AI environments.

Examples include:

Infrastructure security

* Poorly configured servers and cloud services.
* Weak network security.
* Unpatched operating systems and applications.
* Excessive user permissions.
* Exposed management interfaces.

Data security

* Unauthorized access to datasets.
* Data breaches during storage or transmission.
* Weak encryption.
* Poor access controls.
* Improper handling of sensitive information.

Knowledge and skills gaps

Another important risk is a lack of knowledge about AI security.

AI specialists may understand machine learning but lack cybersecurity experience. Traditional security professionals may understand infrastructure security but lack knowledge of machine learning attacks.

Organizations need people who understand both disciplines.

4.2 Risks unique to AI

AI-specific attacks target the components that make machine learning systems work.

Important examples include:

* Data poisoning
* Model poisoning and backdoors
* Model evasion
* Model extraction
* Data extraction through model queries

These attacks are explained in the following sections.

5. Understanding the Machine Learning Lifecycle

To understand AI security risks, it helps to understand the lifecycle of a machine learning model.

A simplified lifecycle looks like this:

1. Obtain or collect training data.
2. Select or obtain a machine learning model.
3. Train the model.
4. Test and evaluate the model.
5. Optimize or fine-tune the model.
6. Deploy the model into production.
7. Monitor and maintain the model.

Security weaknesses can occur at every stage.

6. Data Poisoning

Data poisoning occurs when an attacker deliberately manipulates the data used to train a machine learning model.

Remember that machine learning models learn patterns from training data.

If the training data is manipulated, the model may learn incorrect patterns and produce unreliable predictions.

Example

Imagine a company training an image recognition model to identify different animals.

An attacker gains access to the training dataset and changes some labels:

* Images of cats are labelled as dogs.
* Images of dogs are labelled as cats.

The model is then trained using this manipulated dataset.

As a result, it may learn incorrect relationships between images and labels.

Where can data poisoning happen?

* During the collection of training data.
* When importing datasets from external sources.
* When using publicly available datasets.
* During model retraining or fine-tuning.
* When production data is incorporated into future training.

Why is it dangerous?

The model may appear to function normally while consistently making incorrect decisions.

Data poisoning can be difficult to detect because the manipulated data may look legitimate.

7. Model Poisoning and Backdoors

Model poisoning involves manipulating a machine learning model itself.

An attacker may modify a model before an organization downloads or uses it.

This is particularly relevant because organizations often reuse existing models instead of training everything from scratch.

They may obtain models from:

* Commercial AI providers.
* Open-source repositories.
* Public model libraries.
* External suppliers.
* Third-party development teams.

What is a model backdoor?

A backdoor is a hidden mechanism that causes a model to behave in an unintended way under particular conditions.

The model may appear to work normally in most situations, but a specific trigger can activate the malicious behavior.

Example 1: Facial recognition

Imagine an organization downloads a facial recognition model.

An attacker secretly modifies the model so that a particular person’s face is not recognized.

The organization may not notice the problem during ordinary testing.

Example 2: Autonomous vehicles

Imagine an image recognition model used by an autonomous vehicle.

An attacker compromises the model so that it misclassifies certain stop signs.

The vehicle may fail to recognize a stop sign correctly, potentially causing a dangerous situation.

Important distinction:

* Data poisoning manipulates the data used to train a model.
* Model poisoning manipulates the model itself.
* A backdoor is a hidden malicious behavior that can be introduced into a model.

8. Security Risks Throughout the AI Model Lifecycle

Different attacks can occur at different stages of the machine learning lifecycle.

Lifecycle stage	Potential security risk	Explanation
Model acquisition	Model poisoning / backdoors	An attacker modifies a model in an external repository before an organization downloads it.
Data collection and preparation	Data poisoning	Training data is manipulated or incorrect labels are introduced.
Model training	Data poisoning	The model learns from contaminated training data.
Model testing	Data poisoning / data breaches	Testing datasets may be manipulated or exposed.
Model optimization and fine-tuning	Data poisoning / data breaches	Additional training data or sensitive information may be manipulated or exposed.
Model deployment	Model compromise	Vulnerabilities in the application, infrastructure, or supporting software are exploited.
Model operation	Model evasion	Carefully crafted inputs cause the model to make incorrect predictions.
Model operation	Model extraction / data extraction	Repeated queries reveal information about the model or its data.
Any lifecycle stage	Software and infrastructure compromise	Vulnerable libraries, applications, or servers are exploited.

9. Model Evasion

Model evasion occurs when an attacker creates or modifies an input to cause an AI model to make an incorrect prediction.

The attacker does not necessarily need to compromise the model or its training data. Instead, the attacker manipulates what the model receives.

Example: Image recognition

Imagine an AI model trained to recognize cats.

An attacker takes an image of a cat and makes very small changes to its pixels.

These changes may be almost impossible for a human to notice, but they can cause the AI model to classify the image incorrectly.

This type of carefully crafted input is often called an adversarial example.

Why is model evasion dangerous?

It can affect systems that rely on AI predictions, including:

* Facial recognition.
* Fraud detection.
* Spam detection.
* Malware detection.
* Autonomous vehicles.
* Security monitoring systems.

The model may still be operating normally from a software perspective, but its predictions are wrong.

10. Model Extraction

Model extraction occurs when an attacker repeatedly queries an AI model and uses its responses to recreate or approximate the model.

How does it work?

Imagine a company owns a proprietary machine learning model.

The company makes the model available through an API.

An attacker can:

1. Send many carefully selected inputs to the model.
2. Collect the model’s responses.
3. Identify patterns between inputs and outputs.
4. Use those patterns to train another model.
5. Create a substitute that approximates the original model’s behavior.

Why is it dangerous?

The model may represent valuable intellectual property.

Model extraction can lead to:

* Loss of proprietary technology.
* Unauthorized copying of model behavior.
* Competitive disadvantages.
* Reduced control over the organization’s AI technology.

11. Data Extraction

Data extraction involves obtaining sensitive or confidential information through interactions with an AI system.

Depending on the system, an attacker may use repeated queries or exploit weaknesses to reveal information that should not be exposed.

For example:

* An AI model may unintentionally reveal information about its training data.
* A chatbot may expose confidential information from connected sources.
* An attacker may exploit an insecure API to retrieve data.

Model extraction vs. data extraction

Model extraction	Data extraction
Focuses on recreating or approximating the model.	Focuses on obtaining information or data.
Threatens intellectual property and proprietary model behavior.	Threatens confidentiality and privacy.
Uses model responses to infer how the model works.	Uses model interactions or vulnerabilities to reveal sensitive information.

These attacks are related, but they target different assets.

12. Model Compromise

Model compromise refers to an attacker gaining unauthorized control over the model or the software and infrastructure supporting it.

The lecture emphasizes that not every model compromise involves manipulating the machine learning algorithm directly.

An attacker may instead exploit traditional software vulnerabilities.

For example:

* A vulnerable application hosting the model.
* An insecure API.
* Compromised software libraries.
* Weak authentication or access controls.
* Unauthorized access to model files.
* A compromised cloud environment.

Why does this matter?

AI models depend on software, hardware, cloud infrastructure, APIs, and external libraries.

If one of these components is compromised, the AI system may also be affected.

This is why traditional security practices remain essential.

13. Traditional Cybersecurity vs. AI-Specific Security

AI security requires both traditional cybersecurity controls and controls designed for machine learning systems.

Traditional cybersecurity	AI-specific cybersecurity
Secure servers and networks.	Protect training data and model artifacts.
Patch vulnerable software.	Validate model sources and dependencies.
Apply access controls.	Restrict access to training pipelines and model repositories.
Encrypt sensitive data.	Detect manipulated datasets and suspicious model behavior.
Perform penetration testing.	Test for adversarial inputs and model extraction.
Monitor application logs.	Monitor model queries, predictions, and unusual inference patterns.

Neither approach replaces the other. Both are necessary.

14. Practical Security Measures

The lecture focuses mainly on identifying risks. These examples show how organizations can begin addressing them.

Protect training data

* Validate data sources.
* Restrict who can modify datasets.
* Check data quality and labels.
* Maintain dataset version history.
* Monitor for unusual changes.

Protect machine learning models

* Obtain models from trusted sources.
* Verify model integrity using hashes or signatures where available.
* Scan model dependencies.
* Restrict access to model repositories.
* Test models for hidden or unexpected behavior.

Protect the model lifecycle

* Apply least privilege to data scientists and developers.
* Separate development, testing, and production environments.
* Secure APIs and model endpoints.
* Log model access and administrative changes.
* Monitor for unusual query patterns.

Test AI-specific weaknesses

* Test models with adversarial inputs.
* Evaluate model behavior under unusual conditions.
* Assess whether repeated queries reveal too much information.
* Check whether sensitive training data can be extracted.
* Review model behavior after updates and fine-tuning.

15. Key Terms to Remember

Term	Simple definition
AI security	Protecting AI systems, models, data, and supporting infrastructure.
Data poisoning	Manipulating training data to influence model behavior.
Model poisoning	Maliciously modifying a machine learning model.
Backdoor	Hidden behavior that activates under particular conditions.
Model evasion	Crafting inputs that cause a model to make incorrect predictions.
Adversarial example	An input deliberately modified to mislead an AI model.
Model extraction	Reconstructing or approximating a model through its outputs.
Data extraction	Obtaining sensitive information through a model or its interfaces.
Model compromise	Unauthorized access to or control over a model or its supporting software.
Model repository	A location where machine learning models are stored and shared.
Fine-tuning	Further training an existing model on additional data.
Production data	Data handled by a deployed system during real-world operation.

16. Important Distinctions

These differences are particularly useful to remember:

Attack	What does the attacker target?	Main objective
Data poisoning	Training data	Make the model learn incorrect patterns.
Model poisoning	The model itself	Introduce malicious changes or behavior.
Backdoor	Hidden behavior in a model	Trigger malicious behavior under specific conditions.
Model evasion	Model inputs	Cause incorrect predictions.
Model extraction	Model outputs and query interface	Recreate or approximate the model.
Data extraction	Sensitive information	Reveal confidential data.
Model compromise	Model, application, or supporting infrastructure	Gain unauthorized access or control.

17. Key Takeaways

1. AI systems introduce cybersecurity risks beyond traditional infrastructure and application security.
2. AI can create risks unintentionally, be used maliciously, or become directly compromised.
3. AI increases the scale and potential effectiveness of existing cyberattacks while introducing new attack techniques.
4. Data poisoning manipulates the information used to train a model.
5. Model poisoning manipulates the model itself and may introduce hidden backdoors.
6. Model evasion uses carefully crafted inputs to mislead an AI model.
7. Model extraction attempts to recreate a model by analyzing its responses.
8. Data extraction targets sensitive information that may be exposed through an AI system.
9. Traditional cybersecurity remains essential because AI systems depend on ordinary software, networks, cloud services, and infrastructure.
10. AI security must be considered throughout the entire model lifecycle, not only after deployment.

