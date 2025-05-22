---

---
# [[01. Intro]]
1. **Q**: Define a distributed system.  
    **A**: A system with multiple independent nodes that communicate to achieve a common goal (e.g., cloud computing).
    
2. **Q**: Name three characteristics of distributed systems.  
    **A**: Transparency, scalability, fault tolerance.
    
3. **Q**: What is the difference between horizontal and vertical scaling?  
    **A**: Horizontal scaling adds more nodes; vertical scaling upgrades existing nodes’ resources (CPU, RAM).
    
4. **Q**: Explain the CAP Theorem.  
    **A**: A distributed system can guarantee only two of Consistency, Availability, and Partition Tolerance.
    
5. **Q**: What is eventual consistency?  
    **A**: Nodes may temporarily show different data but will eventually converge to the same state.
    
6. **Q**: How does Lamport’s Logical Clock address clock drift?  
    **A**: It uses logical timestamps to order events without relying on physical clocks.
    
7. **Q**: Give two examples of consensus algorithms.  
    **A**: Paxos and Raft.
    
8. **Q**: What is the role of replication in fault tolerance?  
    **A**: It ensures data redundancy, allowing the system to recover from node failures.
    
9. **Q**: Name two protocols used in distributed systems.  
    **A**: TCP/IP (reliable) and UDP (fast).
    
10. **Q**: What is the purpose of RPC?  
    **A**: To allow a client to request a task execution on a remote server.
    
11. **Q**: List three real-world distributed systems.  
    **A**: AWS, Hadoop HDFS, Blockchain.
    
12. **Q**: How does a CDN work?  
    **A**: It distributes content across geographically dispersed servers to reduce latency.
    
13. **Q**: What is network partitioning?  
    **A**: A scenario where nodes in a distributed system become disconnected.
    
14. **Q**: What is the master-slave architecture in GFS?  
    **A**: A central master node manages metadata, while slave nodes store data blocks.
    
15. **Q**: Why is heterogeneity a challenge in distributed systems?  
    **A**: Diverse hardware/software components complicate interoperability.
    
16. **Q**: What is the difference between strong and eventual consistency?  
    **A**: Strong consistency ensures immediate uniformity; eventual consistency allows temporary discrepancies.
    
17. **Q**: How does blockchain achieve decentralization?  
    **A**: By distributing ledger data across all nodes, eliminating a central authority.
    
18. **Q**: What is load balancing?  
    **A**: Distributing tasks across nodes to prevent overload on any single node.
    
19. **Q**: Name two security threats in distributed systems.  
    **A**: Man-in-the-middle attacks, denial-of-service (DoS).
    
20. **Q**: What is clock drift, and how is it mitigated?  
    **A**: Clocks in different nodes desynchronize over time; mitigated via NTP or logical clocks.
# [[02. Charasteristics]]
1. **Q**: What is heterogeneity in distributed systems?  
    **A**: Diversity in hardware, software, networks, and protocols (e.g., IoT devices and HTTP/Bluetooth coexistence).
    
2. **Q**: Name two solutions to address network heterogeneity.  
    **A**: Protocol converters (e.g., HTTP to MQTT) and adaptive caching techniques.
    
3. **Q**: How does horizontal scaling differ from vertical scaling?  
    **A**: Horizontal scaling adds nodes (e.g., AWS instances), while vertical scaling upgrades existing nodes (e.g., adding RAM).
    
4. **Q**: What is a key challenge in achieving openness in distributed systems?  
    **A**: Security risks due to exposed interfaces (e.g., vulnerabilities in open APIs).
    
5. **Q**: Explain the role of middleware in addressing heterogeneity.  
    **A**: Middleware (e.g., Docker) abstracts differences between components, enabling seamless communication.
    
6. **Q**: What is concurrency transparency?  
    **A**: Allowing multiple users to access shared resources without conflicts (e.g., databases handling concurrent transactions).
    
7. **Q**: List two concurrency control mechanisms.  
    **A**: Locks/mutexes and optimistic concurrency control.
    
8. **Q**: How does a CDN achieve geographical scalability?  
    **A**: By distributing content across globally dispersed servers (e.g., Cloudflare reducing latency).
    
9. **Q**: What is a Byzantine failure?  
    **A**: A node behaving maliciously or arbitrarily (e.g., sending incorrect data).
    
10. **Q**: How does the Raft algorithm contribute to fault tolerance?  
    **A**: It ensures consensus among nodes during failures (e.g., leader election and log replication).
    
11. **Q**: What is the purpose of a digital signature in security?  
    **A**: Ensures data authenticity and non-repudiation (e.g., verifying sender identity).
    
12. **Q**: What is a replay attack, and how is it mitigated?  
    **A**: Reusing intercepted messages; mitigated via timestamps and nonces.
    
13. **Q**: Define location transparency with an example.  
    **A**: Users unaware of resource location (e.g., accessing files on Google Drive without knowing server locations).
    
14. **Q**: What is the role of TLS in distributed systems?  
    **A**: Encrypts data during transmission (e.g., securing HTTP traffic as HTTPS).
    
15. **Q**: How does a load balancer improve scalability?  
    **A**: Distributes traffic across nodes to prevent overload (e.g., Nginx managing web server requests).
    
16. **Q**: What is eventual consistency? Provide an example.  
    **A**: Temporary data inconsistencies resolved over time (e.g., NoSQL databases like Cassandra).
    
17. **Q**: Name two types of transparency in distributed systems.  
    **A**: Access transparency and replication transparency.
    
18. **Q**: What is a deadlock in concurrency?  
    **A**: A state where processes wait indefinitely for resources (e.g., circular dependencies).
    
19. **Q**: How does OAuth enhance security?  
    **A**: Enables secure third-party authentication (e.g., logging into apps via Google/Facebook).
    
20. **Q**: What is the purpose of checkpointing in fault tolerance?  
    **A**: Periodically saving system state to enable recovery (e.g., database transaction logs).
# [[03. Communication]]
1. **Q**: What are the components of a communication system?  
    **A**: Source, transmitter, channel, receiver, destination.
    
2. **Q**: Contrast TCP and UDP protocols.  
    **A**: TCP is reliable and ordered (e.g., HTTP); UDP is fast but unreliable (e.g., live streaming).
    
3. **Q**: What is idempotency in communication semantics?  
    **A**: Processing duplicate messages has the same effect as one (e.g., retrying payments).
    
4. **Q**: Name two middleware examples and their uses.  
    **A**: Kafka (event streaming), gRPC (remote procedure calls).
    
5. **Q**: How does asynchronous communication benefit distributed systems?  
    **A**: Non-blocking operations improve responsiveness (e.g., email sending).
    
6. **Q**: Explain the "exactly-once" delivery semantic.  
    **A**: Messages are delivered once without duplicates (e.g., banking transactions).
    
7. **Q**: What role do event brokers play in distributed systems?  
    **A**: Route and manage events between producers/consumers (e.g., Kafka).
    
8. **Q**: Why is QoS critical for video conferencing?  
    **A**: Minimizes latency/jitter for real-time interaction.
    
9. **Q**: What is the purpose of RMI in Java?  
    **A**: Invoke methods on remote JVM objects (Java-specific RPC).
    
10. **Q**: How does middleware handle heterogeneity?  
    **A**: Abstracts differences in hardware/software (e.g., Docker containers).
    
11. **Q**: What is jitter in QoS parameters?  
    **A**: Variability in packet arrival times (affects real-time apps).
    
12. **Q**: Describe the shared memory communication model.  
    **A**: Processes access common memory (e.g., multi-core CPU threads).
    
13. **Q**: What is traffic shaping in QoS?  
    **A**: Controls data flow to prevent congestion (e.g., limiting P2P traffic).
    
14. **Q**: How does MOM ensure reliable message delivery?  
    **A**: Persistence, retries, and acknowledgments (e.g., RabbitMQ).
    
15. **Q**: What are the benefits of event-driven architecture?  
    **A**: Scalability, loose coupling, real-time processing.
    
16. **Q**: Why is SCTP used in VoIP?  
    **A**: Supports multi-streaming and reliability for voice/data.
    
17. **Q**: Define IPC and its role in distributed systems.  
    **A**: Inter-Process Communication enables data exchange between processes (local/remote).
    
18. **Q**: How does blockchain enhance communication security?  
    **A**: Decentralized, immutable ledger with cryptographic integrity.
    
19. **Q**: What is the role of a transmitter in a communication system?  
    **A**: Converts messages into transmittable signals (e.g., modem).
    
20. **Q**: Name two future trends in distributed communication.  
    **A**: 5G edge computing, AI-driven network optimization.
# [[04. File and Name Services]]
1. **Q**: What is the role of the NameNode in HDFS?  
    **A**: Maps file names to block locations stored on DataNodes.
    
2. **Q**: Contrast strong and eventual consistency.  
    **A**: Strong consistency ensures immediate uniformity; eventual consistency allows temporary discrepancies resolved over time.
    
3. **Q**: How does GFS ensure fault tolerance?  
    **A**: Replicates data chunks across multiple servers.
    
4. **Q**: What is the purpose of the UFID in a file system?  
    **A**: A unique identifier used to reference files in flat file service operations.
    
5. **Q**: Name two challenges in distributed file systems.  
    **A**: Data consistency, network latency, security.
    
6. **Q**: Explain the WORM model in HDFS.  
    **A**: Write Once, Read Many; files are immutable after creation.
    
7. **Q**: What is hierarchical name resolution?  
    **A**: Resolving names step-by-step through a structured hierarchy (e.g., DNS).
    
8. **Q**: How does iterative DNS resolution reduce load on root servers?  
    **A**: Root servers provide referrals, not final answers, distributing the query load.
    
9. **Q**: What is the role of a CORBA Naming Service?  
    **A**: Maps object names to remote object references in distributed systems.
    
10. **Q**: Why is concurrency important in DFS?  
    **A**: Allows multiple users/processes to access/modify files simultaneously without conflicts.
    
11. **Q**: What is location transparency in DFS?  
    **A**: Users access files without knowing their physical location.
    
12. **Q**: Name two advantages of recursive DNS resolution.  
    **A**: Faster client responses, reduced root server load, centralized caching.
    
13. **Q**: How does HDFS handle large files?  
    **A**: Splits files into blocks (e.g., 128MB) distributed across DataNodes.
    
14. **Q**: What is the role of the master node in GFS?  
    **A**: Manages metadata (file-to-chunk mapping) and coordinates chunk servers.
    
15. **Q**: What is a key difference between NFS and HDFS?  
    **A**: NFS is for general network file access; HDFS is optimized for big data with replication.
    
16. **Q**: How does DNS ensure scalability?  
    **A**: Hierarchical structure, partitioning, caching, and replication.
    
17. **Q**: What is the purpose of checkpointing in fault tolerance?  
    **A**: Periodically saves system state to enable recovery after failures.
    
18. **Q**: Why is eventual consistency used in systems like HDFS?  
    **A**: Balances performance and availability in large-scale distributed environments.
    
19. **Q**: What is the difference between iterative and recursive DNS queries?  
    **A**: Iterative: client/resolver handles referrals; Recursive: resolver handles all steps.
    
20. **Q**: How does replication improve DFS reliability?  
    **A**: Data copies ensure availability even if some nodes fail.
# [[07. Transaction]]
### 🔸 **1. Define a transaction and explain its ACID properties.**

**Answer:**  
A transaction is a sequence of operations that performs a single logical unit of work and must be fully completed or fully aborted.  
**ACID Properties:**

- **Atomicity**: All or none of the operations execute.
    
- **Consistency**: System moves from one valid state to another.
    
- **Isolation**: Concurrent transactions do not interfere.
    
- **Durability**: Committed changes persist despite crashes.
    

---

### 🔸 **2. What is the role of the Coordinator in distributed transactions?**

**Answer:**  
The Coordinator manages distributed transactions by assigning a unique transaction ID (`openTransaction()`), deciding to commit or abort (`closeTransaction()`), and issuing aborts when necessary (`abortTransaction()`).

---

### 🔸 **3. Differentiate between strict and regular two-phase locking.**

**Answer:**

- **Regular 2PL**: Locks are acquired in the growing phase and released in the shrinking phase.
    
- **Strict 2PL**: Locks are held until the transaction commits or aborts, preventing dirty reads and premature writes.
    

---

### 🔸 **4. Explain “dirty read” with an example.**

**Answer:**  
A dirty read occurs when one transaction reads data written by another uncommitted transaction.  
**Example**:  
T1 sets balance to $110 but then aborts. T2 reads $110 and commits—T2’s state is now invalid.

---

### 🔸 **5. What causes a cascading abort?**

**Answer:**  
If one transaction aborts and other transactions have read its uncommitted changes, they must also abort. This chain reaction is called a cascading abort.

---

### 🔸 **6. Why is serial equivalence important in concurrency control?**

**Answer:**  
It ensures that the concurrent execution of transactions is equivalent to some serial order, preserving consistency and correctness.

---

### 🔸 **7. Compare optimistic concurrency control and locking.**

**Answer:**

- **Optimistic**: Transactions proceed freely and check for conflicts at commit time; better for low-conflict environments.
    
- **Locking**: Controls access to objects using locks during execution; better for high-conflict environments.
    

---

### 🔸 **8. Explain how backward validation works in optimistic concurrency control.**

**Answer:**  
At commit time, the transaction being validated (`Tv`) checks if its read set conflicts with the write sets of already committed transactions. If conflict exists, `Tv` is aborted.

---

### 🔸 **9. Describe how deadlocks are detected using a wait-for graph.**

**Answer:**  
A wait-for graph shows which transactions are waiting on others. If a cycle is detected in the graph, it indicates a deadlock. One transaction in the cycle is then aborted to break the deadlock.

---

### 🔸 **10. What is the impact of premature writes on data consistency?**

**Answer:**  
Premature writes can overwrite data from uncommitted transactions. If a transaction aborts after another writes on top of its uncommitted value, the system may revert to an incorrect state.

---

### 🔸 **11. A transaction reads a value updated by another transaction that later aborts. What is the problem called? How is it solved?**

**Answer:**  
This is a **dirty read**. It is solved using **strict execution** where reads are delayed until all previous writers have committed or aborted.

---

### 🔸 **12. Give a real-world example where distributed transactions are necessary.**

**Answer:**  
**Example**: Transferring money between two banks. The debit from one bank and the credit to another must happen atomically.

---

### 🔸 **13. If two transactions T and U both update a shared object concurrently, what concurrency problem may arise?**

**Answer:**  
A **lost update** problem, where the update from one transaction overwrites or discards the other's changes.

---

### 🔸 **14. In nested transactions, can a sub-transaction commit if the parent aborts?**

**Answer:**  
No. If the parent transaction aborts, all of its sub-transactions are also rolled back, regardless of their individual outcome.

---

### 🔸 **15. What happens if a lock is not released after a transaction commits?**

**Answer:**  
It can block other transactions indefinitely, potentially leading to reduced concurrency or even deadlocks.

---

### 🔸 **16. (T/F) Optimistic concurrency control uses locks during the working phase.**

**Answer:**  
**False**. Optimistic control avoids locking and checks for conflicts at commit time.

---

### 🔸 **17. (T/F) Timestamp ordering avoids deadlocks by design.**

**Answer:**  
**True**. Since operations are ordered by timestamps, waiting cycles (deadlocks) do not occur.

---

### 🔸 **18. Which method is best when transactions mostly read and rarely write?**

**Answer:**  
**b) Timestamp Ordering**

---

### 🔸 **19. What condition does strict two-phase locking enforce?**

**Answer:**  
**b) Read/write delayed until commit/abort**

---

### 🔸 **20. (T/F) Forward validation checks a new transaction against active transactions’ read sets.**

**Answer:**  
**True**. It ensures the new transaction's write set doesn't conflict with active read sets.

# **---------------------------------------------------**
### **1. What is a key characteristic of a distributed system?**

**Correct Answer: d) Multiple independent entities communicating over a network**

- **a) Centralized data storage** – ❌ Incorrect. Centralized storage contradicts the nature of distributed systems, where data and components are spread across multiple locations.
    
- **b) Single point of failure** – ❌ Incorrect. Distributed systems aim to eliminate single points of failure by replicating services and data.
    
- **c) Processes communicate via shared memory** – ❌ Incorrect. Shared memory is typical in tightly-coupled systems, not in distributed systems where communication is via message passing over a network.
    
- **d) Multiple independent entities communicating over a network** – ✅ Correct. This defines the essence of distributed systems: independent components working together over a network.
    

---

### **2. Which of the following is NOT an example of a distributed system?**

>**Correct Answer: c) A computer system with one processor**

- **a) Cloud computing infrastructure** – ✅ Distributed, as it consists of many servers communicating to offer services.
    
- **b) File sharing systems** – ✅ Distributed, especially peer-to-peer models like BitTorrent.
    
- **c) A computer system with one processor** – ❌ Not distributed, as there’s only one computing entity.
    
- **d) Peer-to-peer networks** – ✅ Distributed, as they consist of many nodes sharing resources without central coordination.
    

---

### **3. What does scalability in a distributed system refer to?**

>**Correct Answer: a) The system's ability to handle increasing amounts of data without performance degradation**

- **a) The system's ability to handle increasing amounts of data without performance degradation** – ✅ Correct. Scalability means maintaining performance when the load increases.
    
- **b) The system's ability to add new hardware without increasing costs** – ❌ Incorrect. Adding hardware usually increases cost, although efficiently.
    
- **c) The system's ability to decrease its size** – ❌ Incorrect. This refers to elasticity, not scalability.
    
- **d) The system’s ability to handle high traffic only during peak times** – ❌ Incorrect. That’s more about elastic scaling or burst performance, not general scalability.
    

---

### **4. Which of the following is a primary challenge in distributed systems?**

>**Correct Answer: b) Time synchronization across nodes**

- **a) Multiple point of failures** – ❌ Incorrect. Systems aim to minimize points of failure through redundancy.
    
- **b) Time synchronization across nodes** – ✅ Correct. Ensuring that clocks are in sync across distributed nodes is challenging.
    
- **c) Unchanging network topology** – ❌ Incorrect. Network topology can change, but it’s not a central challenge.
    
- **d) Localized resource access** – ❌ Incorrect. Local resource access is easier and not a challenge; remote access is harder.
    

---

### **5. Which characteristic ensures functionality despite individual failures?**

>**Correct Answer: b) Fault tolerance**

- **a) Scalability** – ❌ Incorrect. It refers to handling more load, not failure.
    
- **b) Fault tolerance** – ✅ Correct. It means the system can withstand component failures and continue functioning.
    
- **c) Security** – ❌ Incorrect. It protects against threats, not failures.
    
- **d) Load balancing** – ❌ Incorrect. It distributes work but doesn’t handle component failure directly.
    

---

### **6. What term describes access to remote resources without knowing the details?**

>**Correct Answer: b) Transparency**

- **a) Resource allocation** – ❌ Incorrect. It refers to assigning resources, not hiding complexity.
    
- **b) Transparency** – ✅ Correct. Transparency hides complexity like location or replication from users.
    
- **c) Partition tolerance** – ❌ Incorrect. This refers to system resilience during network partitions.
    
- **d) Concurrency control** – ❌ Incorrect. It ensures consistent access by multiple processes, not about hiding system details.
    

---

### **7. Which of the following is NOT a form of transparency?**

>**Correct Answer: c) Timing Transparency**

- **a) Access transparency** – ✅ Exists; hides how resources are accessed.
    
- **b) Failure transparency** – ✅ Exists; hides failures from users.
    
- **c) Timing transparency** – ❌ Not commonly defined in standard distributed system literature.
    
- **d) Location transparency** – ✅ Exists; hides the physical location of resources.
    

---

### **8. Which is a key advantage of distributed systems?**

>**Correct Answer: c) High availability due to redundancy and fault tolerance**

- **a) High cost due to the hardware required** – ❌ Incorrect. That’s a disadvantage, not an advantage.
    
- **b) Easy to maintain due to single-node architecture** – ❌ Incorrect. Distributed systems are complex and not centralized.
    
- **c) High availability due to redundancy and fault tolerance** – ✅ Correct. This is one of the most important benefits.
    
- **d) Simplified security due to centralized control** – ❌ Incorrect. Security is more complex in distributed systems.
    

---

### **9. Which is NOT a component of a distributed system?**

**Correct Answer: d) A centralized server**

- **a) Nodes** – ✅ Part of DS, each performing tasks.
    
- **b) Communication subsystem** – ✅ Required for nodes to interact.
    
- **c) Database management system (DBMS)** – ✅ Can be distributed and is often used.
    
- **d) A centralized server** – ❌ Incorrect for distributed systems, as it contradicts the idea of decentralization.
    

---

### **10. What does "fault tolerance" refer to?**

**Correct Answer: b) The system’s ability to recover from hardware and software failures**

- **a) The system’s ability to store and retrieve large datasets** – ❌ Incorrect. This is storage capacity, not fault tolerance.
    
- **b) The system’s ability to recover from hardware and software failures** – ✅ Correct.
    
- **c) The system’s ability to process requests asynchronously** – ❌ Incorrect. That’s about concurrency, not fault tolerance.
    
- **d) The system’s ability to maintain high security** – ❌ Incorrect. Security is different from fault tolerance.
    

---

### **11. What is used to coordinate tasks in a DS?**

>**Correct Answer: b) Middleware**

- **a) Client-server model** – ❌ A type of architecture, not a coordination tool.
    
- **b) Middleware** – ✅ Correct. Acts as glue between applications and networks.
    
- **c) Centralized database** – ❌ Centralization is avoided in DS.
    
- **d) Local processing** – ❌ Not applicable in coordination among distributed nodes.
    

---

### **12. Which is an example of DS architecture?**

>**Correct Answer: d) All of the above**

- **a) Peer-to-peer** – ✅ True, e.g., BitTorrent.
    
- **b) Client-server** – ✅ True, e.g., web apps.
    
- **c) Hybrid** – ✅ True, combines on-premise and cloud.
    
- **d) All of the above** – ✅ Correct, includes all these types.
    

---

### **13. What transparency hides data distribution complexity?**

>**Correct Answer: c) Replication transparency**

- **a) Performance transparency** – ❌ Hides performance differences, not data distribution.
    
- **b) Location transparency** – ❌ Hides where resources are located, not replication.
    
- **c) Replication transparency** – ✅ Correct.
    
- **d) Access transparency** – ❌ Hides method of accessing resources, not their replication.
    

---

### **14. What is latency?**

>**Correct Answer: b) The time taken for a message to travel from one node to another**

- **a) Time to recover from a fault** – ❌ That’s recovery time.
    
- **b) Message travel time between nodes** – ✅ Correct.
    
- **c) Amount of data being processed** – ❌ That’s throughput.
    
- **d) Resource availability** – ❌ Unrelated to latency.
    

---

### **15. Essential property to ensure consistency?**

**Correct Answer: b) Eventual consistency**

- **a) High throughput** – ❌ May conflict with consistency.
    
- **b) Eventual consistency** – ✅ Correct; widely used in DS.
    
- **c) Real-time processing** – ❌ Not directly related to data consistency.
    
- **d) Caching and replication** – ❌ Help performance but may introduce inconsistency.
    

---

### **16. Not a common challenge in distributed systems?**

>**Correct Answer: d) Management of satellite data**

- **a) Time synchronization** – ✅ Common challenge.
    
- **b) Consistency management** – ✅ Also a key issue.
    
- **c) Geographical distribution** – ✅ True for distributed systems.
    
- **d) Management of satellite data** – ❌ Too domain-specific, not a core DS challenge.
    

---

### **17. What is the purpose of load balancing?**

**Correct Answer: c) To evenly distribute workloads across multiple servers or nodes**

- **a) Ensure all nodes handle data simultaneously** – ❌ Not necessary; depends on load.
    
- **b) Prevent data loss during communication** – ❌ That’s more about reliability.
    
- **c) Evenly distribute workloads** – ✅ Correct.
    
- **d) Reduce processing cost** – ❌ May be a side-effect, but not the main goal.
    

---

### **18. Critical feature of distributed database systems?**

>**Correct Answer: b) High redundancy and replication**

- **a) High centralization** – ❌ Opposite of distribution.
    
- **b) High redundancy and replication** – ✅ Helps with availability and fault tolerance.
    
- **c) No backup mechanisms** – ❌ Dangerous and incorrect.
    
- **d) Single-node storage** – ❌ Not distributed.
    

---

### **19. Which term describes operations appearing simultaneous?**

>**Correct Answer: a) Concurrency**

- **a) Concurrency** – ✅ Correct. It allows multiple tasks to run in parallel.
    
- **b) Atomicity** – ❌ Means indivisible operations, not parallelism.
    
- **c) Distributed transactions** – ❌ Related, but broader than just concurrency.
    
- **d) Synchronization** – ❌ Ensures ordering, not simultaneous appearance.
    

---

### **20. What is partition tolerance?**

>**Correct Answer: a) The system can continue operating even if network partitions occur between nodes.**

- **a) Continue despite partitions** – ✅ Correct.
    
- **b) Centralized database for easy access** – ❌ Opposes partition tolerance.
    
- **c) Independent from congestion** – ❌ That’s about QoS, not partition tolerance.
    
- **d) Always consistent** – ❌ Trade-off may lead to eventual consistency instead.

---


# *---------------------------------------------------*
### **1. What are the main advantages of using replication?**

**Answer:**

- **High Availability**: Replication allows continued service even if some nodes fail, as other replicas can take over.
    
- **Fault Tolerance**: If one replica fails due to hardware/software issues, others can maintain service integrity.
    
- **Performance Enhancement**: Multiple replicas can serve read requests in parallel, reducing latency and load on a single node.
    

> ✅ **Explanation**: Replication introduces redundancy in the system. This redundancy improves **availability** (since one node can fail and another can still serve), ensures **fault tolerance**, and can improve **read performance** through load distribution.

---

### **2. Availability Calculation Problem**

**Problem**: Three computers provide a replicated service. Each has a mean time between failure (MTBF) of 5 days. A failure takes 4 hours (1/6 day) to fix. What's the availability?

**Answer**:

- **Probability of one being down** = 4 / (5×24 + 4) hours = 4 / 124 ≈ **0.03226**
    
- **Probability of one being available** = 1 - 0.03226 ≈ **0.9677**
    
- **Availability of service (assuming at least one machine is available)** = 1 - (all 3 down)  
    = 1 - (0.03226)^3 ≈ **0.99997**
    

> ✅ **Explanation**: Availability of the entire service is high because even if individual machines are down occasionally, the likelihood of all 3 being down at once is extremely low.

---

### **3. Replicating object o but not o’**

**Problem**: Object `o` is replicated, but not object `o’`. When operation X on `o` triggers an invocation on `o’`, what problem arises?

**Answer**:

- **Problem**: All replicas of `o` may issue the same invocation to `o’`, causing duplicate actions (unless the operation is idempotent).
    
- **Solution**: Use **replication-aware smart proxies**. These proxies coordinate using a **consensus protocol** to ensure only one replica sends the invocation to `o’`. The result is multicast back to all other replicas.
    

> ✅ **Explanation**: Without coordination, you risk _duplicate operations_ on `o’`. The smart proxy ensures **exactly-once semantics** even with multiple `o` replicas.

---

### **4. Why may read-only replicas improve gossip system performance?**

**Answer**:

- **First**: Read operations are local and faster. In systems with many reads and fewer writes, this is efficient.
    
- **Second**: Read-only replicas don't need to store **vector timestamps** for update tracking, reducing metadata and complexity.
    

> ✅ **Explanation**: In a **read-heavy workload**, using read-only replicas reduces the load on write-enabled nodes and minimizes the overhead of synchronization.

---

### **5. Why both ‘replica’ and ‘value’ timestamps in gossip architecture?**

**Answer**:

- **Value Timestamp**: Reflects operations **applied** to the replica’s current state.
    
- **Replica Timestamp**: Tracks **received** updates, including those **not yet applied**. Used to assign new operations and manage future gossip exchanges.
    

> ✅ **Explanation**: This distinction is vital for tracking updates separately from application order, enabling consistency and fault tolerance in a **decentralized replication model**.

---

### **6. Vector Timestamp Evaluation Problem**

**Given**:

- Frontend has vector timestamp: **(3,5,7)**
    
- Replica Managers have:
    
    - RM1: (5,2,8)
        
    - RM2: (4,5,6)
        
    - RM3: (4,5,8)
        

**Question**:

- Which RM can satisfy a query?
    
- Which can accept an update?
    
- New frontend timestamp?
    

**Answer**:

- **RM3 (4,5,8)** is the **only one** that can serve the query: It has _all the updates_ the frontend has seen (component-wise greater than or equal).
    
- It is also the only one that can **accept updates** from the frontend immediately.
    
- New timestamp = **(4,5,8)**
    

> ✅ **Explanation**: A replica can only satisfy a frontend if its **value timestamp dominates or equals** the frontend’s. For updates, it must be able to **incorporate new events** without creating inconsistencies.

---

### **7. Compare Passive vs Active Replication**

| Feature              | Passive Replication                           | Active Replication                        |
| -------------------- | --------------------------------------------- | ----------------------------------------- |
| **Model Type**       | Linearizable (Single primary)                 | Sequential Consistent (All active)        |
| **Request Handling** | Only the primary handles client requests      | All replicas receive and process requests |
| **State Sync**       | Primary sends updates to backups              | Each replica updates its own state        |
| **Failure Handling** | Requires backup promotion (slower failover)   | No disruption unless majority fails       |
| **Complexity**       | Simpler to implement                          | Requires ordering and consensus           |
| **Performance**      | Lower overhead; high latency if primary fails | High overhead; fast failover              |
| **Consistency**      | Easier due to single execution point          | Harder due to need for identical ordering |

> ✅ **Explanation**:
>- **Passive Replication** is simpler and more efficient during normal operation but has higher failover latency.
>- **Active Replication** offers higher availability and lower failover time but needs more resources and complexity to maintain consistent ordering.

---

### **Summary of Key Terms in the Tutorial**

- **Replication**: Duplication of data/services to improve fault tolerance and performance.
    
- **Gossip Architecture**: A decentralized update propagation model using timestamps.
    
- **Vector Timestamp**: A tuple used to capture causal relationships and consistency.
    
- **Passive vs Active Replication**: Differ in how client requests are processed and how fault tolerance is achieved.




## **Replication Scenario**

- **Object o** is being replicated (there are multiple copies of o, each on a different server).
- **Object o’** is **not** replicated (there is only one copy of o’).
- **Operation X** on o causes o to invoke an operation on o’.

---

### **The Difficulty**

When you replicate o but not o’, and an operation X on o causes o to invoke o’, the following problem arises:
- **All replicas of o** (let’s say there are N of them) will each independently execute operation X.
- As a result, **each replica will independently invoke the operation on o’**.
- This means that for a single client request, **o’ will receive N invocations** instead of just one.

### **Why is this a problem?**

- If the operation on o’ is **not idempotent** (i.e., repeating it causes different effects, such as incrementing a counter or charging a credit card), this will lead to **incorrect behavior** (e.g., the counter is incremented N times, or the credit card is charged N times).
- Even if the operation is idempotent, this is **inefficient** and may cause unnecessary load or side effects.

---

### **Suggested Solution**

To prevent multiple invocations on o’, you need to ensure that **only one replica of o actually performs the invocation on o’** for each client request.

### **How can this be done?**

- **Smart, replication-aware proxies** are introduced between o and o’.
- When operation X is to be performed:
    1. The proxies (one per replica of o) **coordinate using a consensus algorithm** (e.g., leader election, distributed locking, or unique invocation ID assignment).
    2. **Only one proxy** is chosen to actually forward the invocation to o’.
    3. The chosen proxy performs the operation on o’ and **multicasts the result** to the other proxies/replicas.
    4. The other proxies/replicas **wait for the result** and use it as their own response.

This ensures that:
- **Only one invocation** is made to o’ per client request.
- **All replicas of o** see the same result, maintaining consistency.


## **Why making some replica managers read-only may improve the performance of a gossip system**

### **Background: Gossip System**

In a gossip-based replication system, updates to data are propagated between replica managers (RMs) in a peer-to-peer, epidemic fashion. Each RM keeps track of which updates it has seen and applied, often using vector timestamps. In a typical system, RMs can handle both reads and writes.

---

### **Improvement 1: Efficient Handling of Read Operations**

- **Read-only replica managers** can serve read requests locally, without needing to process or propagate updates.
- If the workload has **many more reads than writes** (which is common in web services, databases, etc.), having dedicated read-only RMs allows these read requests to be handled quickly and efficiently, reducing the load on full (read-write) RMs.
- **Result:** Improved overall system throughput and lower latency for read operations.

---

### **Improvement 2: Reduced Update Propagation Overhead**
- **Read-only RMs do not participate in update propagation.**
- Only a subset of RMs (the read-write ones) need to process and gossip about updates.
- This means **fewer nodes are involved in update dissemination**, reducing network traffic and processing overhead for updates.

---

### **Improvement 3: Smaller Vector Timestamps**
- In gossip systems, each RM often maintains a **vector timestamp** to track the state of updates across all RMs.
- **Read-only RMs do not accept updates**, so they **do not need entries in the vector timestamp**.
- With fewer RMs involved in updates, the **vector timestamp size is reduced**, leading to:
    - Lower metadata overhead in messages
    - Less memory usage
    - Simpler update tracking and conflict resolution

---

### **Summary Table**

|Benefit|Explanation|
|---|---|
|Faster reads|Read-only RMs can serve local reads instantly|
|Less update overhead|Updates are processed by fewer RMs, reducing network and CPU load|
|Smaller timestamps|Vector timestamps only track RMs that accept updates, so are shorter/simpler|

---

### **In Short**
**Making some replica managers read-only in a gossip system improves performance by:**
- Allowing fast, local handling of read requests
- Reducing the number of nodes involved in update propagation
- Minimizing the size and complexity of vector timestamps

This is especially effective when the system has many more reads than writes.


-----------------------------------
### *Q: Give an example of the interleavings of two transactions that are serially equivalent at each server but are not serially equivalent globally. Explain.*

---

## **Key Concepts**

- **Serial equivalence at a server:** At a given server (or object), the operations of the transactions occur in a serial order (all of T’s accesses to that object before U’s, or vice versa).
- **Global serial equivalence:** Across all objects/servers involved, the overall effect is the same as if the transactions were executed one after the other, in some global order.

**The problem:**  
It is possible for the transactions to be serialized at each object, but the overall (global) execution is not serially equivalent.

---

## **Example with Explanation**

## **Transactions**

- **T:**
    1. x = read(i)
    2. write(i, 10)
    3. write(j, 20)
- **U:**
    1. y = read(j)
    2. write(j, 30)
    3. z = read(i)

## **Interleaving**

Let’s interleave the operations as follows:

|Step|Operation|Object|
|---|---|---|
|1|T: read(i)|i|
|2|T: write(i, 10)|i|
|3|U: read(j)|j|
|4|U: write(j, 30)|j|
|5|T: write(j, 20)|j|
|6|U: read(i)|i|

## **At each object/server:**
- **At i:** T does all its accesses (read, write) before U (read).
- **At j:** U does all its accesses (read, write) before T (write).
    
So, **at each server**, accesses are serialized:
- At i: T before U
- At j: U before T
## **Globally:**

But **globally**, there is no single serial order (T before U or U before T) that matches this interleaving:
- If T were before U globally, then at both i and j, T should come before U.
- If U were before T globally, then at both i and j, U should come before T.

But here, at i, T comes before U, and at j, U comes before T!  
**This cannot be achieved by any serial execution of T and U.**

---

## **Why is this Not Globally Serially Equivalent?**

- **Serial equivalence requires** that for any two transactions, all their conflicting operations must be ordered the same way at every object they both access.
- In this interleaving, the order is inconsistent across objects:
    - At i: T before U
    - At j: U before T

So, **no global serial order** of T and U matches this interleaving.

---

## **Summary Table**

|Object|Order of Accesses|
|---|---|
|i|T → U|
|j|U → T|

**No serial order (T→U or U→T) matches both.**

---

## **Conclusion**

This example shows that **serial equivalence at each server does not guarantee global serial equivalence**.  
The interleaving above is **not globally serially equivalent** because the order of conflicting operations is not consistent across all objects.





