# Caching

Caching is the #1 way to reduce latency and database load.

## Where to Cache?
- **Client Side**: Browser, mobile app.
- **CDN**: Edge locations for static content (Images, Video).
- **Load Balancer**: Can cache some static responses.
- **Application**: In-memory cache (Guava).
- **Distributed Cache**: Redis, Memcached.

## Eviction Policies
When the cache is full, what do we remove?
- **LRU (Least Recently Used)**: Remove the oldest-accessed item. (Most common answer).
- **LFU (Least Frequently Used)**: Remove the least-accessed item.
- **FIFO (First In First Out)**: Simple queue.

## Writing Strategies
- **Write-through**: Data is written to cache and DB simultaneously. (Safe but slow writes).
- **Write-around**: Write to DB directly, skip cache. (Prevents cache pollution).
- **Write-back**: Write to cache only, DB updated later asynchronously. (High performance, risk of data loss on crash).

## Common Problems
- **Cache Miss**: Requested item not in cache.
- **Cache Stampede (Thundering Herd)**: Many requests for the same expired key hit the DB at once.
- **Cache Penetration**: Requesting keys that don't exist (use Bloom Filters).
