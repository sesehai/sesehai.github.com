---
layout: post
category : News
tagline: ""
tags : [Apple]
title : 【transfer】A lot of people are mad that Apple bought this tiny company and shut it down
author: SSH
---

On Tuesday, word leaked that Apple was buying a tiny 40-person database startup called FoundationDB and a source tells us that this move is really freaking a lot of people out.

Neither Apple nor FoundationDB has publicly acknowledged the purchase yet (we've reached out repeatedly and asked for comment). But there's plenty of evidence that it happened and that Apple also immediately shuttered FoundationDB.

For some context, FoundationDB is a type of noSQL database. That's a popular type of database for Web applications, and it's cheaper to use than traditional databases like Oracle because they spread themselves across many low-cost commodity servers. An Oracle database prefers to be loaded onto a big, high-performance, and very expensive server.

"Apple bought Foundation not to resell the database, but for internal use," Peter Goldmacher, vice president of development of Aerospike, another noSQL database, tells us. (Prior to joining Aerospike, Goldmacher worked at MongoDB and prior to that, he was a Wall Street analyst covering databases.)

Word in Goldmacher's circles is that Apple will be "replacing" its huge Cassandra noSQL implementation with FoundationDB. Apple uses Cassandra for "iMessage, iTunes passwords, a bunch of stuff," he says.

In fact, Apple is touted as having one of the largest production deployments of Cassandra of all, with over 75,000 nodes storing over 10 pedabytes of data. Cassandra is a free and open source database with a commercial version offered by Datalogix.

Having Apple bail on Cassandra is not good for Datastax,  which recently raised $106 million (total funding of $190 million), on an $840 million valuation to take on Oracle. Apple's huge project serves as a showcase for Cassandra and is one reason why Cassandra has been growing in popularity, market watcher DB-Engines reports. (Datastax had no comment on this.)

FoundationDB shut down
GitHub/screen shot
FoundationDB pulled from GitHub

But that's not why people are mad.

While both Cassandra/DataStax and FoundationDB are noSQL databases, FoundationDB had some unique technology. It works super-fast but needs far less hardware than Cassandra, making it even cheaper to use, even as it scales. (In geek speak, it's an "in-memory" database that runs on flash storage.)

Goldmacher says it needs somewhere between 5% to 10% less hardware than Cassandra.

Most of these noSQL databases give their basic software away for free in an open source version, which allows their customers to add features and help with development. 

But FoundationDB's new owner (Apple, we presume) without notice yanked FoundationDB's open source software off of Github. 

FoundationDB teamFoundationDB
the FoundationDB team

FoundationDB had an active community of companies using it for their own sites.

Developers took a thread on Hacker News to vent. 

One user wrote, "Pulling an open-source project upon which people may depend is total jerk behavior."

FoundationDB, which sold its database as a cloud service, has also quietly suspended new customer registrations. (The sign-up page redirects you back to the home page.)

So Apple has no intention of sharing this technology, it seems.

Datalogix had no comment on Apple replacing Cassandra. But there's an awful lot of comment about all of this in the developer world.

[source >>](http://www.businessinsider.com/why-apple-bought-foundationdb-2015-3)