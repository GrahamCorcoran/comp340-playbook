# State Modeling

> State Modeling focuses on how a system changes over time, and the rules that govern those changes.

In State Modeling, our primary focus is on how the system behaves as it transitions from one situation (state) to another. This perspective is especially useful for features or components whose behavior depends on what has happened before.

State models help us answer questions such as:

- What possible states can this system or object be in?
- What events or conditions cause transitions between states?
- What constraints or rules limit how the system may change?
- What behaviour occurs when entering or leaving a state?

State models describe behaviors of systems. In the real world, many systems have complex rules about what can happen when. State modeling attempts to break these rules down and make them explicit.

Diagraming state models can help teams:

- Understand edge cases and error paths
- Identify invalid sequences (e.g., trying to "submit" something that isn't ready to be submitted)
- Simplify complex logic into clearly defined modes
- Communicate how a system should respond to inputs
- Support testing by outlining expected transitions and constraints

In software engineering, State modeling is widely used in UI design, authentication systems, games, embedded systems, and any domain where rules depend on timing or past events.

## State Machines and State Diagrams

The most common tool for state modeling is the Finite State Machine (FSM) - a model where a system:

- Has a finite set of states
- Can be in exactly one state at a time
- Responds to events that trigger transitions

A State Diagram visualizes these ideas using:

1. States (circles or rounded rectangles)
2. Events that trigger a move (arrows)
3. Entry / Exit actions (what the system does as it enters or leaves a state)
4. Guards or conditions that must be true for a transition to occur

### States

A state represents a situation or mode of the system. Conceptually, from your databases class you can think of it sort of like enums. For example:

- A user account may be: **Active**, **Locked**, **Pending Verification**
- A traffic light may be: Green, Yellow, Red
- A document may be: Draft, Submitted, Approved, Archived

```admonish note
Good states describe meaningful differences in behaviour rather than being simply stored values. Using the traffic light example above, the actual colour of a traffic light is not particularly important. What does matter is driver's ability to differentiate between the colours. The information the "red light" is conveying isn't colour, it's the **state** that traffic coming from a given direction should be in: stopped. 
```

### Events

Events trigger attempts to transition between states.

Examples:

- A user clicks “Submit”
- A timer expires
- A car arrives at a red light's sensor.

An event does not always cause a transition, because guards may block it.

### Transitions

Transitions define how the system moves from one state to another.

`Current State + Event + Guard → New State (with optional actions)`

Transitions may also contain:

- Entry actions (run when entering a state)
- Exit actions (run when leaving a state)
- Transition actions (run during the move)

### Guards (Conditions)

A transition may only occur if certain conditions are true.

For example:

```
[Submitted] --(approve)--> [Approved]
    [Only if user.role == "Manager"]
```

Guards prevent invalid sequences and make **business rules explicit.**

## Using State Modeling

State Modeling is most helpful when:

- Behavior depends heavily on history
- There are many edge cases
- Certain actions must be prevented in some states
- The system involves modes (e.g., "editing", "reading", "locked", "error")
- You want to clarify complex logic before implementation

Some examples of state models you may be familiar with include:

- Login/Logout flows (Is the actor logged in or logged out?)
- Multi-step forms (Which step of the form is the actor interacting with?)
- Payment or billing lifecycle
- Game objects (enemy AI difficulty, player status)
- Media players (playing, paused, buffering, stopped)


### In-Class Example: Login Flow (Simplified)

~~~admonish example title="In-Class Example: Login Flow" 
The following [Mermaid Diagram](https://www.mermaidchart.com/play#pako:eNqNUcsKwjAQ_JWlR6EXjz0I4gMEwQ-wHmKyxGC6gXTbHkr_3T5tK1XMLTszO7uzZSCdwiAKUhaMeyO0F0mYr2OC-l1XNwjDDZyd1qguGcfUAe_CABs6WldEYJ0GQwOtbTrCUHblaesDMXpDeudRIbERNh1JC2Ar2mb8aP5ScI1GkGb3xPCom-PffKJ60lxYo0Aumf_bhJAL55-A3jv_U17v3MwqJaa9TzUJtM9ozPtEH-yhPL9JG7prbhNUL6CrmBE) presents a simple login state model. Based on the model, answer the following:
```
stateDiagram-v2
    [*] --> LoggedOut

    LoggedOut --> LoginFlow: log in

    state LoginFlow {
        [*] --> EnteringCredentials
        EnteringCredentials --> Authenticating: submit
        Authenticating --> EnteringCredentials: invalid credentials
        Authenticating --> EnteringCredentials: network error
        Authenticating --> [*]: success
    }

    LoginFlow --> LoggedIn: success
    LoggedIn --> LoggedOut: logout
```

1. How many states exist in the diagram, and what are they?
2. What other states might exist? 
3. How might we use the "Logged In" or "Logged Out" states?
4. If an actor is in the "Authenticating State", are they also implicitly in any other states?
~~~

## Clear State Modeling

Modeling States, like much of the content in this course is about **communicating** to others. With State diagrams, achieving that involves:

- Keeping states meaningful and distinct
- Avoiding "data-values-as-state" (e.g., "count=5" isn’t a state)
- Avoiding overloading stated. Instead, they should be split them if behaviour differs
- Using guards where applicable to prevent invalid state transitions.
- Including entry/exit actions only when they add clarity

In general, you should always validate your diagram with "What happens if...?" scenarios.