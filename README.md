# Raghav-Gupta2406-LangGraph-MAT496
## LangGraph Course Assignment for MAT496

This repository documents my progress through Modules 1, 2 and 3 of the LangGraph course, fulfilling the requirements for video-by-video commits, learning summaries, and unique code examples.

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

  ### LESSON 3: Multiple Schemas
 - **Learned:** I learned that a private state lets nodes pass working data to each other without changing the final result.I also saw how to use separate schemas to filter the graph's input and output, while an internal schema holds all the working fields for logic.
 - **Tweak:** Changed the question and the final answer from the given code.
 - **Source Code:** [M2L3_multiple-schemas.ipynb](M2L3_multiple-schemas.ipynb)

  ### LESSON 4: Trim Filter Messages
 - **Learned:** I learnt about message reducers, filters, and trimmers control how much of the conversation log reaches the model each turn, also learnt about maintaining a consistent message channel lets us reshape the chat thread without breaking LangGraph structure.
 - **Tweak:**  I relaced working list names with conversation_log and chat_thread so the code is more readable and also updated every invocation of these in the code.
 - **Source Code:** [M2L4_TrimMessages.ipynb](M2L4_TrimMessages.ipynb)

  ### LESSON 5: Chatbot with Summarizing Messages and History
 - **Learned:** I learned that filtering and trimming the message history is a good way to create a summary. This summary makes it possible to stop the conversation and easily resume it later right where we left off.
 - **Tweak:** I made a few adjustments to the project. First I changed the summary in the state schema to hold a number (int) instead of text (str). 
 I noticed a bug after making these changes. Even when I cleared the old conversation and started the new math chat, the summary feature didn't properly reset. It still remembered the old summary and just added the new math inputs on top of it, which wasn't the intended result.
 - **Source Code:** [M2L5_chatbot-summarization.ipynb](M2L5_chatbot-summarization.ipynb)

 ### LESSON 6: Chatbot with Summarizing Messages and External Memory
 - **Learned:** I explored how connecting the chat to an external database is essential for memory. This setup saves the conversation summary and context, allowing us to close a session and return later without losing the entire history. This continuous memory is what makes effective, long-term summarization possible.
 - **Tweak:** I made two main adjustments to the project. First, I changed the message handling process from "filtering" to "trimming" to experiment and see how their efficiency differed. Second, I updated the logic for when a summary is created, switching it from the old method to a new one that triggers based on the total token count.
 - **Source Code:** [M2L6_chatbot-external-memory.ipynb](M2L6_chatbot-external-memory.ipynb)

 ## MODULE 3
 ### LESSON 1: Streaming
 - **Learned:** I learned the fundamentals of how streaming works and explored the different methods, specifically the distinction between streaming updates and streaming values. I also figured out how to stream inputs directly from a graph within the LangSmith environment.
 - **Tweak:** I experimented by adding a new input to both the updates and values streams to observe how the output changed.
 - **Source Code:** [M3L1_streaming-interruption.ipynb](M3L1_streaming-interruption.ipynb)

 ### LESSON 2: Breakpoints
 - **Learned:** I learnt how a breaking point works and how we can use it. I also learnt how to add a new tool, how to add the breaking point to it
  and how to use the breaking point from the studio manually using the code.
 - **Tweak:** I added a new tool power to it. I added a cell at the end and in the studio I asked a question to the LLM.
 - **Source Code:** [M3L2_breakpoints.ipynb](M3L2_breakpoints.ipynb)

 ### LESSON 3: Editing State and Human Feedback
 - **Learned:** I have learned how to manage the graphs flow by using interrupt_before to alter a nodes input, which also provides a way to insert human feedback at specific breakpoints. I also now understand how checkpointers are used to save the graphs current state so it can be reloaded later.
 - **Tweak:**  I added an interrupt_before in front of the tools node to observe what happens. I created a graph that includes interrupt_after for tools and executed it to compare behavior.
 - **Source Code:** [M3L3_edit-state-human-feedback.ipynb](M3L3_edit-state-human-feedback.ipynb)

 ### LESSON 4: Dynamic Breakpoints
 - **Learned:** I learned that breaking point is not like interrupt_before or interrupt_after. It works more like a limit when something crosses that limit it stops the process. This is very useful for saving tokens and controlling execution in our code.
 - **Tweak:** I added one more interruption in node 1 to check if the input is greater than 9. Then I added a new cell because if we are interrupting twice we need to change our input twice when it crosses both thresholds 4 and 9.
 - **Source Code:** [M3L4_dynamic-breakpoints.ipynb](M3L4_dynamic-breakpoints.ipynb)

 ### LESSON 5: Time Travel
 - **Learned:** I have learned to debug by manually adding code instead of just using an IDE built in tools. This new method let us trace different execution paths, replay errors to find their source, and examine every possible state of the program.
 - **Tweak:** I updated the graph and made my own graph where we calculate the temperature from celcius to farheineit. Then I made a new thread so it doesn’t get mixed up. 
 - **Source Code:** [M3L5_time-travel.ipynb](M3L5_time-travel.ipynb)

 ## MODULE 4
 ### LESSON 1: Parrallelization
 - **Learned:** This lesson was on parallelization which I learned just means running multiple nodes at once. I found out that the output gets combined randomly unless you make a custom function to control the order. I applied this by using Tavily to search both the web and Wikipedia at the same time.
 - **Tweak:** To test it, I started with 'start' then went to node a. From a I made three parallel paths one to b, one through c then c1 and another through d, d2, then d3. All of those then converged into e before hitting 'end'. This let me see how parallelization works with different chain lengths, and I tried out some prompt changes too.
 - **Source Code:** [M4L1_parallelization.ipynb](M4L1_parallelization.ipynb)

 ### LESSON 2: Sub-Graph
 - **Learned:** I learnt how sub-graphs work their states and their use it allows us to create and manage different states in different parts of our graph. I also learnt how to add subgraphs to their parent graph and how to use reducers to prevent collision. Also did tracing with langsmith.
 - **Tweak:** Though their was nothing much to change in the code I still added a code cell to write an example by my own demonstrating sub graphs.
 - **Source Code:** [M4L2_sub-graph.ipynb](M4L2_sub-graph.ipynb)

 ### LESSON 3: Map Reduce
 - **Learned:** I learnt how mapping basically works by breaking a problem into small sub problems and then parallelly processing them, then we aggregate the result across the the parallelized sub tasks. This is used as it is very efficient way. And then we saw a demonstration on studio.
 - **Tweak:** I changed the 5 jokes and select the best to add 4 trivias and then select the best out of these.
 - **Source Code:** [M4L3_map-reduce.ipynb](M4L3_map-reduce.ipynb)

 ### LESSON 4: Research Assistant
 - **Learned:** I tied together what I've learned about running nodes in parallel by fanning out and fanning in. We saw how to use a reducer to append parallel updates to a list, which avoids errors and even lets us set the execution order. I then applied this knowledge to build a small-scale research assistant. This agent uses parallel analysts and experts to research sub-topics, then uses a reducer to fan in all their findings and generate a final report summary.
 - **Tweak:**  I changed the research topic to risk and opportunities in investing , changed some prompts too in some cells.
 - **Source Code:** [M4L4_research-assistant.ipynb](M4L4_research-assistant.ipynb)
