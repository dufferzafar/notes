
# High Frequency Trading

* What?
    - Traditional stock exchanges
    - Algorithmic trading
    - High Frequency

* How
    - What kind of a stack is used?
    - What traditional things are not suitable?

    - What's wrong with:

        + Operating Systems
            * Linux Kernel

        + Networking
            * TCP / IP

        + Storage

* Terms
    - Thread pinning - each to one CPU core

## Boost ASIO Comments

https://stackoverflow.com/a/54847003

I do work on ultra low latency financial markets systems. Like many in the industry, I am unable to divulge project specifics. However, I will attempt to answer your question.

In general:

At the lowest latencies you will find hardware based solutions.

Then: Vendor-specific kernel bypass APIs. For example where you encode and decode frames, or use a (partial) TCP/IP stack implementation that does not follow the BSD socket API model.

And then: Vendor-supplied drop-in (i.e. LD_PRELOAD) kernel bypass libraries, which re-implement the BSD socket API in a way that is transparent to the application.

Asio works very well with drop-in kernel bypass libraries. Using these, Asio-based applications can implement standard financial markets protocols, handle multiple concurrent connections, and expect median 1/2 round trip latencies of ~2 usec, low jitter and high message rates.

My advice to those using Asio for low latency work can be summarised as: "Spin, pin, and drop-in".

Spin: Don't sleep. Don't context switch. Use io_service::poll() instead of io_service::run(). Prefer single-threaded scheduling. Disable locking and thread support. Disable power management. Disable C-states. Disable interrupt coalescing.

Pin: Assign CPU affinity. Assign interrupt affinity. Assign memory to NUMA nodes. Consider the physical location of NICs. Isolate cores from general OS use. Use a system with a single physical CPU.

Drop-in: Choose NIC vendors based on performance and availability of drop-in kernel bypass libraries. Use the kernel bypass library.

This advice is decoupled from the specific protocol implementation being used. Thus, as a Beast user you could apply these techniques right now, and if you did you would have an HTTP implementation with ~10 usec latency (N.B. number plucked from air, no actual benchmarking performed). Of course, a specific protocol implementation should still pay attention to things that may affect latency, such as encoding and decoding efficiency, memory allocations, and so on.

As far as the low latency space is concerned, the main things missing from Asio and the Networking TS are:

Batching datagram syscalls (i.e. sendmmsg, recvmmsg).

Certain socket options.

These are not included because they are (at present) OS-specific and not part of POSIX. However, Asio and the Networking TS do provide an escape hatch, in the form of the native_*() functions and the "extensible" type requirements.

## Links

* [Wiki](https://en.wikipedia.org/wiki/High-frequency_trading)

* [C++ for low latency systems course](https://cppcon.org/using-c-for-low-latency-systems/)

* OrderBook design
    * [QuantCup 1's Winning design](https://gist.github.com/druska/d6ce3f2bac74db08ee9007cdf98106ef)
    * [Binary Tree based design](https://web.archive.org/web/20110219163448/http://howtohft.wordpress.com/2011/02/15/how-to-build-a-fast-limit-order-book/)
    * [StackExchange Discussion](https://quant.stackexchange.com/questions/3783/what-is-an-efficient-data-structure-to-model-order-book)
    * [Github Repo](https://github.com/Kautenja/limit-order-book)

* Tech stack
    - [Amazing article from ACM Queue](https://queue.acm.org/detail.cfm?id=2536492)
    - [Low Latency Linux | SE](https://softwareengineering.stackexchange.com/questions/183723/low-latency-unix-linux)
    - [Low latency programming](https://stackoverflow.com/questions/1209803/low-latency-programming)
    - [When a microsecond is an eternity | Youtube](https://www.youtube.com/watch?v=NH1Tta7purM)
    - [What-is-the-technology-stack-like | Quora](https://www.quora.com/High-Frequency-Trading/What-is-the-technology-stack-like-behind-an-HFT-platform)
    - [HFT | SO](https://stackoverflow.com/questions/1176986/high-frequency-trading)
    - [Fast network connections](http://www.alexeyab.com/2017/04/the-fastest-interconnect-for-hundreds.html)

* Issues
    - [Does it add value to the society?](https://www.quora.com/High-Frequency-Trading/How-does-trading-especially-high-frequency-trading-add-value-to-society)

* Books
    - [Flash Boys | Non fiction account | Michael Lewis](https://en.wikipedia.org/wiki/Flash_Boys)

* [Java performance group](https://plus.google.com/u/1/communities/107178245817384004088)
