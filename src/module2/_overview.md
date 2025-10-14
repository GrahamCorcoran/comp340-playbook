# Static Design

> Static Design is about organizing the solution before we bring it to life.

In Systems Analysis, we focused on understanding the problem, and figuring out what we need to build and why.
Now, in Static Design, we shift gears and start thinking about how the solution will be structured.

If Systems Analysis is like designing the floor plan for a house, Static Design is when we decide how the walls fit together, where the electrical outlets go, and how the plumbing connects. It's not the final build yet, but it's when the abstract ideas start turning into a tangible structure.

We call it static because it deals with the parts of the system that don't move. These are the nouns of our software:

- Classes
- Objects
- Entities
- Relationships
- Attributes

These are the components that define your program, rather than define how your program behaves.

## When You Skip Static Design

When developers skip Static Design, you can usually tell. The biggest risk in avoiding Static Design is a lack of coherency, which can make it challenging to develop without painting yourself in a corner.

You may see:

- Classes named after UI buttons instead of concepts
- Databases full of vague tables like data or info
- Multiple parts of the system describing the same thing slightly differently (user, person, customer, account_holder)

It's not that these programs can't work, but they become hard to maintain because no one's quite sure where the "truth" lives.

## What We'll Learn

In this module, we'll explore how to build a clear, consistent model of our software's structure.

That includes:

- Domain Modeling – describing the real-world concepts the software represents.
- Database Design – turning those concepts into tables, fields, and relationships.
- Object-Oriented Design Patterns – reusable approaches for structuring and connecting parts of a system.
- Class Diagrams – showing how entities or classes are related in UML.
- Sequence Diagrams – illustrating how those parts might eventually interact.

By the end of this module, you'll be able to look at a problem and sketch out a solid foundation for any application. This foundation should be something that's technically sound and easy to reason about.