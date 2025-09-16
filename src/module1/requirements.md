# Requirements Gathering and Analysis
Requirements gathering and analysis is the first phase of the [Software Development Lifecycle (SDLC)](./sdlc.md). The goal is to understand what the software should do and why it is being built. In this phase, we identify the needs of stakeholders, clarify the scope, and document requirements to guide later phases.

Good requirements gathering reduces wasted effort, lowers costs, and helps ensure that the final product solves the right problem. Poor requirements, on the other hand, are one of the most common reasons software projects fail.

Throughout the SDLC we will regularly need to gather requirements for different parts of the project. There are several **key activities** associated with the Requirements Gathering and Analysis phase. These key activities are:

**Identify Stakeholders:** We must identify who will use the system, and how our system will benefit them. These are our Users.

**Elicit Requirements:** We must elicit requirements to identify all of the possible things our system could do to help the user.

**Analyze Requirements:** Based on the Requirements we have elicited, we must clarify, refine, and resolve conflicts in these requirements. Often we will have far too many "requirements" and we must identify which of those are core requirements, versus just nice-to-have feature enhancements.

**Document Requirements:** When we have identified core requirements, we must record them in a clear, unambiguous form.

**Validate Requirements:** We must finally validate that these requirements accurately reflect the needs of the users, and ensure we haven't missed anything.

## Use Cases
One tool we use in requirements gathering is the *use case*. A use case describes a specific interaction between a user (often called an "actor") and the system. The goal is to capture what the user wants to accomplish, rather than how the system will do it. As an example, we might make the following Use Case for a LMS

```
Actor: Student
Goal: View Grades
User Flow:
    - Student logs into the system.
    - Student searches for the desired course.
    - Student accesses course.
    - Student accesses Gradebook.
    - System displays grades to student.
```

Use cases are powerful because they:

- Keep requirements grounded in user needs.
- Help identify edge cases and exceptions.
- Provide a bridge between business goals and system design.

### Actor
The Actor represents the entity accomplishing something due to our system. Usually this is a person (such as a student, or faculty member), but can also be another system or service for example in the context of an API.

### Goal
The Goal represents the **core objective** the Actor wishes to accomplish. This defines the essential outcome of the requirement. If that outcome isn't met, the requirement hasn't been achieved. 

For example, in our grades example above the goal is to **view grades**. 
- If the system displays the grades as a percentage, this goal has been achieved. 
- If we also add an exclamation point indicator when a grade is considered a failing grade, this is additional feature *enhancement* that goes beyond the core requirement.

### Preconditions
Preconditions are the conditions that must already be true before the use case can begin. They represent assumptions that the system and stakeholders are relying on when defining requirements. For example, in the Use Case we defined above, there's a hidden precondition we glossed over which is that the student must be enrolled in some course, and they must have done something to see a grade.

```
Actor: Student
Goal: View Grades
Precondition: Student is enrolled in a course, has completed some graded work.
User Flow:
    - Student logs into the system.
    - Student searches for the desired course.
    - Student accesses course.
    - Student accesses Gradebook.
    - System displays grades to student.
```

As you can see, it's very easy to gloss over certain preconditions as they're assumed to be obvious or implied, but part of successful requirements gathering is not making assumptions without validating they're safe to make. However if the student isn't enrolled, the use case fails before it even starts! This is why accurately understanding your preconditions matters.

### Main Flow / User Flow
The Main Flow (sometimes called the **User Flow**) defines the sequence of steps the user takes along the expected path to completion. This is often referred to as the "Happy Path": if everything goes as intended, the Actor will follow these steps and at the end will have achieved their goal.

### Postconditions
The Postconditions are the outcome of a single use case. They define what the state of the system is after the use case completes successfully. We could further expand our example above:

```
Actor: Student
Goal: View Grades
Precondition: Student is enrolled in a course, has completed some graded work.
User Flow:
    - Student logs into the system.
    - Student searches for the desired course.
    - Student accesses course.
    - Student accesses Gradebook.
    - System displays grades to a student.
Postcondition:
    - User understands and is aware of their grade.
```

```admonish example title="Check Your Understanding"
1. Why do we use the term **Actor** instead of simply saying **User**?
2. Think of a program you use regularly. What would you consider its **Happy Path**?
3. Can you recall a time when you went off the Happy Path in a program? How did the program handle it?
4. In the example above of a postcondition, how could the Main Flow ever be completed without the postcondition being true?
```