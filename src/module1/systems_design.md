# Systems Design

> Systems Design is the phase where requirements are translated into technical solutions. It's the *blueprint for development*. This phase sets the foundation for how the system will function, scale, and evolve throughout its lifecycle.

When in the Systems Design phase, you must ensure the system is maintainable, able to scale to the number of users you anticipate, and meets the functional and non-functional requirements you have identified.

## Principles and Trade-Offs
In Systems Design, you are constantly making trade-offs. There are multiple, often competing priorities that must be balanced in order to create a system that meets its requirements, while managing complexity and resource constraints.

```admonish info title="The '-ilities'"
Certain non-functional requirements related to System Quality are often called the "-ilities" and refer to how capable a system is in various ways. For example, "accessibility" refers to how accessible a site is. If you're interested, Wikipedia has a fairly extensive [List of System Quality Attributes](https://en.wikipedia.org/wiki/List_of_system_quality_attributes) and they're worth a read!
```

### Trade-Off Example

Imagine you are building Point-of-Sale (POS) system for a retail store. The core functionality is to  handle in-person transactions. To accomplish this, you'll need to ensure your software can integrate with your debit/credit machine, open the cash register, and managing inventory. Since this is critical, it's the first thing you'll focus on in the design phase.

Maybe those non-negotiables will take you around 40h of work to accomplish. You could theoretically start using this POS Software after a week! You could launch this, and the retail store will be able to begin processing transactions.

However: your software crashes after every transaction, and the system takes about two minutes to restart each time. While the POS Software is technically *working*, this performance issue might be a dealbreaker in the real world. Let's suppose solving this problem would take 10h to resolve.

Also while doing initial testing, you realize having to manually update prices via the POS directly is frustrating and takes the machine out of commission for the time it takes to update. So based on user feedback, you decide adding the ability to do remote price updates would be a good feature. Let's suppose that adding this feature would be another 10h of work.

This is a fairly simplified example of the trade-offs that are always present in systems design. 

- Do you launch with the basic functionality and opt to fix issues as they arise? (Risking user frustration)
- Do you invest more time up front to make the system more reliable and easier to maintain, but at the expense of a delay in shipping "out the door"?
- Do you prioritize new features like remote price updates, knowing they'll improve the software in the future? 

These dilemmas are constantly present in systems design. You'll always need to make decisions and trade-offs and decide what's important to your software, and what can be deferred. As a Systesm Designer, you need to evaluate these requirements and decide where you can compromise, and where you *must* invest.

### Role Highlight: Product Manager
The role of a Product Manager is very common in the software industry, and their core responsibility is usually to align and balance customer needs with business goals. This can mean defining priorities, or just ensuring the team is focused on what matters most to the users and the business. For companies which have more than a handful of developers, this coordination becomes a full-time job!

## Types of Design

In the Systems Design phase, we typically break down design work into different *levels* depending on how detailed the work is, and which part of the system we're focusing on. Think of this as the Big Picture vs. a Deep Dive on individual details.

For this course, we'll focus on two levels of design: High-Level Design, and Low-Level Design. This is not a complete picture: the Systems Design field can be expanded on in many different directions and well beyond two levels, but it gives a good foundation for understanding.

### High-Level Design
High-Level Design focuses on the overall architecture of the system as a whole. This is where you figure out the major components and how they'll interact with each other. At this level, you should be answering questions like:

- What are the main services or modules?
- How will data flow through the system?
- Is this a web app? A mobile app? A desktop app?
- What type of database will we use?
- Do we need any external data storage, or other APIs or integrations?

This level of design sets the *foundation* for the system. A good High-Level Design creates boundaries which make it easier to divide work across a team, and ensure all the pieces will eventually fit together. 

### Low-Level Design
Low-Level Design zooms in on individual components or modules. This is where you figure out the internal logic and structure of each part of the system.

At this level, you should be answering questions like:

- What classes or functions do I need?
- What edge cases exist, and how should I handle them?
- What kind of data structures should be used?
- How should we handle errors, and logging?

This Low-Level Design is helpful for developers who are about to start coding. It removes ambiguity and helps avoid technical debt down the road by clarifying the goals of how things should work *before* anyone touches their keyboard.