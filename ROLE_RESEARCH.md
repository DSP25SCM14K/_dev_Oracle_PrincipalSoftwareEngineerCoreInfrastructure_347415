# Oracle requisition 347415 — role and company research

Research date: November 3, 2026

## The role in the posting

Oracle’s posting is **Principal Software Engineer, Core Infrastructure**, requisition **347415**, posted October 14, 2026. It is an individual-contributor role in Seattle, Washington, or Santa Clara, California, with a stated experience range of 6–10+ years. The job description identifies the team as **Network Modeling and Control** within Oracle Cloud Infrastructure (OCI), focused on the network software that supports large GPU clusters and AI training and inference.

The team’s software translates physical network topology and intended configuration into coordinated infrastructure changes. The core challenges named in the listing are maintaining consistent network state; coordinating concurrent and long-running changes; recovering from partial failure; and automating safe configuration, expansion, and operation as network capacity grows.

The expected ownership spans the engineering lifecycle: distributed services and network models; APIs and automation for new GPU architectures; persistent workflow state, retries, and rollback; validation, testing, observability, and safer rollouts; bottleneck diagnosis; cross-team delivery; production support; incident follow-through; and mentoring. Helpful experience includes AI/ML infrastructure, GPU clusters, network automation and control systems, orchestration/reconciliation/scheduling, and model-based or formal verification. Oracle explicitly says strong systems fundamentals and the ability to learn the domain matter more than knowing every technology in its environment.

## Why the problem matters

A network change controller operates at the boundary between software intent and physical infrastructure. A plausible design must account for partial success: the workflow may time out after a device applied a change, a worker may be retried, resources may be modified concurrently, or a network partition may split observations from reality. Durable desired and observed state, idempotent actions, explicit transition validation, bounded retries, health gates, and compensating rollback help make those cases recoverable. Reconciliation provides a way to repair drift after a workflow completes or loses its coordinator. These are engineering interpretations of the responsibilities in the job posting, not claims about Oracle’s private implementation.

The AI infrastructure context increases the stakes. OCI’s public materials describe GPU compute clusters connected by high-bandwidth, low-latency RoCE/RDMA networking. Large training jobs depend on coordinated communication among accelerators, so capacity turn-up, accurate topology, safe lifecycle changes, and fast detection of a degraded path affect the useful capacity available to customers. Oracle’s AI infrastructure page describes Supercluster networking, including up to 3,200 Gb/sec of cluster bandwidth and support for large GPU clusters. Those are Oracle platform claims, not candidate achievements.

## Oracle and OCI context

Oracle’s recent business results show the scale and growth of the infrastructure context. In its June 10, 2026 FY2026 results, Oracle reported $34.0 billion in annual cloud revenue, up 39%, with $18.1 billion in Cloud Infrastructure (IaaS) revenue, up 77%. The September 10, 2026 Q1 FY2027 release reported IaaS revenue growth of 121% year over year. These company-wide figures help explain why software that brings physical AI capacity online and protects change safety has business relevance; they do not guarantee future growth.

On October 27, 2026, Oracle announced new Acceleron networking capabilities for moving data efficiently and operating multi-tenant AI clusters. The posting and these public materials point to a practical engineering target: evolve network models and control workflows as GPU architectures expand, while keeping infrastructure state correct and changes safe.

## Resume evidence that maps to the work

- **Network models and intent:** At Sprouts AI, designed a Go/Java distributed modeling service that turns infrastructure designs and topology into intended configuration; at Tata Steel, modeled topology for more than 2,000 plant network devices.
- **Long-running change orchestration:** At Sprouts AI, delivered zero failed rollouts across 300+ concurrent workflows using persistent state, idempotent retries, checkpoint recovery, and automatic rollback. At Resilience Inc, increased scheduling throughput 3× with Kafka, partitioned queues, backpressure, and exactly-once PostgreSQL state updates.
- **Reconciliation:** Built a controller that compares desired and observed network state and corrects drift on 95% of managed resources.
- **Verification and failure recovery:** Used model-based testing and TLA+ specifications to catch 15+ transition defects before release; previously found 20+ defects with fault-injection and network-partition tests.
- **Safe production change:** Cut network rollout time 60% with zero high-impact regressions using pre-change validation, canaries, health gates, Terraform, Ansible, and CI/CD.
- **Performance, operations, and collaboration:** Reduced execution time 45% and MTTR 40%; improved integration effort 35% across five partner teams through versioned APIs and topology models; mentored four engineers.
- **Infrastructure context:** Improved large-compute cluster utilization 30%; worked across Go, Java, Python, C++, Kubernetes, OCI, AWS, PostgreSQL, Kafka, and Linux.

The portfolio foregrounds network modeling, desired/observed state, orchestration, verification, safe rollout, and operational learning. It does not claim Oracle employment, Oracle-specific internal design, or direct experience beyond what the resume states.

## Sources

- [Oracle Careers — requisition 347415](https://careers.oracle.com/en/sites/jobsearch/job/347415/)
- [Oracle AI Infrastructure](https://www.oracle.com/ai-infrastructure/)
- [Oracle — Deploy a bare metal GPU cluster for AI workloads](https://docs.oracle.com/en/solutions/deploy-bare-metal-gpu-cluster-for-ai/index.html)
- [Oracle — GPU Memory Cluster and Memory Fabric](https://docs.oracle.com/en-us/iaas/Content/Compute/Concepts/gpu-memory-fabric.htm)
- [Oracle — FY2026 results](https://www.oracle.com/news/announcement/q4fy26-earnings-release-2026-06-10/)
- [Oracle Investor Relations — Q1 FY2027 results, September 10, 2026](https://investor.oracle.com/files/content_files/1q27-pressrelease-September_FINAL.pdf)
- [Oracle — new cloud networking innovations for AI, October 27, 2026](https://www.oracle.com/anz/news/announcement/ai-world-oracle-unveils-new-cloud-networking-innovations-for-ai-2026-10-27/)

