# Lecture 01 Answers

## Exercises

- Model's answer to the course-specific question (the 3 homework levels; a summary is fine):
"The Week 1 homework has three levels, and you only need to complete one:

Basic: Compare answers across different models or temperature settings.
Implementation: Add follow-up questions while keeping conversation history in ask.py.
Advanced: Measure response time and token counts, then compare models or questions and discuss free-tier rate limits."

- What you noticed when comparing it with the correct meaning in the glossary:
The AI’s answer was generally similar, but the glossary was more precise. I noticed that AI may give a confident but incomplete or incorrect explanation of course-specific terms.

- Token counts you displayed (input / output):
Question: display input and output token counts for TODO
Changes made: 
"[tokens] input={usage.prompt_token_count} "
            f"output={usage.candidates_token_count}"

## Homework

- Level attempted: Basic
- What you did: changed the LLM model and checked for each of the outputs
- Results: gemini-3.5-flash-lite model was so much faster producing the answer compared to the gemini-3.5-flash in both Japanese and English. Both gave me an output including the definition and merits of using them. Although gemini-3.5-flash-lite was more helpful with its answer in the way that it gave examples and analogies for us to understand the answer to our question more intuitively. 
- Observations and questions: I tried asking LLM in both Japanese and in English to see how languages affect how they answer the prompt I put in.　I also asked helping chat bot on the right to explain me the differences of different LLM modesl and how they are useful in what areas and aspects. This allowed me to optimize which LLM to use for which purposes. 