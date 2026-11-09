# Generative AI Vocabulary (15 key terms)

This glossary was derived from the topics and risks discussed in `research-report.md` (Financial Services, Software Development, Healthcare, Education, and Marketing).

## 1) Large Language Model (LLM)
- **Definition:** A type of AI model trained on large amounts of text so it can generate and understand language (e.g., answer questions, summarize, draft content).
- **Practical example:** An LLM drafts a client email or summarizes a long report into a short explanation.
- **Connection to the report:** Used across all five domains; for example, marketing tools use LLMs to draft campaign copy.

## 2) Prompt Engineering
- **Definition:** Writing instructions (prompts) in a way that makes model outputs more accurate, relevant, and safe.
- **Practical example:** Adding constraints like “use bullet points and include a disclaimer” when drafting regulated communication.
- **Connection to the report:** Financial Services and Healthcare rely on carefully designed prompts and guardrails to reduce risky outputs.

## 3) Token
- **Definition:** A small unit of text (often a word or part of a word) that an LLM reads and generates.
- **Practical example:** A long document may exceed token limits, so the system summarizes or splits the document into parts.
- **Connection to the report:** In Education tutoring chats and Software Development assistants, token limits affect how much context can be included.

## 4) Context Window
- **Definition:** The maximum number of tokens an LLM can consider at once (prompt + retrieved documents + chat history).
- **Practical example:** A coding assistant can’t load an entire repository at once, so it only includes the most relevant files.
- **Connection to the report:** Software Development tools must manage context carefully for large codebases.

## 5) Retrieval-Augmented Generation (RAG)
- **Definition:** A pattern where the system retrieves relevant documents from a knowledge source and then asks the model to generate an answer using those documents.
- **Practical example:** An internal assistant searches policy documents and then produces a summary answer grounded in those sources.
- **Connection to the report:** Mentioned in Financial Services for advisor assistants and in Marketing for in-context content generation.

## 6) Embeddings
- **Definition:** Numeric vectors that represent the meaning of text so the system can search by similarity (semantic search).
- **Practical example:** Converting documents into embeddings so the system can retrieve the most relevant paragraphs for a user question.
- **Connection to the report:** Supports RAG-style retrieval for enterprise knowledge bases (e.g., finance policies or engineering docs).

## 7) Vector Database
- **Definition:** A database built to store embeddings and quickly find the most similar vectors.
- **Practical example:** Storing embeddings for thousands of internal documents so a chatbot can retrieve relevant passages.
- **Connection to the report:** Helps scale retrieval for RAG in domains with large document collections (finance, software, marketing).

## 8) Hallucination
- **Definition:** When an LLM generates information that sounds correct but is actually false or unsupported.
- **Practical example:** The model invents a product feature or cites a policy rule that does not exist.
- **Connection to the report:** A major risk in Healthcare (patient safety) and Financial Services (regulated communications).

## 9) Fine-Tuning
- **Definition:** Training a pre-trained model further on a smaller, specific dataset to improve performance for a domain or style.
- **Practical example:** Fine-tuning on a company’s approved support messages to better match brand tone.
- **Connection to the report:** Relevant in Marketing (brand voice) and in domain-specific assistants where specialization is needed.

## 10) Grounding
- **Definition:** Making model outputs depend on trusted sources (documents, databases, policies) rather than “guessing” from general training data.
- **Practical example:** Requiring the model to answer only from retrieved internal documents and to say “I don’t know” when sources are missing.
- **Connection to the report:** Central to Financial Services and Healthcare to reduce hallucinations and increase auditability.

## 11) Human-in-the-Loop (HITL)
- **Definition:** A workflow where a human reviews, edits, or approves AI outputs before they are used.
- **Practical example:** A clinician reviews and signs an AI-drafted clinical note; a developer reviews an AI-generated pull request.
- **Connection to the report:** Highlighted in Healthcare documentation tools and in Software Development review processes.

## 12) Model Evaluation (Evals)
- **Definition:** Systematic testing of a model’s performance and safety on specific tasks, including tracking errors over time.
- **Practical example:** Measuring how often an assistant gives incorrect policy interpretations or fails to include required disclaimers.
- **Connection to the report:** Important in Financial Services and Healthcare, where incorrect outputs can have high consequences.

## 13) AI Agents
- **Definition:** Systems where an LLM can plan steps and use tools to complete tasks, not just generate text.
- **Practical example:** An agent creates a file, checks that it exists, and reports the result.
- **Connection to the report:** Related to Software Development “agent-like workflows.” In my practical work, I used **CodeMie** as an agent to create repository files and then verify them via the GitHub API.

## 14) Tool Use / Function Calling
- **Definition:** A method that lets a model call external tools or APIs (instead of guessing), such as searching documents or creating files.
- **Practical example:** Calling the GitHub Contents API to create `connection-test.md` and then calling GET to verify it.
- **Connection to the report:** Tool integration is essential for reliable enterprise systems. In my practice, **CodeMie** used tool calls to PUT and GET files in GitHub to confirm successful automation.

## 15) Data Governance
- **Definition:** Policies and controls for how data is accessed, used, stored, and shared (especially sensitive or regulated data).
- **Practical example:** Preventing confidential client information from being pasted into an unapproved external chat tool.
- **Connection to the report:** A key requirement in Financial Services and Healthcare because sensitive data and compliance obligations are central concerns.

---

## Practical Reflection
Working with an AI agent and the GitHub API taught me that “AI agents” become most useful when they can **take actions** (e.g., create files) and then **verify outcomes** (e.g., read the file back). Tool use made the process more reliable than pure text generation because the system could confirm what actually changed in the repository.

At the same time, the workflow also highlighted the importance of **human review**. Even when API calls succeed, a person still needs to check that the content meets assignment requirements, uses correct sources, and avoids mistakes such as formatting errors or overly confident claims. This matches the broader theme in my research report: in higher-risk domains, GenAI works best as an assistant with clear controls and human oversight.
