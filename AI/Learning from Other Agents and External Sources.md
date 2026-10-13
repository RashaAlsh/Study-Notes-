Learning from Other Agents and External Sources

1. Overview

AI agents can expand their capabilities by using information beyond their original training.

Two important approaches are:

1. Learning from other AI agents — sharing knowledge, solutions, or experience between agents.
2. Retrieving information from external sources — accessing websites, databases, APIs, and other systems to obtain relevant information.

Agents can also use human feedback to improve their performance.

Key idea: An agent can go beyond its built-in knowledge by collaborating with other agents and gathering information from external sources.

Important distinction: Retrieving information gives an agent information to use. Learning means using experience or information to improve knowledge, behavior, or future performance. Retrieval does not automatically change the model itself.

⸻

2. Learning from Other AI Agents

In a multi-agent system, multiple AI agents work together or exchange information to accomplish tasks.

An agent may discover a solution to a problem and share it with other agents, allowing them to reuse that knowledge instead of solving the same problem independently.

Example: Customer Support Agents

Imagine a company has AI support agents serving customers in different countries.

Agent A discovers how to solve a new software error.

Agent A encounters a new problem
              ↓
Finds a successful solution
              ↓
Shares the solution
              ↓
       ┌──────┼──────┐
       ↓      ↓      ↓
    Agent B Agent C Agent D
       ↓      ↓      ↓
  Reuse the shared solution

When another agent encounters the same error, it can use the shared solution to help the customer.

Benefits

* Faster problem-solving: Agents can reuse solutions discovered elsewhere.
* Less duplicated effort: Every agent does not need to solve the same problem independently.
* More consistent responses: Shared, validated knowledge can improve consistency.
* Potential cost savings: Reusing solutions may reduce repeated work and support costs.
* Improved collaboration: Agents can divide tasks and combine their findings.

Important limitations

Knowledge sharing does not guarantee that every agent learns automatically or permanently.

Agents need a mechanism to exchange information, such as a shared database, message system, or common knowledge base. Shared information should also be checked for accuracy, relevance, and permissions.

⸻

3. Learning from External Information Sources

AI agents can retrieve information from systems outside their original model training.

Common sources include:

Source	Example use
Websites	Researching current information
Search engines	Finding relevant articles and documents
Databases	Retrieving structured records and historical data
APIs	Accessing weather, travel, or business data
Company systems	Looking up internal policies and documentation
Knowledge bases	Finding verified answers to common questions

This is especially useful when the agent needs information that is current, specialized, private to an organization, or not available in its existing context.

Example: Planning a Surfing Vacation in Greece

A user asks:

“Which week next year is likely to have the best surfing conditions in Greece?”

The agent needs more than general knowledge about surfing. It needs relevant environmental data and a way to evaluate suitable conditions.

Step 1: Identify the information needed

The agent identifies relevant factors, such as:

* Wave height and swell direction.
* Wind speed and direction.
* Local geography and surf breaks.
* Seasonal weather patterns.
* The user’s surfing preferences.

Step 2: Retrieve external data

The agent queries appropriate sources, such as:

* Historical weather and wave datasets.
* Marine forecasts and buoy observations.
* Surf reports and local spot guides.

For a trip next year, historical patterns can help identify promising seasons, but they cannot reliably determine the exact conditions of a specific future week this far in advance.

Step 3: Understand the requirements

The agent uses relevant surfing knowledge to evaluate the data.

For example, suitable wave conditions depend on the surf location, swell, wind, and the surfer’s ability. Sunny weather may be desirable for a vacation, but it does not necessarily mean better surfing.

Step 4: Combine the findings

The agent combines the retrieved information with its reasoning and the user’s preferences.

Historical Weather and Wave Data
                 +
       Surfing Requirements
                 +
        User Preferences
                 ↓
       Compare Candidate Weeks
                 ↓
       Identify Promising Periods

Step 5: Present a recommendation

The agent recommends a promising period, explains the evidence and uncertainty, and suggests checking updated forecasts closer to the trip.

Result: The answer is based on retrieved evidence rather than only on information already present in the model.

⸻

4. How External Information Expands an Agent’s Capabilities

AI models have limitations. Their built-in knowledge may be incomplete, may not include recent developments, or may lack access to a user’s private or specialized data.

External tools can help bridge these gaps.

User Asks a Question
         ↓
Identify Missing Information
         ↓
Search or Query External Sources
         ↓
Retrieve Relevant Data
         ↓
Check and Interpret the Results
         ↓
Reason About the Evidence
         ↓
Provide an Informed Answer

This process is often called tool use, information retrieval, or retrieval-augmented generation (RAG), depending on how the system is implemented.

These terms are related but not identical:

* Tool use: The agent invokes a tool, such as a search engine or API.
* Information retrieval: The system finds and retrieves relevant information.
* RAG: Retrieved information is supplied as context to a generative model to help it produce a grounded response.
* Learning: The system improves its knowledge or behavior through an update process.

An agent can retrieve new information without permanently learning it or modifying its model parameters.

⸻

5. Traditional AI Tool vs. AI Agent Using External Tools

The key difference is not simply whether a system is an AI tool or an AI agent. Both can access external information.

The distinction is often in how the system uses tools and manages a task.

Basic AI interaction

User Asks a Question
         ↓
AI Generates an Answer
Using Available Context

Agentic workflow

User Defines a Goal
         ↓
Agent Identifies What It Needs
         ↓
Chooses a Suitable Tool
         ↓
Retrieves External Information
         ↓
Evaluates the Results
         ↓
Repeats or Changes Approach if Needed
         ↓
Provides a Final Answer

An agentic system may decide which tools to use, perform several steps, evaluate intermediate results, and adjust its approach.

However, a traditional AI assistant can also use tools. Tool access alone does not automatically make a system an agent. The level of autonomy and task management also matters.

⸻

6. Comparing the Three Sources of Improvement

Source	How it helps	Example
Other AI agents	Shares solutions or findings	Support agents exchange troubleshooting instructions
External sources	Provides additional or current information	An agent queries a weather API
Human feedback	Helps evaluate and correct behavior	A support employee flags an incorrect response

These approaches can work together.

For example, a support agent could retrieve a current troubleshooting guide, solve a problem, receive human feedback, and share the verified solution with other agents.

⸻

7. Benefits and Risks

Benefits

* Access to information beyond the original training data.
* Better handling of current or specialized questions.
* Less duplicated work across agents.
* More informed decisions when reliable evidence is available.
* Greater flexibility when tasks require multiple information sources.

Risks and limitations

* Incorrect information: External sources may contain errors or outdated data.
* Conflicting results: Different sources may disagree.
* Security risks: Retrieved content may contain malicious instructions or untrusted data.
* Privacy and permissions: Agents must access only information they are authorized to use.
* Cost and latency: Multiple tool calls can increase processing time and expense.
* Uncertainty: Retrieved evidence may not be sufficient to support a confident conclusion.

Agents should evaluate source reliability, respect access controls, and communicate uncertainty rather than treating every retrieved result as true.

⸻

8. Common Exam Questions

Q1. How can AI agents expand their knowledge beyond their original training?

They can exchange information with other agents, retrieve information from external sources, and use feedback to improve their performance.

Q2. What is a multi-agent system?

A system in which multiple agents interact, cooperate, or coordinate to accomplish tasks.

Q3. Name four external information sources an AI agent can use.

Websites, databases, APIs, and company knowledge bases.

Q4. What is the difference between information retrieval and learning?

Information retrieval obtains information for use. Learning improves knowledge or behavior through an update or learning process.

Q5. Does retrieving information automatically update an AI model?

No. The information may only be used as context for the current task. Permanent learning or model updates require a separate mechanism.

Q6. Why might an agent use multiple external sources?

To gather complementary evidence, compare results, and make a more informed recommendation.

Q7. Does using external tools automatically make a system an AI agent?

No. Tool use is one capability. Agentic behavior also involves pursuing tasks or goals through decision-making and potentially multi-step actions.

Q8. What is one important risk when agents share knowledge?

Incorrect or unsafe information may spread between agents unless the information is validated and appropriately controlled.

⸻

9. Quick Cheat Sheet

Concept	Remember
Agent-to-agent sharing	Agents exchange knowledge or solutions
External information	Data retrieved from websites, APIs, databases, or other systems
Tool use	An agent invokes an external capability
RAG	Retrieved information provides context for generated answers
Learning	Experience or information improves future behavior or knowledge
Human feedback	People evaluate or correct the system
Main benefit	More flexible, evidence-informed problem-solving
Main risk	Information may be inaccurate, unsafe, or unauthorized

One-Sentence Summary

AI agents can extend their capabilities by sharing knowledge with other agents and retrieving information from external sources, enabling more informed decisions beyond their built-in knowledge.

Golden Rule

Sharing provides knowledge, retrieval provides information, and learning improves future behavior.