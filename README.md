# Backend System Design

I wanted to share with you my notes and thoughts after finishing the course ["Backend System Design"](https://frontendmasters.com/courses/backend-system-design/) from FrontendMasters.

## System Design Introduction

A system is a group of components that work together in order to solve a problem. It has three main characteristics:

1. An input.
2. An output.
3. Boundaries. This point is very important because scoping a system prevents making it too big.

Distributed system helps to solve a complex problem by delegating different tasks to multiple computers. The main advantages are:

1. Provides more scaling options (horizontal scaling)
2. Increase fault tolerance.

### Common system components

- **Client.**. Makes requests and display information to final users.
- **Database.**. Stores information.
- **Server.** Process requests from clients.
- **Load balancers.** Distributes traffic across multiple computers.
- **Cache.**
  - Stores temporary data
  - Reduces latency

## Gathering Requirements

### Core elements of system design

- Translate business requirements.
- Design API and architecture.
- Understanding technology and trade-offs.

Understanding the problem is very important. It’s common mistake to make assumptions about the system based on previous experiences, but that can lead to misunderstanding (solving the wrong problem).

We can classify requirements into two different ones:

1. **Functional requirements.** Describes what the system should do (e.g. Users should be able to change their password).
2. **Non-functional requirements.** Describes how the system should perform (e.g. The site should be accessible by screen readers).

### What is the CAP Theorem?

The CAP Theorem core concept is based on three characteristics of the system:

- **Consistency.** Every request to the system receives the most recent write.
- **Availability.** The proportion of time a system is operational and accessible.
- **Partition tolerance.** The system continues to work even if messages are delayed or lost.

The golden rule is that any distributed system can have only two of the three characteristics:

- **Consistency + Availability:**: It always works if there are not network issues. That is not very realistic on a distributed system, as network can always fail.
- **Consistency + Partition tolerance:** It always show the latest data, but with an unreliable performance.
- **Availability + Partition tolerance:** It always responds, but data could shown can be outdated.

### Quality indicators of your system

- **Reliability.** System works as expected over time.
- **Observability.** Ability to know what is happening in your system.
- **Scalability.** How your system scales up and down.
  - **Vertical scaling**: Increasing hardware capabilities. It's easier than horizontal scaling but it has some limitations, like phisical walls.
  - **Horizontal scaling**: Increasing the amount of computers in your system. It does not have phisical limitations as vertical scaling, but increases the system's complexity. To get the results we expect, we need to orchestrate machines to cooperate. **Load balancers** are an important piece when scaling horizontally, as they are design to distribute traffic across multiple server.
- **Security.** Ability to safeguard your system and its data.
- **Availability:** Ability to handle changing requirements on your system.
- **Performance.**
  - Latency: How quick your system responds (usually a good measure is how long it takes to get the response for a request).
  - Throughput: Amount of data that your system can move at a given time. Requests Per Second (RPS) is a an example of a throughput measurement.

### Modelling ordering

1. Gather requirements (functional and not-functional)
2. Entity modelling.
3. API design.
   - HTTP
   - Websockets
   - Server-Sent Events.
   - gRPC
   - REST
   - GraphQL
4. Endpoints.
5. Optimizations.

## Resources

Besides the course I already mentioned above, I also gather information from the following resources:

[Difference between latency and throughput](https://www.geeksforgeeks.org/computer-networks/difference-between-latency-and-throughput/)
