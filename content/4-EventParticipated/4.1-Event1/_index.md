---
title: "Event 1"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

## Reflection on "Automated Prompt Engineering: Enhancing LLM Output Quality"

### Event Purpose

* Share practical knowledge about communicating effectively with artificial intelligence (AI).
* Analyze the importance of Prompt Engineering in optimizing cost and performance.
* Explain the core components required to create a high-quality prompt.
* Introduce advanced prompting techniques and tools that automate the optimization process.

### Speaker

* **Nguyen Tuan Thinh** - DevOps/Cloud Engineer at First Cloud AI Journey.

### Key Highlights

#### The Importance of Prompt Engineering

Using prompts that are too general can lead to several issues:

* **Token waste:** Unnecessarily increases the cost of using AI.
* **Inconsistent results:** Vague instructions cause AI to return low-quality responses.
* **Reduced productivity:** Requires repeated adjustments instead of producing useful results from the beginning.

#### Key Components of a Great Prompt

For AI to work accurately, a prompt should include seven elements:

1. **Role:** Define the model's role, for example: "You are a career advisor."
2. **Instruction:** Clearly state what needs to be done.
3. **Context:** Provide relevant background information.
4. **Input Data:** Include the specific data that needs to be processed.
5. **Output Format:** Define the expected output structure, such as JSON or Markdown.
6. **Examples:** Provide sample examples through few-shot prompting.
7. **Constraints:** Specify limits related to length, language, or things the model should avoid.

#### Token Economics

* Understand how AI pricing is calculated based on tokens, which are units smaller than words.
* Distinguish between input token and output token costs to optimize the budget.

#### Advanced Prompting Techniques

* **Chain-of-Thought (CoT):** Guides AI to reason step by step to improve logical thinking.
* **Self-Consistency:** Runs multiple reasoning paths and selects the most common result.
* **Tree-of-Thoughts (ToT):** Allows AI to explore multiple directions for solving a problem.
* **RAG (Retrieval-Augmented Generation):** Combines external data with model generation so AI can answer more accurately.

#### Proptimizer Tool

* Introduced a browser extension that helps optimize prompts on web platforms.
* The system architecture is based on AWS services such as **Amazon Bedrock**, **AWS Lambda**, and **Amazon DynamoDB**.

### What I Learned

#### Technical Thinking

* **Be Clear and Specific:** Always prioritize specificity and direct instructional language.
* **Describe DOs, not DON'Ts:** Focus on describing what AI should do instead of only listing restrictions.
* **Separate data clearly:** Use delimiters to separate different parts of the prompt.

#### Optimization Strategy

* Break complex requests into smaller sections so AI can process them more effectively.
* Accept an "I don't know" answer from AI when appropriate to avoid hallucination.

### Application to My Work

* Optimize prompts used for writing test cases and analyzing requirements as a BA.
* Use CoT techniques to ask AI to solve complex programming logic in Java and Flutter.
* Try the Proptimizer tool to speed up document-related work in the browser.

### Event Experience

* I gained deeper knowledge about how large language models (LLMs) operate.
* I better understood the AWS infrastructure behind modern AI applications through the Solution Architecture diagram.
* The workshop provided many practical examples, from writing social media posts to improving self-introduction content for new graduates.

#### Some Photos from the Event

* Photos from the event are shown below.

  ![alt text](image.png)
  ![alt text](image-1.png)

> Overall, the event not only provided technical knowledge but also helped me change the way I think about application design, system modernization, and more effective collaboration between teams.
