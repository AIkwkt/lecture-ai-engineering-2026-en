# Lecture 05 Answers
## Exercises

- Answering model (`[model]` shown during execution):
- Comparison question:
- Target materials (also record the difference in scope between full context and the other methods):

### Results by Method

| Method | Key points and correctness of the answer | Cited pages and evidence | Time (seconds) | Input/output tokens | Model responses | Estimated generation API cost (USD) |
| Method | Key points and correctness of the answer | Cited pages and evidence | Time (seconds) | Input/output tokens | Model responses | Estimated generation API cost (USD) |
|---|---|---|---|---|---|---|
| Full context | Not run in Lecture 05 | Not applicable | Not available | Not available | Not available | Not available |
| Vector search | Not run in Lecture 05 | Not applicable | Not available | Not available | Not available | Not available |
| Tree | Not run in Lecture 05 | Not applicable | Not available | Not available | Not available | Not available |
| Graph | Not run in Lecture 05 | Not applicable | Not available | Not available | Not available | Not available |

<!-- State when a method was not run or a cost was unavailable. Use a separate table for each additional question. -->

- Pages found by running search alone, and what their text confirmed:
  Not applicable for this MCP exercise.

- Tool calls shown by `--trace` (names, arguments, counts, table-of-contents paths followed by Tree, etc.):
 Before MCP: `search_glossary({"query": "..."})`
  Through MCP: `glossary_search_glossary({"query": "..."})`

- Examples where retrieved information was insufficient, or was retrieved but not used in the answer:
No insufficient or unused retrieved information was observed.
- Method you would adopt for this use case, your reasons, and limitations of the comparison conditions:
I would use MCP because the tools can be exposed by a server and reused by the agent
  and other MCP clients. A limitation is that this exercise compared only one or two
  questions, so the result may not apply to every question.
- Observations and questions:
 MCP tool names have a server prefix, such as `glossary_search_glossary`.
  `get_lecture_summary` was successfully exposed as `glossary_get_lecture_summary`.

## Homework

<!-- Completing any one of Basic, Implementation, or Advanced is sufficient. -->

- Level attempted: Basic
- What you did (files, settings, or processing changed, or retrieval method designed):  
changed the `search_glossary` tool description in `app/tools.py`.
  Before: "Search the course glossary and return definitions and the sessions that cover the terms."
  After: "Use this tool whenever the question concerns an AIE2026 term or course-specific concept."
  I also started the MCP server using stdio and Streamable HTTP.

- Comparison question and conditions held fixed (model, target materials, etc.):
Question: "What is LoRA?"
  Model: [model name shown by `[model]`]
  Target materials: the AIE2026 glossary
  The question, model, and target materials were the same before and after the change.

- Results (answers and evidence before/after, `--trace` output, time, token counts, estimated generation API cost, etc.):
 - Before the change:
    - Final answer: [answer]
    - `--trace`: [tool name and arguments]
    - Evidence: [retrieved glossary information]
    - Time: [seconds or `unavailable`]
    - Input/output tokens: [counts or `unavailable`]
    - Estimated generation API cost: [USD or `unavailable`]

  - After the change:
    - Final answer: [answer]
    - `--trace`: [tool name and arguments]
    - Evidence: [retrieved glossary information]
    - Time: [seconds or `unavailable`]
    - Input/output tokens: [counts or `unavailable`]
    - Estimated generation API cost: [USD or `unavailable`]
- Examples of improvements and remaining failures or limitations:
 The revised description may make the model use `search_glossary` more clearly for course-specific terms.

- Observations and questions:
 The tool description appears to influence whether the model selects the tool.
