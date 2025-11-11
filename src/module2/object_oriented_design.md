# Object-Oriented Design

> Object-Oriented Design is about modeling how our system's components will behave and interact in code.

So far, we have:

1. Discussed the domain and thinking about how the *entities themselves* are defined.
2. Discussed the database and how the entities *relate* to one another.

Now, with Object-Oriented Design (OOD) we are looking to wrap the entities, their relationships, and the behaviours of those entities together.


## Mapping Entities to Objects 
In Object-Oriented-Design is where we take the real-world ideas from our domain model and start shaping them into classes, objects, and methods that can actually run in a program. The goal is to design software that's organized, reusable, and easy to maintain.

When transitioning from a Domain Model to an Object Model, we move from describing "what exists" to describing "how it works."

In this stage, we:

- Map Entities to Classes
- Map Attributes to Properties or Fields
- Map Relationships to References or Collections
- Add Behaviours that define what objects can do

For example, if our domain model has a Book entity with attributes like title and author, and a Library entity that contains many books, our object model might define a Library class that includes a books list and a checkOut() method.

This step helps us visualize how data and logic come together, and how our system behaves.

## The Core Concepts of Object Orientation

Object-Oriented Design is built around a few foundational ideas:

- **Encapsulation:** Keeping data and behaviour that belong together inside the same class.
- **Abstraction:** Hiding unnecessary details so we can focus on what an object does, rather than *how* it's done. 
- **Inheritance:** Allowing one class to share behaviour and structure with another.
- **Polymorphism:** Letting different classes respond to the same action in their own way.

These ideas help make systems easier to extend, modify, and understand as they grow in size and complexity.

## Common Design Patterns and Principles

As you progress through the industry, you'll start to recognize common problems that appear across many projects. Design Patterns are reusable solutions to these recurring challenges.

For example:

- A **Singleton** ensures only one instance of a class exists.
- A **Factory** helps create objects without specifying their exact types.
- An **Observer** lets multiple objects stay updated when something changes.

These patterns are built on the same OOD principles of abstraction, encapsulation, and clear responsibility. They provide a shared vocabulary for discussing design decisions.

```admonish info title="Design Tips"
- When designing your classes and interactions, **start from the domain**. Design classes that directly reflect the key concepts in your system.
- Keep responsibilities small and clear: Each class should have one clear purpose. Combine small, focused classes instead of building deep hierarchies. 
- Think about how objects collaborate: Use method calls and relationships to model real-world interactions.
```

Good Object-Oriented Design makes software more flexible and intuitive to work with. The more carefully you plan these relationships, the easier development and maintenance become down the line.