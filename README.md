# Generative AI Applications Research

This repository contains my completed EPAM course assignment **“Research on Generative AI Applications”**. The work includes (1) a source-backed research report across five industries, (2) a concise GenAI vocabulary derived from the report, and (3) an optional interactive relationship graph that connects key GenAI concepts to the use cases and documents how often they are mentioned.

## Contents
- **Research report:** [`research-report.md`](./research-report.md)
- **GenAI vocabulary (15 terms):** [`genai-vocabulary.md`](./genai-vocabulary.md)
- **Relationship data (JSON):** [`genai-relationships.json`](./genai-relationships.json)
- **Interactive relationship graph (HTML):** [`genai-relationships.html`](./genai-relationships.html)

## Summary: five Generative AI use cases
1. **Financial Services** — Internal, secure GenAI assistants for knowledge retrieval and drafting under compliance constraints (e.g., RAG-grounded answers and controlled communications).
2. **Software Development** — Coding copilots and agent-like workflows that help write/explain code, generate boilerplate/tests, and support review.
3. **Healthcare** — Documentation support (draft clinical notes/summaries) and careful decision-support exploration with strong privacy/safety requirements.
4. **Education** — Tutoring-style dialogue, guided practice, and teacher support, with attention to learning objectives and academic integrity.
5. **Marketing** — Scalable content generation and personalization, requiring brand safety, factuality controls, and evaluation (e.g., A/B testing).

## Interactive relationship graph (optional task)
The interactive graph (`genai-relationships.html`) visualizes:
- **15 vocabulary terms** (nodes)
- **5 use cases** (nodes)
- **Relationships** between concepts (term–term edges) and where they appear in the report (term–use case edges)

### Explicit vs. implicit counting methodology
The underlying counts are stored in `genai-relationships.json`.
- **Explicit mentions**: case-insensitive regex matches of the exact term/abbreviation in `research-report.md` (word boundaries used where appropriate).
- **Implicit mentions**: **evidence-based** sentence-level matches where the sentence clearly describes the concept *without* using the exact term. Generic words such as *“workflow”, “context”, “assistant”, “review”, or “API”* are **not** counted automatically.
  - Sentences that already contain an explicit mention for the same term are excluded.
  - Duplicate sentences for the same term are counted once.
  - Each implicit mention includes a **full-sentence excerpt** and the corresponding report **section** in the JSON.

The graph defaults to **Explicit** node sizing, with buttons to switch to **Implicit** and **Total**.

## AI-Assisted Development with EPAM CodeMie
I used **EPAM CodeMie** as an AI assistant/agent to automate parts of the workflow using the GitHub REST API:
- creating new assignment files,
- committing them to the `main` branch,
- verifying changes by reading the files back via API (GET) after creation.

This helped ensure repository changes were reproducible and verifiable rather than only described in text.

### Technical challenges encountered and resolutions
- **403 “Resource not accessible by personal access token”**: initial write attempts failed due to insufficient GitHub token permissions. This was resolved by updating the token/access so that the integration could write to repository contents.
- **422 “content is not valid Base64”**: occurred when using the GitHub Contents API with an invalid Base64 payload or when payload handling caused truncation/corruption. This was resolved by ensuring proper Base64 encoding and (for some files) using the Git Data API (blob/tree/commit) as a more reliable alternative.

---

**Course/assignment context:** EPAM Generative AI course (university-style research and applied tooling).
