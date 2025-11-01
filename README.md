# Akshat-Langgraph-MAT496-2210110135

All I learned in the LangGraph course from LangChain Academy - MAT496 Project

## About This Repository

This repository documents my comprehensive learning journey through LangGraph, covering fundamental concepts to advanced agent architectures. The work is organized into four modules, each building upon the previous to create sophisticated AI workflows.

## Module 1: Introduction to LangGraph

In this module, I explored several generic agent architectures and common challenges faced by developers in building agents. I learned why building custom agents with domain-specific workflows and focusing on high reliability is crucial. LangGraph makes it easy to build these custom agents.

### Lesson 1 - Motivation
I learned why LangGraph is valuable for building complex LLM applications. Instead of working with simple, linear chains, LangGraph enables the creation of dynamic, graph-based workflows with loops, branching, and shared state. This makes it easier to design agent-like systems that can make decisions, use tools, and adapt during execution.

### Lesson 2 - Simple Graph
I learned how to define the state of a graph, what nodes are, and how to define nodes and edges (including conditional edges). I constructed graphs using special nodes such as START and END, compiled graphs to see Mermaid diagrams, and used the `invoke` method to run the entire graph synchronously. I also visualized graphs in the LangGraph platform.

**Reference notebook**: Module 1/simple-graph.ipynb  
**My work**: Module 1/simple_graph_mywork.ipynb - Modified with custom questions and implementation

### Lesson 3 - LangSmith Studio
I learned how to visualize graphs in LangGraph Studio, an interactive IDE for building, visualizing, and debugging AI agent workflows. I familiarized myself with all the features provided by LangGraph Studio.

**Reference notebook**: Module 1/langsmith_studio.ipynb

### Lesson 4 - Chain
I learned about building a simple chain that combines chat messages as graph state, using chat models in graph nodes, binding tools to chat models, and executing tool calls in graph nodes. I saw how chat models use messages to capture different roles within a conversation and how tools help models interact with external systems.

**Reference notebook**: Module 1/chain.ipynb  
**My work**: Module 1/chain_mywork.ipynb - Added a calculator tool with 4 operations and used reducers to prevent message override

### Lesson 5 - Router
I learned how the model can smartly decide when to use a tool and when to answer on its own. This helped me understand how routing works and how the model balances its own reasoning with tool usage.

**Reference notebook**: Module 1/router.ipynb  
**My work**: Module 1/router_mywork.ipynb - Modified with a power function and custom routing

### Lesson 6 - Agent
I learned how to build a simple agent using multiple arithmetic tools following the ReAct architecture. I saw how the model thinks, calls the right tools, observes results, and continues the process step by step to solve multi-step arithmetic problems.

**Reference notebook**: Module 1/agent.ipynb  
**My work**: Module 1/agent_mywork.ipynb - Extended arithmetic calculator with modulus and subtraction functions

### Lesson 7 - Agent Memory
I learned how to add memory to agents using a thread ID that helps them remember previous interactions. This allowed the agent to answer follow-up questions with proper context and maintain continuity across multiple queries. LangGraph's dev mode has a built-in persistence layer that automatically manages memory.

**Reference notebook**: Module 1/agent-memory.ipynb  
**My work**: Module 1/agent_memory_mywork.ipynb - Tested memory with threaded conversations

---

## Module 2: State and Memory

This module focuses on how to represent, maintain, and manipulate the "state" of an agent or workflow built with LangGraph. The "state" refers to the structured data that captures what the agent knows and what has happened so far.

### Lesson 1 - State Schema
I learned that a schema defines the structure and data types used in a graph. I explored TypedDict, dataclasses, and Pydantic for data validation.

**Reference notebook**: Module 2/state-schema.ipynb  
**My work**: Module 2/State_schema_mywork.ipynb - Created a custom graph with Pydantic validation

### Lesson 2 - State Reducers
I explored state reducers, which define how state updates are applied to specific keys or channels in the schema. I learned about built-in reducers and created custom reducers for specific use cases.

**Reference notebook**: Module 2/state-reducers.ipynb  
**My work**: Module 2/state-reducers-mywork.ipynb - Experimented with custom reducers

### Lesson 3 - Multiple Schemas
I learned about using private state for internal processing and how to define separate input and output schemas while maintaining a richer internal schema.

**Reference notebook**: Module 2/multiple-schemas.ipynb  
**My work**: Module 2/multiple-schemas-mywork.ipynb - Built graphs with distinct schemas

### Lesson 4 - Trim and Filter Messages
I learned about managing message history efficiently in long-running conversations by trimming or filtering messages to reduce token usage.

**Reference notebook**: Module 2/trim-filter-messages.ipynb  
**My work**: Module 2/trim-filter-messages-mywork.ipynb - Built a chatbot with message trimming

### Lesson 5 - Chatbot with Summarizing Messages and Memory
I learned how to create a chatbot that automatically summarizes earlier parts of a conversation and uses checkpointers to save graph state.

**Reference notebook**: Module 2/chatbot-summarization.ipynb  
**My work**: Module 2/chatbot-summarization-mywork.ipynb - Created a study assistant chatbot

### Lesson 6 - Chatbot with External Memory
I learned about external memory storage options such as PostgreSQL and SQLite for persistent conversation state.

**Reference notebook**: Module 2/chatbot-external-memory.ipynb  
**My work**: Module 2/chatbot-external-memory-mywork.ipynb - Implemented SQLite persistence

---

## Module 3: UX and Human-in-the-Loop

This module covers streaming, breakpoints, and user interaction patterns for creating transparent and controllable AI systems.

### Lesson 1 - Streaming
I learned about two kinds of streaming: streaming values (complete state after every node) and streaming updates (only changes to state). I also learned about token streaming with `.astream_events`.

**Reference notebook**: Module 3/streaming-interruption.ipynb  
**My work**: Module 3/streaming-interruption_mywork.ipynb - Modified with custom queries

### Lesson 2 - Breakpoints
I learned how breakpoints facilitate approval, debugging, and state editing in AI workflows. Breakpoints allow pausing execution, inspecting state, and resuming.

**Reference notebook**: Module 3/breakpoints.ipynb  
**My work**: Module 3/breakpoints_mywork.ipynb - Added more mathematical operations

### Lesson 3 - Editing State and Human Feedback
I learned how to edit the graph state after an interruption using breakpoints and the "add_message" reducer. I also learned to inject user input dynamically.

**Reference notebook**: Module 3/edit-state-human-feedback.ipynb  
**My work**: Module 3/edit_state_human_feedback_mywork.ipynb - Implemented state editing with user input

### Lesson 4 - Dynamic Breakpoints
I learned about dynamic breakpoints that allow the graph to interrupt itself automatically based on conditions in its state using `NodeInterrupt`.

**Reference notebook**: Module 3/dynamic-breakpoints.ipynb  
**My work**: Module 3/dynamic_breakpoints_mywork.ipynb - Used step count triggers

### Lesson 5 - Time Travel
I learned that Time Travel in LangGraph allows going back to a previous state, re-running nodes, or modifying inputs before continuing execution.

**Reference notebook**: Module 3/time-travel.ipynb  
**My work**: Module 3/time_travel_mywork.ipynb - Experimented with checkpoint restoration

---

## Module 4: Building Your Assistant

This module covers advanced topics including parallelization, sub-graphs, map-reduce patterns, and research assistants.

### Lesson 1 - Parallelization
I learned about fanning out and fanning in during parallel execution of steps in a LangGraph workflow. I learned how to use reducers to merge updates from multiple parallel nodes.

**Reference notebook**: Module 4/parallelization.ipynb  
**My work**: Module 4/parallelization_mywork.ipynb - Built an investor brief generator

### Lesson 2 - Sub-graphs
I learned that sub-graphs provide a way of keeping independent states in various sections of a large graph, useful in multi-agent environments. They communicate with the parent graph via shared keys.

**Reference notebook**: Module 4/sub-graph.ipynb  
**My work**: Module 4/sub-graph-mywork.ipynb - Created a product review analyzer

### Lesson 3 - Map-Reduce
I learned that MapReduce divides a big job into smaller parts that can be executed simultaneously and combines their outputs efficiently using the Send API.

**Reference notebook**: Module 4/map-reduce.ipynb  
**My work**: Module 4/map_reduce_mywork.ipynb - Built a fun fact generator

### Lesson 4 - Research Assistant
I learned to construct a multi-agent AI setup for research that simulates a human analyst's workflow. I saw how to use MapReduce to run research tasks in parallel and automatically gather results.

**Reference notebook**: Module 4/research-assistant.ipynb  
**My work**: Module 4/research_assistant_mywork.ipynb - Created an entrepreneurship model

---

## Key Takeaways

Throughout this course, I learned:
- How to build complex, stateful AI agents with LangGraph
- State management techniques including schemas, reducers, and memory
- Human-in-the-loop patterns for controllable AI systems
- Advanced patterns like parallelization, sub-graphs, and map-reduce
- How to debug and visualize agent workflows effectively

## Student Information

**Name**: Akshat Gupta  
**Roll Number**: 2210110135  
**Course**: MAT496  
**Repository**: https://github.com/Akshat-Gupta1/Akshat-Langgraph-MAT496-2210110135
