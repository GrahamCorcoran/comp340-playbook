# System Integration

> System Integration is about how separate components, services, or subsystems work together as one cohesive system.

When building software, few components operate in isolation. A web app interacts with an authentication provider. A service calls a database. A mobile app syncs with an API. Each of these interactions introduces complexity since they add failures, delays, retries, mismatching expectations, and partial results.

## Interactions as States

Every interaction between systems can be viewed as a mini state machine:

- A request is initiated
    - It becomes pending
- It succeeds, fails, or times out
    - The caller responds to the outcome with its own state change

Using state models to represent these integrations can help with communication as it shows what states external systems must reach before an interaction can continue. This is especially important in distributed systems, where timing, latency, and partial failures are common.

## Different Systems, Different States

One of the main challenges when integrating systems with each other is that each system is tracking its own states. When these systems interact, the task becomes keeping state transitions consistent with each other and understanding how these states map to each other. When systems interact, they form a combined state model.

For example, consider a simple case:

User places an order → Order Service communicates with Payment Service.

Each subsystem has its own states. The Order Service might track the order through the states of Draft, Submitted, Payment Pending, Completed, Cancelled whereas the Payment Service might track its own states as Not Started, Authorizing, Authorized, Declined, Error.

~~~admonish example title="Order / Payment Processing State Diagram Example"
[Mermaid Link](https://www.mermaidchart.com/play#pako:eNp1UUtrwzAM_isix0EuPeYwGEuvo9DjuoNqa6khsYuiFLrS_z4_4iQNxCfre8mSH4Vymoqq6AWFaoMNY1fedicL_ny__UBZvkPN-Csnm8BYRPg4nDsjQrqCPl7BsSZOsomM0gPeO7JyIKuNbXJUbLri4JG4Zf8vJ0dB9mHZGc6MRtHHIBfH5s9nVHCmxljAEUIxbmFcKF-caRClqO-3xXtmx15HfDOKgEK5ra5JtcaGYD3ewgSzPvOrMStgEr7Puth1lZjYZ45brTFoP113bSnmXRM7rSQ8ZMuFVlHbBtfgxwSV6nGJyTYlR4f_pxHO1hkunv9EhcWA)
```
stateDiagram-v2
    [*] --> Draft

    Draft --> Submitted: submit order
    Submitted --> PaymentPending

    state PaymentPending {
        [*] --> NotStarted

        NotStarted --> Authorizing: begin authorization
        Authorizing --> Authorized: success
        Authorizing --> Error: service error
        Authorizing --> Declined: declined


        Declined --> NotStarted: retry
        Error --> Declined: 
    }

    PaymentPending --> Completed: payment authorized
    PaymentPending --> Cancelled: user cancellation

    Completed --> [*]
    Cancelled --> [*]
```
~~~

```admonish example title="Load Balancing Article"
There's a great article on [Load Balancing](https://samwho.dev/load-balancing/) that I quite like that I think both explains an interesting concept in a great way, as well as demonstrates servers in different states in a simplified version of a complicated system.
```