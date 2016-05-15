Tags: computing, parallel, concurrent

# Parallel vs Concurrent

In short, Concurrency and Parallelism are **NOT** the same thing, they are related but quite distinct concepts.


## What's the Difference

From the [Quora answers](https://www.quora.com/What-is-the-difference-between-concurrent-computing-parallel-computing-and-distributed-computing)

> **Parallelism** is generally concerned with  accomplishing a particular computation as fast as possible, exploiting  multiple processors. The scale of the processors may range from multiple  arithmetical units inside a single processor, to multiple processors  sharing memory, to distributing the computation on many computers. On  the side of models of computation, parallelism is generally about using  multiple simultaneous threads of computation internally, in order to  compute a final result. Parallelism is also sometimes used for real-time reactive systems, which contain many processors that share a single master clock; such systems are fully deterministic.

> **Concurrency** is the study of computations with  multiple threads of computation. Concurrency tends to come from the  architecture of the software rather than from the architecture of the  hardware. Software may be written to use concurrency in order to exploit  hardware parallelism, but often the need is inherent in the software's  behavior, to react to different asynchronous events (e.g. a computation  thread that works independently of a user interface thread, or a program  that reacts to hardware interrupts by switching to an interrupt handler  thread).

> **Distributed** computing studies separate processors  connected by communication links. Whereas parallel processing models  often (but not always) assume shared memory, distributed systems rely  fundamentally on message passing. Distributed systems are inherently  concurrent. Like concurrency, distribution is often part of the goal,  not solely part of the solution: if resources are in geographically  distinct locations, the system is inherently distributed. Systems in  which partial failures (of processor nodes or of communication links)  are possible fall under this domain.


## Conclusion
> In programming, **concurrency** is the composition of independently executing processes, while **parallelism** is the simultaneous execution of (possibly related) computations.
> **Concurrency** is about dealing with lots of things at once. **Parallelism** is about doing lots of things at once.

> -- The Go Blog, Rob Pike [Link](https://blog.golang.org/concurrency-is-not-parallelism)

> **Concurrency** is often referred to as a property of a program, and is a concept more general than **parallelism**.
> Interestingly, we cannot say the same thing for **concurrent programming** and **parallel programming**. They are overlapped, but neither is the superset of the other.

> -- Yuan Lin [Link](https://blogs.oracle.com/yuanlin/entry/concurrency_vs_parallelism_concurrent_programming)

> **Concurrency** is a property of the program and **parallel** execution is a property of the machine.

> -- Douglas Eadline, Ph.D. [Link](http://www.linux-mag.com/id/7411/)



## Reference

- [Wikipedia: Parallel Computing](https://en.wikipedia.org/wiki/Parallel_computing)
- [Wikipedia: Concurrent Computing](https://en.wikipedia.org/wiki/Concurrent_computing)
- [Linux-Mag: Concurrent and Parallel Are Not The Same _By Douglas Eadline, Ph.D._](http://www.linux-mag.com/id/7411/)
- [The Go Blog: Concurrency is not parallelism](https://blog.golang.org/concurrency-is-not-parallelism) | [Slides](https://talks.golang.org/2012/waza.slide#1)
- [Yuan Lin: Concurrency vs Parallelism, Concurrent Programming vs Parallel Programming](https://blogs.oracle.com/yuanlin/entry/concurrency_vs_parallelism_concurrent_programming)
- [bytearcher: Parallel vs Concurrent in Node.js](http://bytearcher.com/articles/parallel-vs-concurrent/)
- [Quora: What is the difference between concurrent computing, parallel computing and distributed computing?](https://www.quora.com/What-is-the-difference-between-concurrent-computing-parallel-computing-and-distributed-computing)
- [HelpLib: Difference between concurrent programming and parallel programming](http://qa.helplib.com/191292)

### Misc
- [Concurrency can bite you even in Node](https://glebbahmutov.com/blog/concurrency-can-bite-you-even-in-node/)
