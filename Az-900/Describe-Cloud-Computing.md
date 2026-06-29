Domain 1.1 — Describe Cloud Computing (Complete Study Notes)
1. What is Cloud Computing?

Cloud computing is the delivery of computing services over the internet.

Instead of buying and managing your own physical infrastructure (servers, storage, networking), you use resources provided by a cloud provider.

Examples of cloud services:
* Compute (virtual machines, applications)
* Storage
* Databases
* Networking
* Security services
* Artificial Intelligence (AI)
* Machine Learning (ML)
* Internet of Things (IoT)


Examples of cloud providers:
* Microsoft Azure
* Amazon Web Services
* Google Cloud
 
⸻
 
2. Why Use Cloud Computing? (Benefits)
1. Cost-effective
Traditional IT:
* Buy servers
* Build data centres
* Maintain hardware
* Replace equipment
Cloud:
* No need to buy expensive hardware upfront
* Pay for resources when needed


Cloud reduces:
* Capital Expenditure (CapEx)
Cloud increases:
* Operational Expenditure (OpEx)
 
⸻
 
2. Scalability
Scalability = ability to increase or decrease resources to meet demand.
Example:

A website normally needs:
* 2 servers
During a sale:
* Traffic increases
* Add more servers
After the sale:
* Remove extra servers
 
⸻
 
3. Elasticity
Elasticity = automatic scaling based on demand.
Difference:
Scalability:
You can increase resources.
Elasticity:
The system automatically increases and decreases resources.
Example:
A streaming service automatically adds capacity during a popular event and removes it afterward.
 
⸻
 
4. Global Availability
Cloud providers have data centres around the world.

Benefits:
* Deploy applications closer to customers
* Better performance
* Disaster recovery options

Example:
A company in Europe can run services in European data centres while serving customers worldwide.
 
⸻
 
5. Security

Cloud providers offer:
* Encryption
* Identity management
* Monitoring
* Threat protection
* Backup
* Disaster recovery

Important: Cloud does not mean automatic security.
Security is shared between provider and customer.
 
⸻
 
3. Cloud Services Examples
Artificial Intelligence (AI)
AI allows computers to perform tasks that normally require human intelligence.
Examples:

* Speech recognition
* Image recognition
* Chatbots
* Decision-making
 
⸻
 
Machine Learning (ML)

Machine learning is a part of AI where systems learn from data.
Example:
Email system:
* Learns patterns from spam emails
* Predicts whether future emails are spam
 
⸻
 
Internet of Things (IoT)
IoT connects physical devices to the internet.
Examples:
* Smart watches
* Smart homes
* Sensors
* Industrial machines
IoT devices:
* Collect data
* Send data to the cloud
* Allow monitoring and automation
 
⸻
 
4. Cloud Deployment Models
There are three main cloud models:
1. Public Cloud
2. Private Cloud
3. Hybrid Cloud
 
⸻
 
Public Cloud
Definition:
A cloud environment where the cloud provider owns and manages the hardware.
Examples:
* Azure
* AWS
* Google Cloud
The customer rents resources.
 
⸻
 
Advantages:
Scalability
Easily increase resources.
Agility
Quickly create applications and services.
Pay-as-you-go
Pay only for what you use.
No hardware maintenance
The provider manages:
* Servers
* Networking
* Physical infrastructure
Lower skills required
You do not need to manage data centre hardware.
 
⸻
 
Public Cloud Use Cases:
* Websites
* Mobile applications
* Startups
* Development and testing
* Online services
* Businesses needing fast growth
Example:
A startup launches an app globally without buying servers.
 
⸻
 
Private Cloud
Definition:
A cloud environment dedicated to one organization.
It can be:
* Inside the company’s own data centre
* Hosted by a provider but dedicated to one company
 
⸻
 
Advantages:
More control
The organization controls:

* Infrastructure
* Security settings
* Data location
 
⸻
 
Compliance
Useful for industries with strict rules:
Examples:

* Banking
* Healthcare
* Government
 
⸻
 
Legacy Support
Older applications may require:
* Specific hardware
* Specific configurations
Private cloud can support these systems.
 
⸻
 
Private Cloud Use Cases:
* Banks
* Government systems
* Healthcare systems
* Companies with sensitive data
Example:
A hospital stores patient information in a private cloud.
 
⸻
 
Hybrid Cloud
Definition:
A combination of public cloud and private cloud.
Some workloads run privately. Others run publicly.
 
⸻
 
Advantages:
Flexibility
Choose where workloads run.
Example: Sensitive data → private cloud Public website → public cloud
 
⸻
 
Scalability
Use public cloud resources when demand increases.
 
⸻
 
Compliance
Keep regulated data in private environments.
 
⸻
 
Hybrid Use Case:
A bank:
Private cloud:
* Customer records
Public cloud:
* Website
* Analytics
* Extra computing power
 
⸻
 
5. Shared Responsibility Model
Definition:
The cloud provider and customer share responsibility for security.
The responsibility changes depending on the service used.
 
⸻
 
Cloud Provider Responsibility
The provider manages:
Physical security
* Buildings
* Data centres
* Hardware
Infrastructure
* Servers
* Storage
* Networking
Cloud platform
* Maintaining cloud services
Example:
Microsoft protects Azure data centres.
 
⸻
 
Customer Responsibility
The customer manages:
Data
* Protect information
* Backup decisions
Identity and Access
* User accounts
* Passwords
* Permissions
Applications
* Secure your code
Configuration
* Correct settings
Example:
You are responsible for who can access your cloud resources.
 
⸻
 
Memory:
Provider = Security OF the cloud
Customer = Security IN the cloud
 
⸻
 
6. CapEx vs OpEx
Capital Expenditure (CapEx)
Money spent upfront on physical assets.
Examples:
* Buying servers
* Building a data centre
* Buying networking equipment
Characteristics:
* Large upfront cost
* You own the equipment
* Long-term investment
Example:
Company buys $200,000 worth of servers.
 
⸻
 
Operational Expenditure (OpEx)
Money spent on ongoing services.
Examples:
* Cloud subscriptions
* Storage usage
* Software licenses
Characteristics:
* Pay over time
* Flexible costs
* Based on usage
Example:
Company pays monthly Azure bills.
 
⸻
 
Cloud impact:
Traditional IT: More CapEx
Cloud: More OpEx
 
⸻
 
7. Cloud Pricing Models
Consumption-Based Pricing
Also called:
Pay-as-you-go
You pay only for what you use.
Pricing can be based on:
 
⸻
 
Unit
Pay per item.
Example:
$0.02 per GB of storage
 
⸻
 
Time
Pay for duration.
Example:
$0.10 per hour of computing
 
⸻
 
Capacity
Pay for allocated resources.
Example:
8 CPU cores 100 GB storage
 
⸻
 
Execution
Pay each time something runs.
Example:
Serverless function execution
 
⸻
 
Fixed Price Model
You pay a set amount regardless of usage.
Example:
A server costs $500/month.
Even if:
* You use 10%
* You use 90%
You still pay $500.
 
⸻
 
Comparison:
	Consumption	Fixed Price
Payment	Based on usage	Set amount
Flexibility	High	Lower
Predictability	Lower	Higher
Risk	Unexpected bills	Paying for unused resources
 
⸻
 
8. Serverless Architecture
Definition:
Serverless allows developers to write and run code without managing servers.
The cloud provider manages:
* Servers
* Operating systems
* Scaling
* Availability
Important:
Servers still exist.
They are just hidden from the developer.
 
⸻
 
Serverless benefits:
No server management
Developers focus on code.
 
⸻
 
Automatic scaling
Resources automatically increase or decrease.
 
⸻
 
Consumption pricing
Pay only when code runs.
 
⸻
 
Serverless Services
1. Function as a Service (FaaS)
Runs small pieces of code when triggered.
Example:
User uploads image:
Upload image
      ↓
Function runs
      ↓
Resize image
      ↓
Save image
Used for:
* Processing files
* APIs
* Automation
* Background tasks
 
⸻
 
2. Logic Apps
A service used to automate workflows.
Usually uses:
* Triggers
* Actions
* Connectors
Example:
New email received
        ↓
Save attachment
        ↓
Send notification
        ↓
Update database
Used for:
* Business processes
* Approvals
* Scheduled tasks
* Connecting applications
 
⸻
 
3. Event Grid
A service that detects events and sends notifications.
Event = something happened.
Examples:
* File uploaded
* Payment completed
* Database updated
Example:
File uploaded
       ↓
Event Grid detects event
       ↓
Trigger Function
       ↓
Process file
 
⸻
 
Final Exam Summary
Cloud computing = delivering computing services over the internet
Public cloud = provider owns everything
Private cloud = one organization controls environment
Hybrid cloud = public + private together
Shared responsibility = provider protects cloud infrastructure, customer protects data and access
CapEx = buy infrastructure upfront
OpEx = pay for services
Consumption model = pay for what you use
Fixed price = pay regardless of usage
Serverless = write code, cloud manages servers
FaaS = run code when needed
Logic Apps = automate workflows
Event Grid = react to events