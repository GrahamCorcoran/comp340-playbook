# Workflow Modeling

In Workflow Modeling, what we are working to describe is:

- What Happens?
- In What Order?
- Under What Conditions?
- By which actors?

This can be done using basic flowcharts, swimlane flowcharts, process maps, and more UML-specific tools such as Activity Diagrams.

## General-Purpose Workflow Flowcharts

Flowcharts are the simplest and most flexible way to model a process. They use basic shapes to model actions, decisions, and when the process starts/ends. Flowcharts are excellent for:

- Describing straightforward, step-by-step processes.
- Modeling deicison points. (If valid -> do X, else do Y.)
- Illustrating loops or repeated actions.
- Communicating logic to beginners or non-technical audiences.

Basic Flowcharts have some key elements:

- **Start/End Nodes** - Which indicate where this specific process begins and concludes.
- **Action Steps** - Representing tasks, operations, or activities.
- **Decision Points** - Indicating a branch in the workflow based on True/False outcomes.
- **Flow Lines** - Showing the direction of the process from each step to the next.

~~~admonish title="In-class Activity"
Copy-paste the following flowchart code into a mermaid.js-compatible editor. Modify the flowchart to prompt users to re-submit rather than reject their request entirely.

```
flowchart TD
    A([Start]) --> B[Receive request]
    B --> C{Is the request valid?}
    C -->|Yes| D[Process request]
    C -->|No| E[Reject request]
    D --> F([End])
    E --> F([End])
```
~~~

## Adding Actors
In the basic example above as part of our in-class activity, the flowchart describes a process without any real mention of actors. The user is implied by the system prompting for re-submission, but is never explicitly drawn out.

This can impact the readability of a diagram and even the design of a program because the concept of **responsibility** isn't clear. When we prompt the user for re-submission, what happens when they just don't respond? 

When diagramming, this is solved by defining who the actors are for a given action. Rather than just "Submitting Request" -> "Is Request Valid?", the user actor will submit the request, the system actor will *receive* the request, and then the request submission's validity will be determined.

These concepts of Actors can be modeled in Mermaid's flowcharts using *subgraphs*.

~~~admonish example title="Subgraph Example - Actor 'Lanes'"
The following example shows actor 'lanes' modeled using subgraphs in Mermaid.

```
flowchart LR

    %% User lane
    subgraph User["User"]
        U1([Start])
        U2[Submit Request]
        U3[Re-submit Request]
    end

    %% System lane
    subgraph System["System"]
        S1[Receive Request]
        S2{Is Request Valid?}
        S3[Process Request]
        S4[Prompt User to Re-submit]
        S5([End])
    end

    %% Flow between lanes
    U1 --> U2 --> S1 --> S2

    S2 -->|Yes| S3 --> S5
    S2 -->|No| S4 --> U3 --> S1

```
~~~

## Activity Diagrams and Formal Specifications

Different softwares have different ways of modeling these specifications to try and keep the syntax consistent. UML Actiivty Diagrams are one example which are particularly well suited for:

- Showing concurrency or parallel processes.
- Modeling object flow through a system.
- Modeling multiple different actors, where responsibility must be clear.

UML's Activity Diagrams formalize the flowcharts further adding **forks and joins** to show parallel workflows, **swimlanes** to model actors or other responsible parties, and **object nodes** which represent data or artifacts moving throughout the process. 

```admonish example title="Activity Diagrams: PlantUML"
The following [documentation](https://plantuml.com/activity-diagram-beta) outlines how Activity Diagrams are modeled and the UML syntax for them. In particular, the UML concepts of a Fork are very useful for modeling parallel workflows.
```