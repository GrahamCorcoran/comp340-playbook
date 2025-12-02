# Performance and Scalability
> Performance and Scalability describe how well a system responds under load, and how effectively it can grow to handle increasing demand.

In real software systems, correctness alone is not enough. An application may function perfectly under light use but fail, slow down, or become unstable when many users interact with it simultaneously. Performance and Scalability focus on designing and evaluating systems so they remain responsive, stable, and cost-effective as demand changes.


## Performance

Performance relates to the speed and responsiveness of a system. Typical questions include:

- How fast can the system respond to a request?
- Is the system meeting its target response times?
- Does performance degrade as the workload increases?

Common metrics:

- Response Time (how long a request takes)
- Throughput (how many operations per second the system can handle)
- Latency (how long it takes for data to move through the system)
- Resource Utilization (CPU, memory, disk, and network usage)

Good performance ensures that users experience the system as smooth and responsive.

## Scalability

Scalability describes how well a system can grow with increased demand. A scalable system can handle more users, more data, or more requests by adding more resources.

The two most common approaches are *Vertical Scaling* and *Horizontal Scaling*.

**Vertical Scaling:** Adding more power to an existing machine (bigger CPU, more RAM).

**Horizontal Scaling:** Adding more machines or service instances.

Scalability is about maintaining performance while demand increases. While scaling, the system will encounter bottlenecks along the way as a system's speed is dictated by its slowest component. Common bottlenecks are in the database, the network, disk access, and external dependencies such as another API or a payment service.

Identifying bottlenecks is a major part of performance analysis, and so working to keep these bottlenecks as visible as possible is a key part of a developer's job.

## Optimization Strategies

Many performance issues can be mitigated through:

- Caching frequently accessed data
- Query Optimization
- Load Balancing
- Asynchronous Processing
- Reducing unnecessary computation

We will expand on many of these concepts in our final presentations.

When optimizing your systems, this should be guided by profiling and measurement rather than guessing. 

**Load Testing:** Simulates real user traffic

**Stress Testing:** Pushes the system beyond its limits

**Monitoring & Observability:** Tracking metrics, logs, and traces in production