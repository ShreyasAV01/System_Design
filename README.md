# 🏗️ WEEK 1: Foundation & Core Concepts
🎯 Goal: Understand what system design is and key performance trade-offs.
Day	Topic	What to Learn / Cover

## 1.	System Design Overview	What is system design, HLD vs LLD, why interviews test it
IT basically means how you design a complete system - not just piece of code - that can handle scale, reliability, performance, maintainability <br />
HLD stands for high level design it focuses on the architecture of the system --big picture (Here We understand how the system’s major components interact)<br />
			🧱 Key Concepts<br />
				&emsp; Client-server architecture<br />
				&emsp; Databases (SQL vs NoSQL)<br />
				&emsp; Load balancers<br />
				&emsp; Caching layers<br />
				&emsp; Queues & pub/sub systems (Kafka, RabbitMQ)<br />
				&emsp; CDN (Content Delivery Network)<br />
				&emsp; Sharding, replication, consistency models	<br />
LLD stands for Low level design it focuses more on class-level/component-level design.  (Here we Convert HLD into detailed class diagrams and interactions)<br />
			🧩 Key Concepts<br />
				&emsp; Object-oriented design principles (SOLID)<br />
				&emsp; Design patterns (Singleton, Factory, Observer)<br />
				&emsp; Database schema design<br />
				&emsp; Detailed sequence diagrams<br />
   
| Criteria          | High-Level Design (HLD)           | Low-Level Design (LLD)                     |
|-------------------|-----------------------------------|--------------------------------------------|
| **Focus**         | Architecture & interaction between systems | Class design, internal logic          |
| **Granularity**   | Broad, component-level            | Detailed, method-level                     |
| **Audience**      | Architects, senior developers     | Developers, implementers                   |
| **Output**        | Architecture diagram, data flow   | UML, class & sequence diagrams             |
| **Example**       | Design Netflix                    | Design MovieRecommendationService class     |


## 2. Functional vs Non-functional requirements 
| Aspect            | Functional Requirements              | Non-Functional Requirements                  |
|-------------------|-------------------------------------|----------------------------------------------|
| **Definition**    | Define what the system should do     | Define how the system should perform         |
| **Focus**         | Features, actions, and processes     | Performance, quality, constraints            |
| **Visibility**    | Directly visible to end users        | Indirect, affects user experience            |
| **Measurability** | Easily tested via outputs            | Verified via metrics and benchmarks          |
| **Examples**      | Login, search, payment               | Security, speed, reliability                 |
| **Documentation** | Use cases, user stories              | Technical specs, service-level agreements    |


## 3. Networking Basics IP, DNS, and routing
IP		 -- Internet Protocol  	---  identifies what devices are communicating
DNS		 -- Domain Name System  ---  tells you where to go (via IP resolution)
Routing  	 -- routing 			---	 decides how to get there


| Component | Purpose | Example Function | Layer in OSI Model |
|------------|----------|------------------|--------------------|
| **IP** | Assigns unique numerical addresses to devices | Identifies source and destination nodes | Network layer |
| **DNS** | Translates domain names to IP addresses | Resolves www.example.com → 93.184.216.34 | Application layer |
| **Routing** | Decides the path data takes across networks | Forwards packets via routers to reach destination | Network layer |


## 4. TCP  ---   Transmission Control Protocol
connection-oriented protocol prioritizes reliability, making it ideal for tasks where accuracy is essential(line in banling and financial)  

## 5. UDP  ---   User Datagram Protocol
connectionless protocol emphasizes speed, best suited for real-time applications like streaming and online gaming.

| Feature               | TCP                                             | UDP                                             |
|-----------------------|-------------------------------------------------|-------------------------------------------------|
| **Type**              | Connection-oriented                             | Connectionless                                  |
| **Reliability**       | Reliable with error detection and retransmission| Unreliable with no retransmission               |
| **Order of Delivery** | Ensures ordered data                            | May arrive out of order                         |
| **Speed**             | Slower                                          | Faster                                          |
| **Header Size**       | 20–60 bytes (variable)                          | 8 bytes (fixed)                                 |
| **Handshake**         | SYN–SYN/ACK–ACK (3-way)                         | None                                            |
| **Use Cases**         | Web, email, file transfer<br />Commonly used by applications requiring high reliability like HTTP, HTTPS, FTP, SMTP, Telnet | Streaming, gaming, VoIP, DNS<br />Commonly used in DNS, DHCP, VoIP, gaming, streaming where speed matters |

## 6. Client-Server Model Overview
The client-server model is a distributed architecture where clients make requests to access data or perform operations, and servers process those requests and return responses.[synchronet](https://synchronet.net/client-server-model/)
Examples include:<br />
&emsp;•	Web browsers requesting web pages from a web server.<br />
&emsp;•	Mobile apps fetching data from cloud APIs.<br />
&emsp;•	Email clients communicating with mail servers.[ninjaone](https://www.ninjaone.com/it-hub/endpoint-management/what-is-client-server-architecture/)<br />

## 7. Requests and Responses
The client initiates communication:<br />
1.	The client sends a request—an HTTP message containing a method (GET, POST, PUT, DELETE), headers, and optionally a body.[toolsqa](https://toolsqa.com/client-server/client-server-architecture-and-model)<br />
2.	The server processes the request, often involving database queries or application logic.<br />
3.	The server sends a response, usually with a status code (e.g., 200 OK, 404 Not Found) and data in HTML or JSON format.[toolsqa](https://toolsqa.com/client-server/client-server-architecture-and-model)<br />
This follows a request–response communication loop central to all client-server architectures.[wikipedia](https://en.wikipedia.org/wiki/Client%E2%80%93server_model)<br />


## 8. Stateful vs Stateless Architectures
Servers can manage client interactions as stateful or stateless, affecting scalability and resource management.sjsu+1
| Feature             | Stateful                                                                   | Stateless                                                     |
|---------------------|----------------------------------------------------------------------------|---------------------------------------------------------------|
| **Definition**      | Server remembers clients and their session data [sjsu][1]                  | Server treats each request independently [sjsu][1]            |
| **Session Handling**| Uses session IDs or cookies to track interactions [sjsu][1]                | No session storage; client must send full info each time [sjsu][1]      |
| **Resource Usage**  | Higher—server must maintain memory per client [sjsu][1]                    | Lower—no client-specific data storage [sjsu][1]               |
| **Example**         | Online shopping carts, database transactions, SOAP [sjsu][1]               | RESTful APIs, web searches [sjsu][1]                          |
| **Reliability**     | Can resume interrupted workflows [sjsu][1]                                 | Easily scalable, but less context-aware [sjsu][1]             |

[1]: https://www.cs.sjsu.edu/~pearce/oom/ood/distArch/server.htm

## 9. REST gRPC and 
REST (Representational State Transfer) is a stateless architectural style for building web services that operate over HTTP. It uses resources (URLs) and standard HTTP verbs:<br />
&emsp;•	GET – Retrieve data<br />
&emsp;•	POST – Create new data<br />
&emsp;•	PUT – Update existing data<br />
&emsp;•	DELETE – Remove data[toolsqa](https://toolsqa.com/client-server/client-server-architecture-and-model)<br />
REST APIs allow interoperability between systems via lightweight, text-based communication, often returning JSON objects. They are central to modern web and mobile applications.[algomaster](https://blog.algomaster.io/p/client-server-architecture-explained)<br />

## TODO

## 10. understanding Latency, Throughput and Availability
Latency is the time it takes for a single operation or request to complete — from the client sending a request to receiving a response. It measures speed per request, often in milliseconds.[igotanoffer](https://igotanoffer.com/blogs/tech/latency-throughput-availability-system-design-interview)<br />
Examples:<br />
&emsp;	Web page loading time after clicking a link (e.g., 200 ms)<br />
&emsp;	Database query execution time (e.g., 10 ms)<br />
&emsp;	Packet delivery delay in a network (e.g., 50 ms)[substack](https://substack.com/home/post/p-158164046)<br />
Optimizing Latency:<br />
&emsp;	Reduce network hops or distance (use CDNs)<br />
&emsp;	Cache frequently accessed data<br />
&emsp;	Use faster storage and CPUs<br />
&emsp;	Optimize query execution path[sigotanoffer](https://igotanoffer.com/blogs/tech/latency-throughput-availability-system-design-interview)<br />


Throughput is the amount of work a system can perform per unit of time, often measured in requests per second (RPS), transactions per second (TPS), or megabytes per second. It reflects how well a system handles concurrent workloads.[linkedin](https://www.linkedin.com/top-content/business-strategy/scalable-system-design/understanding-system-design-tradeoffs/)
Examples:
&emsp;	A web server handling 10,000 requests/sec<br />
&emsp;	A database processing 2,000 queries/sec<br />
&emsp;	A streaming service serving 1 GB/sec [datasubstack](https://substack.com/home/post/p-158164046)<br />
Optimizing Throughput:<br />
&emsp;	Enable parallel processing or batch operations<br />
&emsp;	Scale horizontally (add more servers)<br />
&emsp;	Use asynchronous or queue-based processing<br />
&emsp;	Balance traffic across multiple nodes[linkedin](https://www.linkedin.com/top-content/business-strategy/scalable-system-design/understanding-system-design-tradeoffs/)<br />


Availability measures the percentage of time a system is operational and accessible, expressed as uptime ratio:
Availability=Uptime/(Uptime+Downtime)

It reflects system reliability and fault tolerance. For instance, 99.9% availability equals about 8.76 hours of downtime per year.[igotanoffer](https://igotanoffer.com/blogs/tech/latency-throughput-availability-system-design-interview)<br />
Improving Availability:<br />
&emsp;	Use load balancers and failover systems<br />
&emsp;	Deploy redundant servers (active-active clusters)<br />
&emsp;	Design disaster recovery and backup strategies<br />
&emsp;	Use monitoring tools with auto-healing workflowssystemdesign[school](https://systemdesignschool.io/primer)<br />
________________________________________________________________________________________________________________________________________________________________
Trade-offs: Speed, Concurrency, and Uptime<br />
Balancing latency, throughput, and availability is central to system design trade-offs.[designgurus](https://www.designgurus.io/blog/complex-system-design-tradeoffs)



        
