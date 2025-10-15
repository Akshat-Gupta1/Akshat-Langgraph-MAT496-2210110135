# Akshat-Langgraph-MAT496-2210110135

This module introduces generic agent architecture and some common challenges faced by developers in building agents .
Why building custom agents with domain specific workflows and focus on high reliability is really important.
Using langraph to develop these custom agents..

# Lesson 1: Motivation

We learned why LangGraph is useful for building complex LLM applications.
Instead of using simple linear chains, we build dynamic graph-based workflows with loops, branches, and shared state.
This makes it easier to design systems that make decisions, use tools, and adapt while running.
It also helps me debug and scale by giving clear visibility into the workflow.

# Lesson 2: Simple Graph

We showed how to add nodes and edges to a graph.
We used conditional edges to choose the next node based on user input.
Here, we used a randomizer function to make the choice.
At the end of the file, I added a small example.
It performs one of three actions: runs a web search, opens a calculator, or sends input to a general LLM query.

# Lesson 3: Langsmith Studio

We used the existing course files to check if the LangSmith Studio works.
There wasn’t much work do...
I added the example I made earlier to this.
