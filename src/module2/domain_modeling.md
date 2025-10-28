# Domain Modeling

> Domain Modeling is about capturing the real-world concepts your system needs to understand.

Before we can build a database or write classes, we need to make sure we actually understand the world our software represents. Beyond just the classes, or database tables, or functions - what are the real concepts we're trying to model?

## The "Domain"

A domain is just the problem space you're working in. This is what your software needs to understand.

For a few examples:
- A banking system deals with accounts, customers, and transactions.
- Blackboard's model deals with students, courses, and grades.
- A video game might deal with characters, items, and levels.

Each of these has its own rules, relationships, and concepts. It's these ideas which we want to capture in our domain model.

When developers misunderstand the domain, we end up building the wrong abstractions.
For example, imagine building a "Course Registration System" where a Student can only have one Course at a time. That might technically work, but it fails to reflect reality which is that students take many courses.

A domain model helps us avoid those mistakes by making the system's assumptions visible and reviewable.

## How to Build a Domain Model

Building a domain model is about discovery and refinement. We need to:

- Identify the main concepts (entities)
- Skim through requirements, user stories, or even conversations.
- Look for the nouns. Student, Course, Instructor, Invoice, etc.
- List the details (attributes)
    - What information do we need to track for each one?
    - e.g. Student → name, email, student_id
- Map the relationships
    - How do these entities connect?

During this whole process, you should ensure to validate this model with real people. Your stakeholders should agree this is how the entities are modeled, so that you can be confident in the implementation you're moving forward with.

| Entity     | Attributes       | Relationships                          |
|------------|------------------|----------------------------------------|
| Student    | Name, Email      | Enrols in Courses                      |
| Course     | Title, Credits   | Taught by one instructor; Has students |
| Instructor | Name, Department | Teaches courses                        |

A simple visual model might look like:

`[Student] *-- enrolls in --* [Course] *-- taught by --1 [Instructor]`

At this stage, this isn't code or a database schema yet. It's just a map of how the system thinks about the world.

```admonish example "In-Class Exercise - Building a Library's Inventory System"
In class, we will model a Library's inventory system using [Mermaid.js](https://mermaid.live/edit#pako:eNptkbtOAzEQRX_FmgpEtojoLBqUECkFFV1kCc2uB6-1fgQ_FImQf8e7sCYkuJo543t1PT5C5yUBh85gjGuNKqAVjpXz6LRFwx4-m4atczdc042O_TXdURvwD-bsTrvEUNElfklBO8UUOUnhfDhK4jPaUt7cXgwsJprhFHuKd_wGrJq2hMPKGx_qIB60nYWlfc_YDXN_OvcbH1b9mjF71B-0dRuiVHGH7gnTv_ppBb-BWu8N0_H1oI2sMGRXtbAAFbQEnkKmBVgKFscWJg8BqSdLAngpJYZBgHCjZo9u572dZcFn1QN_QxNLl_ey7OnnR-uVadErn10Cvlzen74Aox2dUQ).
```