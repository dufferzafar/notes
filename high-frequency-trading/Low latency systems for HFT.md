
## What I’ve learned after coding for HFT and Low Latency Systems

> [by Ariel Silahian](https://www.linkedin.com/pulse/what-ive-learned-after-coding-hft-low-latency-systems-ariel/)

* Choose the right language: FORGET about scripting languages, they won’t work. When you are looking to shave those last few microseconds off your processing time you cannot have the overhead of an interpreted language. Additionally, you will want a strong memory model to enable lock free programming so you should be looking at Java, Scala or my preferred one, C++11.

* Keep it all in memory: Read everything at the beginning. FORGET about databases or active persistence. I/O will kill your latency, so make sure all of your data is in memory. This generally means managing your own in-memory data structures and maintaining a persistent log, so you can rebuild the state after a machine or process restart. Alternatively, you might be able to get away with running a local, persisted in-memory database like Redis or MongoDB (with memory >> data). Note that you can loose some data on crash due to their background syncing to disk, but that’s the price isn’t?

* Keep your hardware underutilized: Low latency requires always having resources to process the request. Don’t try to run at the limit of what your hardware/software can provide. Always have lots of head room for bursts and then some.

* Keep context switches to a minimum: your code must be tailored on your hardware. Context switches are a sign that you are doing more compute work than you have resources for. You will want to limit your number of threads to the number of cores on your system and to pin each thread to its own core.

* Keep your reads sequential: make sure you are using CPU caches. All forms of storage, wither it be rotational, flash based, or memory performs significantly better when used sequentially. When issuing sequential reads to memory you trigger the use of prefetching at the RAM level as well as at the CPU cache level. If done properly, the next piece of data you need will always be in L1 cache right before you need it. The easiest way to help this process along is to make heavy use of arrays of primitive data types or structs. Following pointers, either through use of linked lists or through arrays of objects, should be avoided at all costs.

* Non blocking as much as possible: design your system to create non blocking and wait free data structures and algorithms. Every time you use a lock you have to go down the stack to the OS to mediate the lock which is a huge overhead. Often, if you know what you are doing, you can get around locks by understanding the memory model of the JVM or C++11.

* Async as much as possible: Any processing and particularly any I/O that is not absolutely necessary for building the response should be done outside the critical path.

* Parallelize as much as possible: Any processing and particularly any I/O that can happen in parallel should be done in parallel. For instance, if your high availability strategy includes logging transactions to disk and sending transactions to a secondary server those actions can happen in parallel.
