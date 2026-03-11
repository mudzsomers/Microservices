\# Report: The Microservices Paradox – Engineering for Scale vs. Cost



\## 1. What are Microservices?

Microservices is an architectural style where an application is built as a collection of small, autonomous services. 

\*   \*\*Independence\*\*: Each service can be developed and deployed without affecting others.

\*   \*\*Single Responsibility\*\*: Each service focuses on one specific task (e.g., "Billing" or "Search").

\*   \*\*Decentralized Data\*\*: Services typically have their own databases to avoid tight coupling.



---



\## 2. The Success Case: Netflix

Netflix is the pioneer of microservices, managing over \*\*1,000 independent services\*\* to support 260M+ users.



\### How they use it:

\*   \*\*Task Isolation\*\*: They split the "brains" (logic on AWS) from the "muscle" (video delivery via \[Open Connect CDN](https://openconnect.netflix.com)).

\*   \*\*Resilience\*\*: They use \[Chaos Monkey](https://netflix.github.io) to randomly shut down services in production, ensuring the system can survive individual failures.

\*   \*\*Independent Scaling\*\*: During a major show launch, they scale only the "Playback" and "Navigation" services to handle the surge.



---



\## 3. The "U-Turn": Companies Moving Back to Monoliths

Some companies have refactored back to monolithic structures to reduce "network tax" and operational overhead.



\### Company 1: Amazon Prime Video

\*   \*\*The Issue\*\*: Their video monitoring tool used microservices that passed data via \[AWS Step Functions](https://aws.amazon.com), causing massive costs and scaling bottlenecks.

\*   \*\*The Switch\*\*: They moved to a single monolithic process where data stays in memory.

\*   \*\*Result\*\*: They \*\*reduced infrastructure costs by 90%\*\*.



\### Company 2: Segment

\*   \*\*The Issue\*\*: Managing 140+ microservices became an operational nightmare. Updating a shared library required changes across 140 repositories.

\*   \*\*The Switch\*\*: They consolidated into a "Modular Monolith."

\*   \*\*Result\*\*: Development speed increased by eliminating "dependency hell."



---



\## Summary: Scale vs. Simplicity



| Feature | Microservices (Netflix) | Monolith (Prime Video) |

| :--- | :--- | :--- |

| \*\*Best For\*\* | Large, global apps | High-performance, data-heavy tasks |

| \*\*Primary Goal\*\* | Team speed and reliability | Low cost and simplicity |

| \*\*Complexity\*\* | High (Orchestration) | Low (Single Deployment) |



