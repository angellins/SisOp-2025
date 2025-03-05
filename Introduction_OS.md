Nama : Angelina Safara
NRP : 3124521004
Kelas : 1 Teknik Informatika A

Practice exercise
1.	What are the three main purposes of an operating system?
Answer:
The three main goals of an operating system are:
•	Convenience: An operating system aims to make it easier for users to interact with the computer.
•	Efficiency: An operating system manages computer resources such as CPU, memory, and I/O devices efficiently.
•	Ability to evolve: An operating system is designed to be able to evolve and adapt to new technologies.
2.	We have stressed the need for an operating system to make efficient use of the computing hardware. When is it appropriate for the operating system to forsake this principle and to "waste" resources? Why is such a system not really wasteful?
Answer:
Operating systems (OS) are generally designed to manage computing resources as efficiently as possible. However, there are situations where the OS may shift its priorities and “waste” resources to achieve other goals such as improving user experience, increasing security, and advanced features.
While it may seem like “waste,” these features are usually optimized to remain efficient.
3.	What is the main difficulty that a programmer must overcome in writing an operating system for a real-time environment?
Answer:
The main difficulty for programmers in writing operating systems for real-time environments is ensuring determinism and timeliness of system response, which requires efficient interrupt handling, careful process scheduling, and high reliability and robustness.
4.	Keeping in mind the various definitions of operating system, consider whether the operating system should include applications such as web browsers and mail programs. Argue both that it should and that it should not, and support your answers.
Answer:
The inclusion of applications such as web browsers and email in an operating system has its pros and cons; the former increases the usability of the software for novice users who may have difficulty installing the software themselves and basic computing functions, while opponents emphasize the principle of minimalism, as well as the security and stability risks, so the decision involves a trade-off between usability, efficiency, and competition.
5.	How does the distinction between kernel mode and user mode function as a rudimentary form of protection (security)?
Answer:
Kernel mode is a mode with full access rights to hardware and all memory while user mode is a mode with limited access rights, both separate access rights to protect the system but are not completely secure because vulnerabilities in kernel code, drivers, and system call handling can be exploited to compromise the system.
6.	Which of the following instructions should be privileged?
a. Set value of timer.
b. Read the clock.
c. Clear memory.
d. Issue a trap instruction.
e. Turn off interrupts.
f. Modify entries in device-status table.
g. Switch from user to kernel mode.
h. Access I/O device
answer:
e. Turn off interrupts: allows the operating system to complete its tasks without interruption.
g. Switch from user to kernel mode: to perform sensitive system operations that require high privileges.
d. Issue a trap instructions: to maintain system stability and security
f. Modify entries in the device-status table: to manage and control hardware.
h. Access I/o devices: for communication with hardware
a. Set value of timer: for process scheduling
b. Read the clock
c. Clear memory: for memory management,
7.	Some early computers protected the operating system by placing it in a memory partition that could not be modified by either the user job or the operating system itself. Describe two difficulties that you think could arise with such a scheme.
Answer:
Operating system protection schemes with unmodifiable memory partitions have the main difficulty of lacking flexibility for security updates and fixes, and remaining vulnerable to exploitation if there are gaps in the operating system code, making protection not fully effective.
8.	Some CPUs provide for more than two modes of operation. What are two possible uses of these multiple modes?
Answer:
CPU dengan lebih dari dua mode operasi memungkinkan virtualisasi yang aman dengan mode khusus untuk mesin virtual, dan menyediakan mode keamanan tambahan untuk menjalankan kode kritis seperti Trusted Execution Environment (TEE), meningkatkan perlindungan dan dukungan untuk berbagai aplikasi dengan kebutuhan keamanan dan kinerja yang berbeda.
9.	Timers could be used to compute the current time. Provide a short description of how this could be accomplished
Answer:
Pengatur waktu menghitung waktu dengan menghasilkan interupsi pada interval tetap, yang meningkatkan penghitung sistem operasi, lalu dikonversi ke satuan waktu yang dapat dibaca, dan disimpan untuk diakses aplikasi.
10.	Give two reasons why caches are useful. What problems do they solve? What problems do they cause? If a cache can be made as large as the device for which it is caching (for instance, a cache as large as a disk), why not make it that large and eliminate the device?
Answer:
Caches improve performance by storing frequently accessed data, bridging the speed gap between CPU and storage, but they pose data coherence and size limitations, and cannot replace storage due to cost, volatility, purpose differences, and scalability.
11.	Distinguish between the client-server and peer-to-peer models of dis-tributed systems
Answer:
The client-server model has a centralized structure with the server providing the service and the client requesting the service, so control and resources are centralized, scalability is limited if the server is overloaded, security is centralized, and clients are dependent on the server, as in the web and email; while the peer-to-peer (P2P) model is decentralized with no central server, each node acts as both a client and a server, resources are distributed, scalability increases with the number of peers, security is distributed, and there is no dependence on a central server, as in file sharing and blockchain.
Chapter 1 exercise
12.	How do clustered systems differ from multiprocessor systems? What is required for two machines belonging to a cluster to cooperate to provide a highly available service?
Answer:
A multiprocessor system consists of multiple CPUs in a single computer that share memory to increase computing performance, while a clustered system consists of multiple separate computers connected over a network to increase service availability; for two machines in a cluster to work together for high availability, redundancy, automatic failover, load balancing, reliable communications, and (optionally) shared storage are required.
13.	Consider a computing cluster consisting of two nodes running a database. Describe two ways in which the cluster software can manage access to the data on the disk. Discuss the benefits and disadvantages of each
Answer:
Cluster software can manage data access to disks in two ways:
shared disk, where both nodes access the same disk with a locking mechanism to prevent conflicts, which is simple and provides high availability but has a single point of failure and scalability limitations
shared nothing, where each node has its own disk with data replicated or partitioned, which is more complex but has high scalability, no single point of failure, and better performance because each node has its own disk.
14.	What is the purpose of interrupts? How does an interrupt differ from a trap? Can traps be generated intentionally by a user program? If so, for what purpose?
Answer:
An interrupt is a signal from external hardware or software to notify the CPU of an event, allowing the operating system to respond efficiently, while a trap is a service request from a user program to the operating system generated by a software instruction, with the user program intentionally using a trap to request a service that requires special access rights..
15.	Explain how the Linux kernel variables HZ and jiffies can be used to determine the number of seconds the system has been running since it was booted
Answer:
The Linux kernel variable HZ defines the timer interrupt frequency per second, and jiffies stores the number of interrupts since boot; by dividing jiffies by HZ, we can determine the number of seconds the system has been running, taking into account potential jiffies overflow and using jiffies_64 for long-running systems.
16.	Direct memory access is used for high-speed 1/O devices in order to avoid increasing the CPU's execution load.
Answer:
a. How the CPU Interfaces with Devices to Coordinate Transfers: The CPU initiates a DMA transfer by writing to the DMA control register. The DMA controller then takes over the system bus and transfers data directly between the I/O device and memory, without involving the CPU in any data transfers.
b. How Does the CPU Know When a Memory Operation is Complete?
After a DMA transfer is complete, the DMA controller signals the CPU via an interrupt that the data transfer is complete. The CPU can also check the DMA status register to see the status of the transfer
C. The CPU is allowed to execute other programs while the DMA controller is transferring data. Does this process interfere with the execution of user programs? If so, describe what forms of interference are caused
Yes, the DMA process can disrupt the execution of user programs.
• Cycle Stealing:
• The DMA controller takes over the system bus to transfer data, which can slow down CPU access to memory.
Interrupts:
• When a DMA transfer is complete, the DMA controller generates an interrupt, which can disrupt the flow of user program execution.
17.	Some computer systems do not provide a privileged mode of operation in hardware. Is it possible to construct a secure operating system for these computer systems? Give arguments both that it is and that it is not possible
Answer:
arguments in favor
• Operating systems can use software virtualization techniques to simulate operating modes
• Operating systems can enforce strict access control at the software level
• Operating systems can isolate user processes from each other to prevent them from interfering or damaging each other
arguments against
• It is difficult to prevent user processes from accessing operating system memory or hardware.
• Software virtualization techniques and software access control can introduce overhead
• Operating systems without hardware operating modes are more vulnerable to security attacks
18.	Many SMP systems have different levels of caches; one level is local to each processing core, and another level is shared among all processing cores. Why are caching systems designed this way?
Answer:
The local and shared cache system in SMP is designed to reduce memory access latency with fast local caches for individual core data and shared caches for inter-core data, improve multitasking performance by allowing cores to work independently and share data efficiently, manage cache coherence with a shared coordination point, and optimize memory usage by separating individual core data and shared data.
19.	Rank the following storage systems from slowest to fastest:
Answer:
f. Magnetic tapes
c. Optical disk
a. Hard-disk drives
e. Nonvolatile memory
d. Main memory
g. Cache
b. Registers
20.	Consider an SMP system similar to the one shown in Figure 1.8. Illustrate with an example how data residing in memory could in fact have a different value in each of the local caches.
Answer:
Scenario
•	A variable x in main memory has an initial value of 10.
•	The value of x (10) is loaded into CPU0's local cache
•	The value of x (10) is loaded into CPU1's local cache.
•	CPU0 executes an instruction to change the value of x to 20.
•	This change only occurs in CPU0's local cache. Main memory has not been updated.
Illustration of the difference in values
Location	Value x
Main memory	10
Cache cpu0	20
Cache cpu1	10

21.	Discuss, with examples, how the problem of maintaining coherence of cached data manifests itself in the following processing environments:
Answer:
a.Single Processor Systems:
In single processor systems, cache coherence problems typically arise when there are multiple caches or buffers that hold copies of the same data.
Examples include CPU caches and I/O buffers. If the data is modified by an I/O device, the copy in the CPU cache may become invalid
b. Multiprocessor Systems:
In multiprocessor systems, each CPU has its own local cache. If multiple CPUs access and modify the same data, the copies of the data in the different caches may become inconsistent.
For example, Two CPUs access the same variable in main memory. CPU1 modifies the variable and stores it in its local cache. CPU2 now has an outdated copy of the variable in its local cache
c. Distributed Systems:
In distributed systems, data may be cached at multiple locations, such as a web server, a database server, and a client 
For example, A web page is cached at multiple proxy servers. If the web page is modified on the origin server, the proxy servers must update their caches.
22.	Describe a mechanism for enforcing memory protection in order to prevent a program from modifying the memory associated with other programs
Answer:
Memory protection prevents programs from changing another program's memory through segmentation (dividing memory into segments with access rights), paging (dividing memory into pages with page table mapping), a combination of both, the Memory Management Unit (MMU) as address translation hardware, and kernel/user mode which separates access rights
23.	Which network configuration-LAN or WAN-would best suit the fol-lowing environments?
Answer:
 a. A campus student union : LAN
b. Several campus locations across a statewide university system : WAN
c. A neighborhood : LAN
24.	Describe some of the challenges of designing operating systems for mobile devices compared with designing operating systems for tradi-tional PCs
Answer:
Designing an operating system for mobile devices is different from traditional PCs due to resource constraints, hardware diversity, touch interfaces, cellular connectivity, security, application ecosystem, and OS updates, which require efficiency optimization, intuitive UI design, handling unstable networks, sensitive data protection, developer support, and complex update distribution.
25.	What are some advantages of peer-to-peer systems over client-server systems?
Answer:
Peer-to-peer (P2P) systems offer the advantages of decentralization without a central server, easy scalability with the addition of peers, resilience to disruptions and attacks, lower implementation and maintenance costs, and the ability to share resources directly between peers, making them a strong choice for applications that require high availability and cost efficiency.
26.	Describe some distributed applications that would be appropriate for a peer-to-peer system
Answer:
Peer-to-peer (P2P) systems are well suited for distributed applications that require decentralization, scalability, and resilience, such as file sharing with BitTorrent, real-time communication like Skype, cryptocurrencies like Bitcoin, blockchain technology for distributed data, media streaming, content delivery networks (CDNs), online gaming, and distributed computing for shared computing tasks.
27.	Identify several advantages and several disadvantages of open-source operating systems. Identify the types of people who would find each aspect to be an advantage or a disadvantage.
Answer:
Advantages of Open Source Operating Systems:
•Free or Low Cost:
Type of people: Individuals or organizations on a budget such as Students, home users, small businesses, non-profit organizations.
• Flexibility and Customization:
The available source code allows users to modify and customize the operating system according to their needs.
Type of people: Software developers, system administrators, advanced users.
• Security:
Open source code allows the community to quickly review and fix security vulnerabilities.
Type of people: System administrators, security professionals, security-conscious users.
• Transparency:
Open source code allows users to see how the operating system works.
Type of people: Privacy-conscious users, researchers.
Disadvantages of Open Source Operating Systems:
• Lack of Commercial Support:
Unlike closed source operating systems, open source operating systems may not have official commercial support.
Type of people: Business users, large organizations.
• Hardware and Software Compatibility:
Some hardware and software may not be fully compatible with open source operating systems.
Type of person: Users who rely on specialized hardware or software.
• Security:
While open code has its positives in terms of security, it can also be a vulnerability if a malicious person finds a bug that has not been detected by the community.
Type of person: Users who are concerned about potential exploits
