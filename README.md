# Backend System Design

I wanted to share with you my notes and thoughts after finishing the course ["Backend System Design"](https://frontendmasters.com/courses/backend-system-design/) from FrontendMasters.

## System Design Introduction

### Notes

A system is a group of components that work together in order to solve a problem. It has three main characteristics:

1. An input.
2. An output.
3. Boundaries. This point is very important because scoping a system prevents making it too big.

Distributed system helps to solve a complex problem by delegating different tasks to multiple computers. The main advantages are:

1. Provides more scaling options (horizontal scaling)
2. Increase fault tolerance.

Common system components:

- **Client.**. Makes requests and display information to final users.
- **Database.**. Stores information.
- **Server.** Process requests from clients.
- **Load balancers.** Distributes traffic across multiple computers.
- **Cache.**
  - Stores temporary data
  - Reduces latency

## Requirements

### Notes

Core elements of system design:

- Translate business requirements.
- Design API and architecture.
- Understanding technology and trade-offs.

Understanding the problem is very important. It’s common mistake to make assumptions about the system based on previous experiences, but that can lead to misunderstanding (solving the wrong problem).

We can classify requirements into two different ones:

1. **Functional requirements.** Describes what the system should do (e.g. Users should be able to change their password).
2. **Non-functional requirements.** Describes how the system should perform (e.g. The site should be accessible by screen readers).

#### CAP Theorem

The CAP Theorem core concept is based on three characteristics of the system:

- **Consistency.** Every request receives the most recent write.
- **Availability.** The system is operational and accessible.
- **Partition tolerance.** The

The golden is that a system can have only two of the three characteristics, but in reality we just have two possibilites, because we cannot ignore the partition tolerance as in a distributed system **errors will happen always**:

- **Consistency + Partition tolerance**
- **Availability + Partition tolerance**

As a programmer, you have to decide what is the most important for your system:

- Read latest data always (Consistency + Partition tolerance)
- Be always available (Availability + Partition tolerance)
