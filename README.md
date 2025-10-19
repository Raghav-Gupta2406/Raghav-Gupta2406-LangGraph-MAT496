# Raghav-Gupta2406-LangGraph-MAT496
## LangGraph Course Assignment for MAT496

This repository documents my progress through Modules 1 of the LangGraph course, fulfilling the requirements for video-by-video commits, learning summaries, and unique code examples.

## MODULE 1

### LESSON 1: Motivation
 - **Learned:** I've learned the fundamental motivation for using LangGraph to build more powerful and reliable AI agents, need to move beyond single LLM calls. This lesson showed the basics of how LangGraph gives the control to create complex, multi-step workflows, setting the stage for what we will learn in the next few lessons.
 - **Source Code:** No code was provided to edit.

 ### LESSON 2: Simple Graph
 - **Learned:** I learned I can control which path the graph takes just by changing the logic in a decision step. I also learned the final message is built piece by piece with each node adding its own specific words to the story.
 - **Tweak:** I tweaked the random probability to control the path and changed the node text to a new weather theme.
 - **Source Code:** [M1L2_simple-graph.ipynb](M1L2_simple-graph.ipynb)

 ### LESSON 3: LangGraph Studio
 - **Learned:** After I ran my studio project, it automatically opened in my browser through LangSmith and displayed the output graph for video 2, lesson 2. For testing purposes, I entered the input text “Hi, this is Raghav” to check the response. The system processed it correctly. Since the task didn’t require any specific modifications, I didn’t make any changes to the code as no code was provided.

 ### LESSON 4: Chain
 - **Learned:** My core lesson was learning how to build a LangGraph chain and get it to properly use custom tools. I now understand how to bind tools to the language model and make the graph execute tool calls as part of its workflow.
 - **Tweak:** I replaced the default tool-calling cell with a custom web search tool that I built myself. To do this, I tweaked the code so my new tool would use the Serper and Tavily APIs for performing live searches.
 - **Source Code:** [M1L4_chains.ipynb](M1L4_chains.ipynb)

 ### LESSON 5: Router
 - **Learned:** I learned how to build a router in LangGraph using conditional edges. This allows agent to intelligently decide its next action by inspecting the output of a tool. Instead of following a fixed path ,now create dynamic workflows that loop or branch.
 - **Tweak:** Not much of tweaking was required just changed the input text multiplication and used langgraph studio.
 - **Source Code:** [M1L5_router.ipynb](M1L5_router.ipynb)

 ### LESSON 6: Agents
 - **Learned:** I learned how to build a complete agent that can solve problems requiring multiple steps. I did this by creating a loop where the AI can use the result from one tool to decide on the next action. I was then able to trace the agent's entire step by step process in LangSmith until it reached the final answer.
 - **Tweak:** I changed the AI's step by step plan which created a new flowchart showing its workflow. Also changed the question to test how my new version would solve a different problem.
 - **Source Code:** [M1L6_agents.ipynb](M1L6_agents.ipynb)

 ### LESSON 7: Agent Memory
 - **Learned:** The key lesson is that LangGraph agents are stateless by default, but adding a checkpointer during compilation and using a thread_id at runtime gives them memory to handle multi-turn conversations.
 - **Tweak:** The tweaks involved changing the input text to test this memory and using LangGraph Studio to visualize the agent's execution flow.
 - **Source Code:** [M1L7_agent-memory.ipynb](M1L7_agent-memory.ipynb)

 ## MODULE 2
 ### LESSON 1: State Schema
 - **Learned:** I learnt about typed state schemas, typeddict, dataclass, pydantic, which lets every node share a consistent contact so langGraph graphs stay predictable.
 - **Tweak:** Changed the mood to status channel with new "frustrated" or "chill" values.
 - **Source Code:** [M2L1_state-schema.ipynb](M2L1_state-schema.ipynb)

  ### LESSON 2: State Reducers
 - **Learned:** I found out that reducers allow parallel nodes to combine updates safely, keeping the state predictable. I also learned that annotated keys can switch between overwrite, append, or custom merge modes without needing to rewrite the nodes.
 - **Tweak:** I changed the content in removal for AI message.
 - **Source Code:** [M2L2_state-reducers.ipynb](M2L2_state-reducers.ipynb)
