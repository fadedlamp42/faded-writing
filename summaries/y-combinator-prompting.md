# Y Combinator prompting

Prompting advice from [this video](https://www.youtube.com/watch?v=DL82mGde6wo&feature=youtu.be), processed with [this conversation](https://g.co/gemini/share/a2081454f227).

# Advanced Prompt Engineering Insights for LLM Engineers

This document provides a breakdown of key topics and actionable advice from a video on advanced prompt engineering techniques for engineers working with Large Language Models (LLMs).

---

## Prompt Engineering: A New Frontier

The video frames **prompt engineering** not just as writing queries, but as a new form of programming or even management. This paradigm shift requires engineers to think of LLMs less as deterministic machines and more as collaborators that need clear instructions and context to perform tasks effectively.

### Actionable Information for Engineers:

* **Treat Prompts Like Code:** Version control your prompts, write clear documentation, and establish a testing framework to evaluate their performance.
* **Embrace the "Manager" Mindset:** When an LLM fails, don't just tweak the prompt. Analyze the failure, provide constructive feedback (in the form of better instructions), and iterate.

---

## Advanced Prompting Techniques

The video highlights several advanced techniques to get the most out of your LLMs:

* **XML-like Formats:** Using structured formats like XML in your prompts can significantly improve an LLM's ability to understand and respond to your requests.

    * **Actionable Information for Engineers:** For complex tasks, structure your prompts with clear hierarchies and tags to guide the LLM's output.

* **Meta-Prompting:** This is the concept of using one prompt to generate and refine other prompts. This is a powerful way to automate prompt optimization.

* **Prompt Folding:** This technique uses a classifier prompt to generate a specialized prompt based on the user's query. This allows for dynamic prompt generation and a more personalized user experience.

    * **Actionable Information for Engineers:** Instead of manually rewriting failed prompts, use meta-prompting and prompt folding to have the LLM improve them for you. This can save time and lead to better results.

---

## System, Developer, and User Prompts

The video introduces a useful framework for categorizing prompts based on their purpose:

* **System Prompts:** These define the high-level behavior and constraints of your AI system. Think of them as the "constitution" for your LLM.
* **Developer Prompts:** These provide specific context for individual customers or use cases.
* **User Prompts:** These are for direct interaction with the end-user.

### Actionable Information for Engineers:

* By separating your prompts into these categories, you can build more robust and scalable AI systems. This modular approach makes it easier to manage and update your prompts over time.

---

## The Importance of "Escape Hatches"

The video stresses the need to give LLMs a way to say "I don't know" to prevent hallucinations. An **"escape hatch"** allows the LLM to request more information when a query is unclear or underspecified.

### Actionable Information for Engineers:

* In your prompt's response format, include a **"debug info"** parameter. This allows the LLM to communicate when it's confused, creating a feedback loop for developers to improve the system.

---

## "Evals" are the Crown Jewels

The video argues that the **evaluations (evals)** of your prompts are more valuable than the prompts themselves. Evals provide the data and reasoning behind why a particular prompt was chosen, which is essential for continuous improvement.

### Actionable Information for Engineers:

* Don't just focus on writing good prompts. Build a robust evaluation framework to track their performance over time. This data will be invaluable as you scale your AI systems.

---

## The "Forward-Deployed Engineer"

The video highlights the concept of the **"forward-deployed engineer"**—a founder or engineer who works directly with users to understand their needs and build solutions in real-time. This hands-on, empathetic approach can be a significant advantage for startups.

### Actionable Information for Engineers:

* Get out of the building and talk to your users. Understanding their workflows and pain points will help you build better products and write more effective prompts.

---

## LLM Personalities and Rubric Application

The video makes two interesting observations about the differences between LLMs:

* **LLM "Personalities"**: Different LLMs have distinct characteristics. For example, one might be more "human steerable," while another is more "developer-like" and requires more direct instruction.

* **Rubric Application**: When given a rubric, some models are very rigid, while others are more flexible and can reason through exceptions.

### Actionable Information for Engineers:

* Don't assume all LLMs are the same. Experiment with different models to find the one that's best suited for your specific use case. Consider the model's "personality" and how it aligns with your desired output.
