# Plan-Driven Methodologies

> Plan-Driven methodologies approach software development with a **structured, sequential process**, in which each phase of the SDLC is carefully planned and completed in order.

This methodology is sometimes called the "waterfall" approach, since work flows downward through distinct stages (Requirements, Design, Development, Testing, Deployment, and Maintenance).

## Characteristics of Plan-Driven Approaches
While the Waterfall model is one example of Plan-Driven Methodologies, the core characteristics shared by Waterfall and others include:

**Up-front Planning**: where Requirements and designs are expected to be complete and *stable* before development begins.

**Sequential**: Each phase is completed before the next starts, with limited overlap.

**Documentation-heavy**: Progress and handoffs between phases are primarily handled through documentation, with documentation being considered the source of truth.

**Predictable**: Plan-Driven methodologies work best when requirements are *well-understood* and unlikely to change.

## Advantages

Plan-Driven methodologies are less common today, but do have some distinct advantages. The clear structure and milestones makes it easier to identify when something is "Done". This means progress is easier to measure, and so it's usually much easier to identify how a project is going and if it's on or off-track.

Additionally, for projects with tightly **regulated requirements**, such as medical devices, aerospace devices, or government contracts, the Plan-Driven approach can ensure nothing gets missed, which can be life-or-death in some cases!

## Disadvantages

The biggest disadvantage is a lack of flexibility. If requirements change during development, this can be very hard to reconcile. Additionally in many methodologies, testing often happens late which makes errors costly to fix, if they can be fixed at all.

This can result in software that might meet the original plan, but doesn't fit the actual user needs as they evolve.

## Common Plan-Driven Methodology Models

**The Waterfall Model** is the classic example of a Plan-Driven approach. This model divides the process into a series of linear, sequential stages:
1. Requirements - All functional and non-functional requirements are gathered and documented in detail.
2. Design - System architecture, database structures, and technical specifications are created.
3. Development - Programmers translate the design into actual code.
4. Testing - Completed software is tested against requirements.
5. Deployment - The tested system is released to users.
6. Maintenance - The system is updated and supported over time.  

Each stage must be completed and documented before moving onto the next. This structure makes the model predictable and easy to manage, but also inflexible. Changes discovered late in the process can be expensive to accommodate.

**The V-Model**  is an extension of the Waterfall approach. It emphasizes that each development stage has a directly corresponding testing stage, arranged visually in the shape of a "V":

On the left side of the V are the planning and design stages (requirements, system design, detailed design).

At the bottom of the V is the Implementation (coding) phase, the “primary phase” where the system is actually built.

On the right side of the V are the testing stages, which mirror the earlier planning:

- Unit testing → validates detailed design.
- Integration testing → validates system design.
- System testing → validates requirements.
- User acceptance testing → validates business needs.

This structure ensures that testing is planned alongside each design stage, rather than being left entirely to the end. Although the execution of tests still occurs after implementation, the test cases are designed much earlier, reducing the risk of missed requirements.

```admonish example title="Check Your Understanding"
1. What are the main characteristics of plan-driven methodologies?
2. In what situations might a plan-driven methodology be the best choice?
3. How does the V-Model improve on the Waterfall model in terms of testing?
4. Why might plan-driven methodologies struggle in projects with rapidly changing requirements?
```