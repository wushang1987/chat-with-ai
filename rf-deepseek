To understand all user stories in an outdated IT system, you can use a structured methodology that leverages Large Language Models (LLMs) to analyze legacy artifacts like code, documents, and logs. The core idea is to treat the system's existing outputs and structures as a source from which to reverse-engineer user needs and system behaviors.

Below is a practical, three-phase methodology you can follow. An overview of the different ways to apply LLMs to this task is provided first, followed by detailed implementation steps.

### 📊 Choosing Your LLM Approach
You can apply LLMs to your legacy system artifacts in several ways. The table below compares the main techniques to help you decide which might be best for your situation.

| Method | Best For / Key Feature | Key Insight from Search Results |
| :--- | :--- | :--- |
| **Direct Prompting** | Quick, initial exploration. Feeding raw code/document snippets to an LLM with simple instructions. | A basic method, but can lead to unreliable or hallucinated outputs if the context is too complex. |
| **Multi-Step & Refined Prompting** | **Improving accuracy on complex, long, or unclear documents.** Involves breaking the task into steps (e.g., summarize, then extract). | The “Refine and Thought” (RaT) prompting strategy was developed specifically to mitigate LLM hallucination when processing complex requirement documents. |
| **Structured Extraction** | Getting output in a consistent, machine-readable format (like JSON) for further analysis. | LLMs can be guided to output structured data using function calling, JSON mode, or detailed prompt instructions. |
| **RAG (Retrieval-Augmented Generation)** | Systems with vast, scattered documentation. Dynamically finds relevant info before answering. | While powerful, a simpler "Find, Retrieve, Answer" workflow can be effective for structured documents without a full vector database setup. |

### 🔬 How to Implement: A Three-Phase Plan

Here is a step-by-step plan to apply these techniques to your outdated system.

**Phase 1: Assemble and Prepare Your System Artifacts**
Your first task is to gather all available materials. Treat this as an archaeological dig to find every clue about how the system works.
*   **What to Collect**: Source code files, database schemas, old requirement documents, design wikis, user manuals, log files, and even recorded support tickets.
*   **How to Prepare**: For code in obscure languages, try to find and include any available syntax documentation or glossaries. For documents, convert them to plain text (`.txt`) or a standard format. **Crucially, create an inventory** listing each artifact, its type, and its suspected relevance.

**Phase 2: Extract and Structure Requirements with LLMs**
Use LLMs to process the artifacts you've collected. Start small with a single, representative file to test your approach.
1.  **Parse Code Logic**: Prompt the LLM to act as an analyst for the specific legacy language. Ask it to explain the purpose of functions, modules, or scripts in business terms.
    *   **Example Prompt**: "You are analyzing a [Legacy Language Name] system. Review this code snippet: `[Paste code]`. List the key business actions it performs. For each action, suggest who the user might be (e.g., 'data clerk', 'report manager') and what goal they are trying to achieve."
2.  **Mine Documents for Requirements**: Use the **multi-step prompting** strategy from research. First, ask the LLM to summarize a long document. Then, feed the summary back and ask it to extract specific functional requirements or user goals.
3.  **Generate Structured User Stories**: Combine insights from code and documents. Prompt the LLM to format findings into a consistent template.
    *   **Example Prompt for Structure**: "Based on the following analysis `[Paste analysis from previous steps]`, generate user stories in this JSON format: `{"role": "user type", "goal": "what they want", "reason": "why they want it"}`."

**Phase 3: Validate, Synthesize, and Refine**
The initial output from the LLM is a starting point, not a final product.
*   **Validate with Code & Logs**: Cross-check the generated user stories. Do the code paths and database interactions you identified logically support these stories? Do log files show activity patterns that match?
*   **Synthesize a Complete View**: Consolidate user stories from all artifacts. Use the LLM to help identify duplicates, group related stories into features (or "epics"), and spot conflicting requirements.
*   **Apply a Quality Framework**: Evaluate your generated stories against established criteria. Research has used the **Quality User Story (QUS) framework** to assess aspects like whether a story is *Atomic*, *Unambiguous*, and *Problem-oriented*.

### ✅ Verification and Next Steps
To ensure the generated user stories are accurate and useful:
*   **Seek Expert Review**: If possible, have a developer or user familiar with the old system review the stories. Their feedback is the best validation.
*   **Trace to System Outputs**: Confirm that the described user goals logically lead to the reports, data updates, or outputs the system is known to produce.
*   **Start Small and Iterate**: Begin with a pilot on one module of the system. Refine your prompts and process based on the results before scaling to the entire codebase.

For your next steps, you could begin by selecting one clear legacy code file or a short requirements document and applying the Phase 2 steps to it.

If you can share the name of the obscure language or the type of system (e.g., banking, inventory), I may be able to offer more specific guidance for your context.
