# Moving to Mesos from Bare metal - t.co service


## Static Partitions
- Wasted capacity
- Not fault tolerant
- Mesos uses containers?

## Issues

- Job Throttling
  - Sudden spikes in latencies because of cgroups - GC overhead was not taken into account which causes process freeze
    - What we learned - cgroups & cpu quotas
- Capacity Planning
  - Max traffic of the cluster was lower than our expectation
  - What we learned
    - Different CPU variants have different throughput
- Rethink service Discovery
    - Services get hosts and ports assigned dynamically
    - Used Aurora, hence ZK had all these information
    - What we learned
        - Use static proxies to forward connections
- No perfect isolation
    - Sudden spike in latency
    - noisy neighbours still affect us - mostly on the disks
    - Answer - move to Async write operations

Tools
- Twitter Frontend -- Can't seem to find a link to this.

<blockquote data-lang="en" class="twitter-tweet"><p dir="ltr" lang="en">Talk about how <a href="https://twitter.com/twitter">@twitter</a> uses <a href="https://twitter.com/ApacheMesos">@ApacheMesos</a> at <a href="https://twitter.com/hashtag/rootconf?src=hash">#rootconf</a> <a href="https://t.co/R89LKpPYrK">pic.twitter.com/R89LKpPYrK</a></p>— gethash (@gethash) <a href="https://twitter.com/gethash/status/720479925438963712">April 14, 2016</a></blockquote>
