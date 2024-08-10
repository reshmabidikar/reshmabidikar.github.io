---
title: "Hibernate Caching Mechanisms Explained"
date: "2019-05-23"
categories: 
  - "java-interview-questions"
  - "hibernate"
tags: 
  - "cache"
  - "hibernate"
---

In this blog post, I will be explaining Hibernate caching. Caching is the ability to buffer the data retrieved from the database. So the cache stores recently used data items. So if the same items are requested, these items are then returned from the cache thus reducing the number of calls that are made to the database. This increases the performance of an application

Hibernate supports 3 types of cache – First Level, Second Level, and Query Cache.

## First level cache

The first-level cache is nothing but the session cache. It caches data in the session. This cache is automatically enabled, programmers do not need to do anything. Hibernate stores all objects in the session.  So once Hibernate associates an object with a session, it remains in the session till the session is closed. So even if we try to load the object again, a database call is not made if the object is in the session. So also, when the code updates an object, all updates are delayed until the session is committed or closed. Once the session is closed, the first-level cache is terminated as well so all objects in the session are either persisted or lost.

## Second-level cache

The Second-Level Cache is an optional cache. Programmers need to explicitly enable it. There is a property that you need to specify in the config file to enable the Second-Level Cache. It caches data across sessions – within the same SessionFactory. So it is shared by all sessions created with the same session factory. Also, once you enable the Second-Level Cache, you need to supply the cache provider. A cache provider is something that provides an implementation of a cache. Different vendors have different implementations of the Second Level Cache. Hibernate provides built-in support for JCache, EHCache and Infinispan.

## Query Cache

The query cache caches the result of executing a query. Again, this is an optional cache and needs to be explicitly enabled.  When you enable the query cache, it stores the results of the query. The next time that the code fires query, Hibernate first checks the cache to see if there are results in the cache corresponding to the particular query and the query parameters. If Hibernate finds the results in the cache, it returns them, otherwise, it queries the database.  As you can see, it is not a good idea to cache a query, particularly if it has a large number of parameters.  Each parameter can take a number of values. For each of these combinations, the results are stored in the memory. This can lead to extensive memory usage.
