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
IP		 -- Internet Protocol  	---  identifies what devices are communicating<br />
DNS		 -- Domain Name System  ---  tells you where to go (via IP resolution)<br />
Routing  	 -- routing 			---	 decides how to get there<br />


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

## HTTP vs HTTPS
**HTTP (HyperText Transfer Protocol)** -- Data transferred in plain text, No encryption, but Vulnerable to middle attacks, Packet sniffing and Data tampering.<br />
&emsp;Client → Server<br />

System implications:<br />
&emsp;Faster (no encryption overhead)<br />
&emsp;Unsafe for production systems<br />
&emsp;Used mostly in: Internal systems and testing environments<br />

**HTTPS (HTTP Secure)** -- HTTP + TLS/SSL encryption, Data encrypted before transmission hence Provides Confidentiality, Integrity and Authentication.<br />
&emsp;Client → TLS Handshake → Secure Channel → Server<br />

&emsp;Extra steps:<br />
&emsp;Certificate verification<br />
&emsp;Key exchange<br />
&emsp;Encryption setup<br />
System implications:<br />
&emsp;More secure<br />
&emsp;Slightly more complex<br /> 
&emsp;Industry standard for public systems.<br />

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
Servers can manage client interactions as stateful or stateless, affecting scalability and resource management.
| Feature             | Stateful                                                                   | Stateless                                                     |
|---------------------|----------------------------------------------------------------------------|---------------------------------------------------------------|
| **Definition**      | Server remembers clients and their session data [sjsu][1]                  | Server treats each request independently [sjsu][1]            |
| **Session Handling**| Uses session IDs or cookies to track interactions [sjsu][1]                | No session storage; client must send full info each time [sjsu][1]      |
| **Resource Usage**  | Higher—server must maintain memory per client [sjsu][1]                    | Lower—no client-specific data storage [sjsu][1]               |
| **Example**         | Online shopping carts, database transactions, SOAP [sjsu][1]               | RESTful APIs, web searches [sjsu][1]                          |
| **Reliability**     | Can resume interrupted workflows [sjsu][1]                                 | Easily scalable, but less context-aware [sjsu][1]             |

[1]: https://www.cs.sjsu.edu/~pearce/oom/ood/distArch/server.htm

## 9. REST gRPC and JSON
REST (Representational State Transfer) is a stateless architectural style for building web services that operate over HTTP. It uses resources (URLs) and standard HTTP verbs:<br />
&emsp;•	GET – Retrieve data<br />
&emsp;•	POST – Create new data<br />
&emsp;•	PUT – Update existing data<br />
&emsp;•	DELETE – Remove data[toolsqa](https://toolsqa.com/client-server/client-server-architecture-and-model)<br />
REST APIs allow interoperability between systems via lightweight, text-based communication, often returning JSON objects. They are central to modern web and mobile applications.[algomaster](https://blog.algomaster.io/p/client-server-architecture-explained)<br />

**Example System Design Without REST**  		<br />
		**Mobile app → custom TCP protocol → server** <br />
**Problems:** <br />
&emsp;• Hard to maintain<br />
&emsp;• Not scalable<br />
&emsp;• Not standard<br />
&emsp;• Tight coupling<br />

**With REST**			<br />
			**Client → HTTP REST API → Service → Database** <br />
**Benefits:** <br />
&emsp;• Standard protocol<br />
&emsp;• Language independent<br />
&emsp;• Easy scaling<br />
&emsp;• Stateless<br />
&emsp;• Cacheable<br />

⭐ Core REST Principles<br />
1️⃣ Client–Server Separation

				Client → UI
				Server → Logic + Data
				
System impact:<br />
&emsp;• Independent scaling<br />
&emsp;• Separate deployment<br />
&emsp;• Better maintainability<br />

2️⃣ Stateless Communication <br />
Every request contains all required information, Server stores no client session.<br />

Request 1 → independent
Request 2 → independent

Benefits:<br />
&emsp;• Easy horizontal scaling<br />
&emsp;• No session synchronization<br />
&emsp;• Load balancer friendly<br />
&emsp;• Fault tolerant<br />

👉 This is why REST is widely used in distributed systems.<br />

3️⃣ Resource-Based Design<br />
Everything is a resource.<br />
/users<br />
/orders<br />
/products<br />
| Operation | HTTP Method |
| --------- | ----------- |
| Read      | GET         |
| Create    | POST        |
| Update    | PUT / PATCH |
| Delete    | DELETE      |


4️⃣ Uniform Interface<br />
Standard API design:<br />

GET /users/101<br />
POST /orders<br />

System impact:<br />
&emsp;• Predictable APIs<br />
&emsp;• Easier integrations<br />
&emsp;• Faster development<br />

5️⃣ Cacheable Responses<br />
Server can mark responses cacheable.<br /> 
Cache-Control: max-age=3600<br />

System design benefits:<br />
&emsp;• Reduced server load<br />
&emsp;• Better performance<br />
&emsp;• Lower latency<br />
Used heavily by: CDNs, Edge systems, Large-scale platforms<br />

6️⃣ Layered System Architecture<br />
Client doesn’t know if request goes through:<br />
Client → CDN → Gateway → Load Balancer → Service<br />

System impact:<br />
&emsp;• Security layers<br />
&emsp;• Scalability layers<br />
&emsp;• Observability layers<br />

📦 What is JSON?<br />
✅ JSON = Data Format (Not Architecture)<br />
JSON (JavaScript Object Notation) is a lightweight format for exchanging data between systems.<br />
Why JSON Is Used in System Design<br />
✔ Lightweight  --> Small payload → faster network transfer.<br />
✔ Human readable --> Easy debugging.<br />
✔ Language independent --> Works with Java, Python, JS, Go, etc.<br />
✔ Easy parsing --> Built-in libraries everywhere.<br />

🤝 How REST + JSON Work Together<br />
Typical Flow<br />

Client → REST API request<br />
Server → returns JSON response<br />
⚡ System Design Tradeoffs of REST + JSON<br />

Advantages<br />
&emsp;• Simple<br />
&emsp;• Scalable<br />
&emsp;• Stateless<br />
&emsp;• Easy integration<br />
&emsp;• Widely supported<br />

Limitations (Interview Bonus Points)<br />
❌ JSON size larger than binary protocols → More bandwidth.<br />
❌ Multiple requests for related data → Over-fetching / under-fetching (Why GraphQL exists.)<br />
❌ No strict schema by default → Validation needed.<br />


## ⭐ 1️⃣ Idempotency<br />
An operation is idempotent if performing it multiple times produces the same result as performing it once.<br />

1 request → same result
10 same requests → same result

No side effects from retries.<br />

🧠 Why Idempotency Exists (System Design Problem)<br />
In distributed systems:<br />
&emsp;• Network failures happen<br />
&emsp;• Timeouts occur<br />
&emsp;• Clients retry requests<br />
&emsp;• Messages may be duplicated<br />

Without idempotency → duplicate operations<br />

🏗️ How Systems Implement Idempotency<br />
1️⃣ Idempotency Keys (Most Common)<br />
Client sends unique request ID<br />
Idempotency-Key: payment-123<br />
Server:<br />
stores key + response<br />
ignores duplicates<br />
Used by companies like:<br />
→ Stripe payment APIs.<br />

2️⃣ Unique Constraints in Database<br />
Example:<br />
order_id UNIQUE<br />
Duplicate inserts fail safely.<br />

3️⃣ Upsert Operations<br />
Insert or update if exists<br />
Used in:<br />
caching<br />
user profile updates<br />

4️⃣ HTTP Method Design<br />
Some HTTP methods are naturally idempotent:<br />

| Method | Idempotent? |
| ------ | ----------- |
| GET    | ✅ Yes       |
| PUT    | ✅ Yes       |
| DELETE | ✅ Yes       |
| POST   | ❌ No        |

🏢 Where Idempotency is Critical<br />
Payments<br />
Order creation<br />
Banking systems<br />
Distributed messaging<br />
Event processing<br />
Retry mechanisms<br />
Microservices communication<br />


## ⭐ 2️⃣ Rate Limiting<br />
Limiting how many requests a client can make in a time period.<br />
eg: 100 requests per minute per user<br />

Without rate limiting:<br />
&emsp;• Server overload<br />
&emsp;• DDoS attacks<br />
&emsp;• API abuse<br />
&emsp;• Resource starvation<br />
&emsp;• Unfair usage<br />


🏗️ Where Rate Limiting Happens in Architecture<br />
Client
  ↓
API Gateway (rate limit)
  ↓
Service

Usually implemented at:<br />
API gateway<br />
Load balancer<br />
Edge/CDN<br />
Reverse proxy<br />

⚙️ Rate Limiting Algorithms <br />
1️⃣ Token Bucket (Most Common)<br />
Tokens added at fixed rate<br />
Request consumes token<br />
No token → reject<br />

2️⃣ Fixed Window Counter<br />
100 requests per minute<br />

Simple but burst issues at window boundaries.<br />

3️⃣ Sliding Window<br />
More accurate rate tracking.<br />
Used in high-scale systems.<br />

4️⃣ Leaky Bucket<br />
Requests processed at fixed rate.<br />
Smooths traffic.<br />


Response When Limit Exceeded --> HTTP 429 Too Many Requests --> Retry-After: 60<br />

🏢 Where Rate Limiting Is Used<br />
&emsp;• Login APIs<br />
&emsp;• Payment APIs<br />
&emsp;• Public APIs<br />
&emsp;• Search services<br />
&emsp;• OTP systems<br />
&emsp;• Messaging services<br />




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


| Trade-off                | Description                                                                                                         | Real-World Example                                                                                                                                                        |
|--------------------------|---------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Latency vs Throughput** | Lower latency (faster responses) often reduces total throughput because systems keep slack or idle capacity to respond instantly. High throughput (batch jobs) can increase latency since tasks queue up. | Real-time trading (low latency) vs batch data analytics (high throughput) [danslimmon][1]                                          |
| **Throughput vs Availability** | Scaling for high throughput increases complexity—more nodes mean more failure points, potentially lowering availability unless redundancy is built in. | Large-scale streaming platforms (YouTube, Netflix) balance redundancy to maintain uptime [linkedin][2]                              |
| **Latency vs Availability** | Adding fault tolerance (replication, quorum reads) can increase latency due to coordination overhead.              | Distributed databases like Cassandra or MongoDB trade some delay for higher uptime [igotanoffer][3]                                 |

[1]: https://blog.danslimmon.com/2019/02/26/the-latency-throughput-tradeoff-why-fast-services-are-slow-and-vice-versa/
[2]: https://www.linkedin.com/top-content/business-strategy/scalable-system-design/understanding-system-design-tradeoffs/
[3]: https://igotanoffer.com/blogs/tech/latency-throughput-availability-system-design-interview

Summary
&emsp;•	Latency = Time per operation (speed)<br />
&emsp;•	Throughput = Operations per second (concurrency)<br />
&emsp;•	Availability = Uptime percentage (reliability)<br />
In real-world systems, improving one often comes at the cost of another — a high-throughput, highly available system might have slightly higher latency, while a low-latency one might sacrifice concurrency or fault tolerance. The optimal design depends on the system’s business goals — for instance, stock trading prioritizes latency, while e-commerce prioritizes availability and throughput.[designgurus]()

Example:<br />
&emsp;•	Suppose a web server can handle 1,000 concurrent requests, but you only allow 200 active at a time to ensure each responds fast (say, within 100 ms).<br />
&emsp;•	Most CPU cores remain free for sudden traffic spikes.<br />
&emsp;•	Result: Each request is fast (low latency), but overall you’re processing fewer total requests per second (lower throughput).<br />

## 11. Scalability
Scalability is the ability of a system to handle increasing workloads by adding resources — either by improving existing hardware or by distributing the load across multiple systems. It ensures your system performs efficiently as user demand or data volume grows.[geeksforgeeks](https://www.geeksforgeeks.org/system-design/what-is-scalability/)

## Vertical vs Horizontal Scaling
| Aspect         | Vertical Scaling (Scale Up)                                      | Horizontal Scaling (Scale Out)                                                |
|----------------|------------------------------------------------------------------|-------------------------------------------------------------------------------|
| **Definition** | Increase power (CPU, RAM, storage) of a single server            | Add more servers or nodes to distribute the workload [geeksforgeeks][1]       |
| **Example**    | Upgrading a 4-core CPU to 32 cores                               | Adding more identical servers behind a load balancer [geeksforgeeks][1]       |
| **Limitations**| Hardware ceiling — can’t scale infinitely                        | Software complexity — needs distributed architecture [pingcap][2]             |
| **Fault Tolerance** | Single point of failure                                     | High, since load is distributed [geeksforgeeks][1]                            |
| **Cost**       | Higher for premium hardware                                      | Cost-effective long-term using commodity hardware [aerospike][3]              |
| **Downtime**   | Usually requires restart                                         | Often zero downtime with rolling updates [pingcap][2]                         |
| **Use Case**   | Databases, monolithic apps                                      | Cloud-native, microservices, and large-scale web apps [aerospike][3]          |

[1]: https://www.geeksforgeeks.org/system-design/system-design-horizontal-and-vertical-scaling/
[2]: https://www.pingcap.com/horizontal-scaling-vs-vertical-scaling/
[3]: https://aerospike.com/blog/vertical-vs-horizontal-scaling/

## Bottlenecks in Scalability<br />
A bottleneck is a system component that limits overall performance as load increases. Even if other parts scale, a single slow component constrains the system’s capacity.[statsig](https://www.statsig.com/perspectives/designing-for-scalability-principles)
Common bottlenecks:<br />
&emsp;•	CPU/Memory limits on specific nodes in vertical scaling.<br />
&emsp;•	Database throughput — the database can’t handle all incoming requests.<br />
&emsp;•	Network latency or bandwidth when nodes communicate frequently.<br />
&emsp;•	Disk I/O slowness for large read/write workloads.<br />
&emsp;•	Locking or contention in shared resources (e.g., global session manager or cache).<br />
To mitigate bottlenecks:<br />
&emsp;•	Use load balancers to distribute traffic.<br />
&emsp;•	Implement caching near users (CDNs) or near data (Redis).<br />
&emsp;•	Apply sharding to partition data horizontally.<br />
&emsp;•	Design stateless services for independent scaling.[linkedin](https://www.linkedin.com/pulse/system-design-key-concepts-scalability-saeed-anabtawi--1g0pf)<br />

## ⭐ 2️⃣ Load Balancing (Traffic Distribution)<br />
Load balancing distributes incoming requests across multiple servers to prevent overload.<br />

Users
  ↓
Load Balancer
  ↓
Server 1
Server 2
Server 3

**⚙️ Load Balancing Algorithms** <br />
1️⃣ Round Robin (Most Basic)<br />
Req1 → Server1<br />
Req2 → Server2<br />
Req3 → Server3<br />
Req4 → Server1<br />

Pros<br />
&emsp;•	Simple<br />
&emsp;•	Equal distribution<br />

Cons<br />
&emsp;•	Doesn’t consider server capacity.<br />

2️⃣ Least Connections<br />
Send request to server with fewer active connections.<br />
Better for uneven workloads.<br />

3️⃣ IP Hash<br />
Same client IP → same server<br />
Used when session consistency required.<br />

4️⃣ Weighted Load Balancing<br />
Servers with higher capacity get more traffic.<br />
Powerful server → more requests<br />


**🏗️ Types of Load Balancers (Architecture Level)** <br />
1️⃣ Layer 4 Load Balancer (Transport Level)<br />
Works using:<br />
&emsp;•	IP address<br />
&emsp;•	TCP/UDP ports<br />
Fast but less intelligent.<br />

2️⃣ Layer 7 Load Balancer (Application Level)<br />
Works using:<br />
&emsp;•	URL<br />
&emsp;•	Headers<br />
&emsp;•	Cookies<br />

Can route:<br />
/images → image server<br />
/api → API server      <br />

Used in modern architectures.<br />
