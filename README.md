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

        
