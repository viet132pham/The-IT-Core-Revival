# Caching in System Design

## What is Caching?

Caching is a system design technique that involves storing frequently accessed data in a location that is easily and quickly accessible. The purpose of caching is to improve the performance and efficiency of a system by reducing the time it takes to access frequently requested data.

Think of caching like a library where books are stored on shelves. Retrieving a book from a shelf takes time, so a librarian decides to keep a small table near the entrance. This table is like a cache, where the librarian places the most popular or recently borrowed books. When someone asks for a frequently requested book, the librarian checks the table first. If the book is there, it's quickly provided without needing to go to the shelves.

In computing systems:
- Accessing data from primary memory (RAM) is faster than accessing data from secondary memory (disk).
- Caching acts as a local store for data, making retrieval easier and faster than fetching from the main database.
- It serves as a short-term memory with limited space but offers faster access to recently or frequently used items.

## How Does Cache Work?

Typically, web applications store data in a database. When a client requests data:

1. The system first checks if the requested data exists in the cache
2. If the data is found in the cache (cache hit), it's returned directly, avoiding a database query
3. If the data is not in the cache (cache miss), it's fetched from the database, stored in the cache for future use, and then returned to the client

Reading data from a database requires network calls and I/O operations, which are time-consuming. Cache reduces these database calls, significantly speeding up system performance.

## Why You Cannot Store All Data in Cache

Despite its benefits, storing all data in cache is impractical for several reasons:

- **Limited Space**: Cache memory is typically more expensive and limited compared to disk storage
- **Cost**: High-performance cache hardware is much more expensive than normal database storage
- **Search Efficiency**: Search time increases with the volume of cached data
- **Volatility**: Cache is typically volatile storage, meaning data is lost if the system crashes or restarts
- **Relevance**: A cache needs to contain only the most relevant information according to anticipated future requests

## Types of Cache

### 1. Application Server Cache

An Application Server Cache is a storage layer within an application server that temporarily holds frequently accessed data. This helps applications run faster by reducing database load and speeding up response times.

**Example**: When an app frequently needs certain data, like user profiles or product lists, the application server can store this data in cache. When users request it, the app can instantly provide the cached version instead of processing a full database query.

**Drawbacks**:
- If you have multiple application servers with local caches, the same data might get cached on multiple servers, leading to inconsistency
- When a server goes down, its cache is lost
- Managing cache invalidation across multiple application servers can be challenging

### 2. Distributed Cache

A distributed cache is a separate caching layer that multiple application servers can access. It provides a centralized location for cached data, addressing the inconsistency issues of application server caches.

**Popular distributed cache systems**: Redis, Memcached

### 3. Client-Side Cache

Client-side caching stores data on the client's device (browser, mobile app). This reduces server load and network traffic.

**Example**: Browsers cache web pages, images, and CSS files to speed up future visits to the same websites.

### 4. CDN (Content Delivery Network)

CDNs distribute cached content across multiple geographical locations to minimize latency by serving content from the nearest server to the user.

## Applications of Caching

1. **Browser Caching**: Browsers save copies of frequently visited websites to speed up loading times and save bandwidth
2. **Database Caching**: Applications store frequently used database query results in memory to avoid repeated database access
3. **Content Delivery Networks (CDNs)**: Store copies of data (images, videos) in multiple locations worldwide, allowing users to access content from nearby servers
4. **Session Caching**: Applications store user session data (like login status) to provide seamless experiences without requiring re-login
5. **API Response Caching**: Frequently requested API data (stock prices, weather information) can be cached for faster responses

## Advantages of Caching

1. **Improved Performance**: Significantly reduces the time it takes to retrieve frequently used data
2. **Reduced Load on Original Source**: Decreases the number of requests to the primary data source
3. **Cost Savings**: Improves efficiency of existing resources, potentially reducing the need for expensive hardware upgrades
4. **Enhanced User Experience**: Faster response times lead to better user satisfaction
5. **Increased Throughput**: Systems can handle more requests when cache is properly implemented

## Disadvantages of Caching

1. **Data Inconsistency**: If cache consistency is not maintained properly, users may receive outdated information
2. **Cache Eviction Issues**: Poorly designed cache eviction policies can result in performance issues or data loss
3. **Additional Complexity**: Caching adds another layer to system architecture, making it more complex to design, implement, and maintain
4. **Memory Overhead**: Cache systems require additional memory resources

## Cache Invalidation Strategies

Cache invalidation ensures that outdated cached data is either updated or removed when the original data changes.

Common strategies include:

1. **Time-based Expiration**: Cached data is discarded after a predetermined time period
2. **Event-based Invalidation**: Cache entries are invalidated when specific events occur (data update, delete operations)
3. **Write-through**: Data is written to both the cache and the backing store simultaneously
4. **Write-behind/Write-back**: Data is written to cache, and the cache later synchronizes with the backing store
5. **Write-around**: Data is written directly to the backing store, bypassing the cache

## Cache Eviction Policies

Eviction policies determine which items to remove when the cache is full and new items need to be stored:

1. **Least Recently Used (LRU)**: Eliminates items that haven't been accessed for the longest time
2. **Least Frequently Used (LFU)**: Removes items that are accessed least frequently
3. **First-In-First-Out (FIFO)**: Evicts the oldest cached items first
4. **Random Replacement**: Randomly selects items to remove
5. **Time-To-Live (TTL)**: Removes items that have exceeded their predetermined expiration time

## Real-world Example: Cache Stampede

A cache stampede (also known as "thundering herd") occurs when a large number of requests hit a system simultaneously after a cache entry expires. This can overwhelm the backing database and cause system instability.

One notable example was a major Facebook outage where a cache stampede played a significant role. When a large number of cache entries expired simultaneously, the database was flooded with requests, causing a cascading failure.

## Conclusion

Caching is an essential technique in modern system design, offering significant performance improvements and resource optimization. However, it requires careful implementation with appropriate invalidation strategies and eviction policies to avoid data inconsistency and other potential issues.

As internet content continues to grow exponentially, caching becomes increasingly important for delivering responsive user experiences, especially for real-time applications like online gaming, video streaming, and collaborative tools. When implemented correctly, caching helps in delivering content quickly without needing to fetch it from the original source every time.