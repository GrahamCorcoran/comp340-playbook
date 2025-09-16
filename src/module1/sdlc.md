# Software Development Lifecycle
> The Software Development Lifecycle (SDLC) is the process used to deliver software with a predictable quality and cost.

Across Software Development, there are many different ways to organize work. Some methods emphasize speed and iteration, while others emphasize stability. The SDLC represents the general flow from ideation to completion of a piece of software. This may not always be linear, since some methodologies go back and forth between phases.

## Phases

The SDLC is broken up into several phases. Depending on the context, source, and methadology you'll often see a number between 5-7 phases. This is due to the fact that with different frameworks and methodologies, you can have fewer or different phases. For example, when using Test-Driven-Development, the "Development" phase often includes testing first, then development, then validation. For the purpose of this course, we have broken the SDLC into a *five-phase* model to balance simplicity with completeness.

**1. Requirements Gathering and Analysis**

Understanding what the stakeholders actually need, and defining the goals of the system. This can involve interviews, workshops, documentation, and establishes functional and non-functional requirements. 

**2. Systems Design**
Translating requirements into a "blueprint" for development. This phase produces technical designs such as architecture diagrams, database schemas, and other mockups.

**3. Development, Validation, Testing** 
This is where the code is actually written, the features are actually built, and the work is validated to ensure it's working as expected. This phase is the most *cyclical* of all the phases, and often includes iterative testing alongside development.

**4. Deployment**
Delivering the software into a live environment where it can be used by real users. 

**5. Maintenance**
The ongoing process of resolving bugs, adding new features, and ensuring the system continues to meet user needs as requirements evolve over time. 

```admonish info title="The SDLC Phases are Cyclical"
A common misconception is that the phases of the SDLC happen only once, in strict sequence. In reality, most software goes through many iterations of the lifecycle. Each new feature, bug fix, or release re-enters the cycle, often looping back to earlier phases. This is true even when following a Waterfall methodology, where iteration can happen through re-work loops or maintenance cycles.

Think of building a house. The first time through, you gather requirements (what kind of house?), design blueprints, build, inspect, and move in. Later, you might add a deck, remodel the kitchen, or replace the roof. Each of those improvements goes through its own mini-cycle of requirements → design → build → test → use. The house is never truly "finished", it’s just continuously maintained and improved.
```