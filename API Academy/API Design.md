# Module 1
An API is a software interface, a building block that works behind the scenes to connect different applications and systems so they can share information.

## Business Benefits of APIs
- New Revenue
- Reach and Retention
- Faster Partnerships
- Mobile and Omnichannel
- Interaction Analysis

# Module 2 : The API 360 Model

![[Pasted image 20231205095851.png]]


# Module 3 : API Styles

## Styles vs Standards
**Standards** are usually formal documents that establish uniform engineering or technical criteria, methods, processes, and practices.
**Styles** refer to abstract plans or conventions for the construction of an object or a system, such as architectural blueprints, engineering drawings or business processes.

## API Styles

- Tunnel Style (SOAP)
- URI Style (CRUD)
- Hypermedia Style (REST)
- Event-driven style (Reactive)

## Tunnel Style : SOAP (Simple Object Access Protocol)
- also known as Web Service Style
- Exposes an RPC-like interface and provides an interface descriptor for binding
- Uses an XML-centric message format
- Uses HTTP as a transport protocol for a higher application-level protocol

### Common Implementation Model
- Focus on the Functions/Methods
- Build a component (DLL, Assembly, etc.)
- Expose functions and args via WSDL
- Publish WSDL (direct, UDDI, etc.)
- Code generate proxy class via WSDL
- Use proxy class in client

### Advantages
- Continues RPC line (Corba, COM/DCOM, etc.)
- Good "tooling" for publishers & consumers
- Strong governance model for enterprises

### Limitations
- "Stack dependencies" (all or nothing)
- XML-centric implementation
- Ignores HTTP features (caching, etc.)
- Loss in popularity

---

## URI Style: CRUD (Create Read Update Delete)
- An object or resource-centric API is exposed
- URIs and query parameters are used to identify and filter objects
- CRUD (create, read, update, delete) operations are mapped to HTTP methods

### Common Implementation Model
- Focus on Objects/ Entities
- Design public identifiers (URIs)
- Design query rules
- Use HTTP methods as operations on entities
- Server serializes internal objects
- Clients use URIs to pass objects

### Advantages
- HTTP path & query is "well known"
- Object "tooling" is good
- "hacking" is relatively easy

### Limitations
- URI modeling is not standard
- HTTP method set is very small
- May become "chatty"

---

## Hypermedia Style: REST (Representational State Transfer)
- Exposes a task-based interface, often incorporating a workflow or state machine
- Uses media to describe link semantics, template-based input and message structures
- Provides its own URIs

### Common Implementation Model
- Focus on the Tasks/Use Cases
- Select Media Type(s)
- Match Tasks to forms/links
- Server translates internal storage to media types
- Client uses links/forms in responses
### Advantages
- Media Types can be customized
- Growing body of guidance
- Favors services that will last many years
### Limitations
- Poor "tooling"
- Assumed to be "too hard"
- Limited use in public APIs

---

## Event-Driven Style : Reactive
- Emphasis on event notifications
- Asynchronous communication, "Reactive"
- Emerging Style
	- HTTP- based technologies: `webhooks` , `websockets`
	- Non-HTTP technologies: Apache Kafka, AMQP
- Popular with Domain-Driven Design(DDD), Command Query Responsibility (CQRS), Microservices

---

## GraphQL and gRPC

### GraphQL
- Query language for APIs
- Originated at Facebook
- Intended for flexibility of arguments

### gRPC
- HTTP2-based protocol
- Originated at Google
- Intended for high scale communication


# Module 4 : Designing API for Developers

## What is Good Design?
The principles of functionality, usability and experience state that a good design must not only have a purpose, but should be easily leveraged and address the human experience.

# Module 5 : Overcoming API Design Obstacles

## Common Challenges in API Design
### Cost
From Managing multiple gateway servers and instances to building an entire API management program from the ground up, the wrong infrastructure approach can lead to unnecessary and unwieldy expenses
### Scalability
Addressing scalability early on in the process can help define early adoption, future success, and the lifespan of the API.
### Security
Security should be incorporated at the infrastructure level. You'll need a multi-pronged approach that includes leveraging an API gateway to easily validate, authorize and control the access of legitimate API consumers, as well as protect endpoints against malicious traffic.

## API Design Obstacles
Some obstacles that an API designer may face during the design process:
- The perspective obstacle
- The bias obstacle
- The assumptions obstacle
- The resource obstacle

# Module 6 : Architecting your API

## What is API Architecture?
The process of developing a software interface that exposes backend data and application functionality for use in new applications.

## Requirements of a Well-Designed API
- Security - the API is protected against attack and misuse
- Usability - the API is easy for developers to effectively leverage
- Scalability - the API is able to handle rapid spikes in traffic
- Testability - The API is designed to help developers experiment with functionality
- Reliability - The API is robust enough to minimize downtime

## Layered Architecture Style
Dividing the API architecture into layers simplifies the process of interface design. Each quality is abstracted away from API implementation and handled in a centralized server architecture, which can be used across multiple interfaces.
- Security Layer
- Caching Layer
- Representation Layer
- Orchestration Layer

## Steps of Basic API Design Approach
- Determine Goals
- Identify Users
- Design Interface
- Evaluate
- Implement

# Module 7 : API Change Management
