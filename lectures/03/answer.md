# Lecture 03 Answers

## Exercises

- Differences between the Lecture 01 (bare LLM) and agent answers: app.ask replies the definition probably given by in the slides to students. It also suggests where we can access further information. app.agent replies saying "it does not exist in the dictionary" and does not hunt for an answer for us but only refers to the dictionary. 
- Tool calls shown by `--trace` (tool names and arguments):  search_glossary({'query': 'LoRA'}), search_glossary({'query': 'QLoRA'})
- Number of LLM calls for one question (`requests`): 2
- Tool added and the description in its docstring: N/A

## Homework

- Level attempted: Basic 
- What you did: make changes to INSTRUCTIONS and tool docstrings, and use --trace to observe changes
- Results: before changing, it used search_glossary({'query':'-----'}) and after claiming that it did could not find the answer, it changed the origin of the source to general knowledge. LLM call count with two. At the end of the answer, the system wrote *(Reference: General AI Engineering Knowledge)* which means if the search did not hit any definition from the materials, it changed the source to general AI engineering knowledge. This only had LLM call of once.
- Observations and questions: making changes in the instruction altered the tool call as well. The system never mixes where the origin of their source is so it is more or less easy to tell if the information comes from the matrial for sure or from the general knowledge.
