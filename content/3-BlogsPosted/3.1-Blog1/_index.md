---
title: "Blog 1"
date: 2026-10-05
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

<h2 align="center">BUILDING AN AI AGENT WITH LONG-TERM MEMORY AND SANDBOX CODE EXECUTION USING AMAZON BEDROCK AGENTCORE</h2>

When exploring AI Agents, I realized that a truly useful AI assistant requires more than just answering questions—it needs to remember information from past interactions and execute code to solve complex tasks.

For example, a data analysis AI Agent needs to remember how the user wants reports presented, while also having the capability to run Python to calculate metrics and generate charts instead of merely predicting results.

Amazon Bedrock AgentCore provides components to build such systems without having to provision and manage the entire infrastructure from scratch.

### 1. OVERVIEW OF AMAZON BEDROCK AGENTCORE

Amazon Bedrock AgentCore Memory: Supports storing and retrieving information across sessions, helping the Agent maintain context and remember useful details.

Amazon Bedrock AgentCore Code Interpreter: Provides an isolated code execution environment, allowing the Agent to run Python, JavaScript, or TypeScript to process data and perform calculations.

The key point is that Memory and Code Interpreter serve two distinct purposes. Memory preserves information needed for future use, while Code Interpreter executes code within a sandbox session.

### 2. SYSTEM ARCHITECTURE DESIGN

Let's design an AI Data Assistant capable of analyzing CSV files and remembering the user's workflow.

Components used:
* Amazon Bedrock: Provides the language model to understand requests and orchestrate tasks.
* AgentCore Memory: Stores and retrieves preferences and analysis rules.
* AgentCore Code Interpreter: Executes code to compute metrics and generate charts.
* Strands Agents SDK: Assists in building the Agent and integrating tools.

Workflow:
1. User submits a data analysis request.
2. Agent queries memory for relevant rules.
3. Model creates an appropriate plan and code.
4. Code Interpreter executes code inside the sandbox.
5. Agent uses actual results to compose the report.
6. Useful insights are saved to Memory for subsequent sessions.

### 3. IMPLEMENTING LONG-TERM MEMORY

Not all conversation history needs to be stored long term. The Agent should prioritize information that adds value to upcoming interactions.

For example:
* User prefers receiving reports in Markdown format.
* When analyzing data, missing values must be checked prior to calculation.
* Reports should include mean, median, and distribution charts.

Upon receiving a new request, the Agent retrieves related information and injects it into the execution context.

### 4. CODE EXECUTION WITH CODE INTERPRETER

LLMs can generate code but cannot guarantee it is always correct or secure. Executing AI-generated code directly on application servers poses risks to data, resources, and access privileges.

AgentCore Code Interpreter provides an isolated execution environment, separating code execution from the main application.

For example, when a user requests an analysis of scores.csv, the Agent can:
* Read and inspect data.
* Handle missing or invalid values.
* Calculate mean and median.
* Generate distribution charts.
* Return results to the Agent to synthesize into a report.

The sandbox can maintain session state during its lifecycle. However, temporary files or variables within the sandbox should not be considered permanent storage. If files need to be reused in future sessions, the application should persist them to appropriate storage such as Amazon S3.

### 5. REAL-WORLD SCENARIO ILLUSTRATION

Suppose in the first session, the user asks to analyze exam score data and generate a Markdown report.

Upon completion, the Agent saves the report formatting preference to AgentCore Memory.

In the next session, the user simply uploads a new file and asks: "Analyze this file like last time."

The Agent retrieves the saved memory, uses Code Interpreter to process the data, and produces the report following the stored rules without the user needing to repeat the full instructions.

This is the true value of combining long-term memory with tool execution: the Agent maintains operational context and performs tasks based on real computational results.

### 6. SECURITY AND COST

When deploying in production environments, several considerations should be kept in mind:
* Permissions: Users should only access memory and data within their authorized scope.
* Code security: Limit compute resources, file access permissions, and sandbox network connectivity.
* Memory management: Avoid storing unnecessary sensitive data; maintain appropriate update and deletion mechanisms.
* Monitoring: Track execution errors, response times, and resource utilization.

Costs should also be evaluated comprehensively, including Amazon Bedrock, AgentCore Memory, Code Interpreter, and associated storage or monitoring services. Actual costs depend on usage patterns and current AWS pricing.

### 7. CONCLUSION

Amazon Bedrock AgentCore Memory and Code Interpreter address two essential requirements when building AI Agents: retaining information across sessions and executing code in an isolated environment.

Combined with Amazon Bedrock and a framework like Strands Agents SDK, one can build applications such as an AI Data Analyst, Coding Assistant, or Research Assistant without having to build custom memory and runtime mechanisms from scratch.

### References

* Amazon Bedrock AgentCore: [https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/)
* AgentCore Memory: [https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/long-term-memory-long-term.html](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/long-term-memory-long-term.html)
* AgentCore Code Interpreter: [https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/code-interpreter-getting-started.html](https://docs.aws.amazon.com/bedrock-agentcore/latest/devguide/code-interpreter-getting-started.html)
* Strands Agents: [https://strandsagents.com/](https://strandsagents.com/)

#AWS #AmazonBedrock #BedrockAgentCore #AIAgent #GenerativeAI #AWSStudyGroup #CodeInterpreter #LongTermMemory

Post link: [https://www.facebook.com/share/p/1B8v39nAMn/](https://www.facebook.com/share/p/1B8v39nAMn/)

