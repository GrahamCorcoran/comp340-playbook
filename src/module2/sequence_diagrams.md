# Sequence Diagrams

> Sequence Diagrams are about modeling how different parts of a system interact over time to accomplish a specific task.

Where Class Diagrams are showing the structure of a system, sequence diagrams are how we begin showing dynamic behaviour, how objects communicate to make something happen. They help us visualize the flow of messages between objects, methods, or systems in a particular use case.

A Sequence Diagram represents a scenario as a series of interactions arranged vertically over time. Each object or component involved is shown as a lifeline, and the messages they send to each other are shown as horizontal arrows.

Think of it as a timeline that shows who talks to whom, in what order, and what the result is.

## Elements

A Sequence Diagram is made up of a few elements:

**Actors:** Represent external users or systems that start the interaction (e.g., a User).

**Objects (Lifelines):** Represent parts of the system that participate in the interaction (e.g., LibrarySystem, Book, Database).

**Messages:** Arrows showing communication between lifelines. These can represent method calls, signals, or data requests.

**Return Messages:** Dotted arrows showing responses or results returned from an operation.

## Usage
Sequence Diagrams are most useful when you need to:

- Clarify the flow of a specific use case
- Identify which classes or components handle which responsibilities
- Communicate how data and control move through the system
- Validate that your design matches real-world behaviour. 

Like most of the diagrams we've spoken about so far, they are very useful in early design discussions, where having a simple visual aid can be helpful in revealing overly complicated interactions before you've committed to building them.

To create a Sequence Diagram, you should start with a clear *scenario*. Identify the main actors and components, and then map out the messages that are required to occur, and the order in which they occur.

1. **Identify participants:** who's involved in the interaction?
2. **List the key steps:** what happens from start to finish?
3. **Draw lifelines for each participant.**
4. **Add messages between lifelines to show communication flow.**
5. **Include activations and returns to show when and how each participant responds.**

