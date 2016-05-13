Title: Web Architecture Study Notes
Notebook: Evernote
Tags: EVND
Tags: Architecture, Study, Web, Design, System



[TOC]

# Scalable Web Architecture and Distributed Systems

## Principles of Web Distributed Systems Design

- Availability
- Performance
- Reliability
- Scalability
- Manageability
- Cost

## Basics

### Services

Service Oriented Architecture (SOA)

### Redundancy

Redundancy of its services and data

> Creating redundancy in a system can remove single points of failure and provide a backup or spare functionality if needed in a crisis

> Another key part of service redundancy is creating a **shared-nothing** architecture.

### Partitions

Scaling: scale vertically or horizontally

> Scaling vertically means adding more resources to an individual server.
> To scale horizontally, on the other hand, is to add more nodes.

> When it comes to horizontal scaling, one of the more common techniques is to break up your services into partitions, or shards. The partitions can be distributed such that each logical set of functionality is separate; this could be done by geographic boundaries, or by another criteria like non-paying versus paying users. The advantage of these schemes is that they provide a service or data store with added capacity.

## Fast and Scalable Data Access

*scalability of storage and fast access of data*

### Caches

> Caches take advantage of the locality of reference principle: recently requested data is likely to be requested again.

> Caches can exist at all levels in architecture, but are often found at the level nearest to the front end

Cache misses -> Two choices

- Global Cache
- Distributed Cache

#### Global Cache

> A global cache is just as it sounds: all the nodes use the same single cache space.

- Global cache where **cache** is responsible for retrieval
- Global cache where **request nodes** are responsible for retrieval

#### Distributed Cache
> In a distributed cache, each of its nodes own part of the cached data
- One of the advantages of a distributed cache is the increased cache space that can be had just by adding nodes to the request pool.
- A disadvantage of distributed caching is remedying a missing node

### Proxies

> At a basic level, a proxy server is an intermediate piece of hardware/software that receives requests from clients and relays them to the backend origin servers.

> Proxies are also immensely helpful when coordinating requests from multiple servers, providing opportunities to optimize request traffic from a system-wide perspective.

> One way to use a proxy to speed up data access is to collapse the same (or similar) requests together into one request, and then return the single result to the requesting clients. This is known as **collapsed forwarding**.

### Indexes

> Using an index to access your data quickly is a well-known strategy for **optimizing data access performance**; probably the most well known when it comes to databases.

> An index makes the trade-offs of **increased storage overhead and slower writes (since you must both write the data and update the index)** for the **benefit of faster reads**.

### Load Balancers

> **Load balancers** are a principal part of any architecture, as their role is to **distribute load** across a set of nodes responsible for servicing requests.

> Their main purpose is to **handle a lot of simultaneous connections** and **route those connections to one of the request nodes**, allowing the system to scale to service more requests by just adding nodes.


### Queues

Another important part of scaling the data layer is effective management of **writes**.


> Queues are fundamental in managing distributed communication between different parts of any large-scale distributed system.

> - Queues enable clients to work in an asynchronous manner, providing a strategic abstraction of a client's request and its response.
> - Queues also provide some protection from service outages and failures.


## Reference

- [Scalable Web Architecture and Distributed Systems - Kate Matsudaira](www.aosabook.org/en/distsys.html)
