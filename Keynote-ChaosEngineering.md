# Chaos Engineering and design patterns for building highly available services

From HashiCorp

Correlation between scale and change

Enterprise IT - Everything works
- Slowly changing
- Small scale

Web scale - Everything is Broken
- Rapid Change
- Large Scale

Telcos - Hardware will fail
- Slowly changing
- Large scale

Startups - Software will fail
- Rapid change
- Small scale


- Increased the number of failure points from Monoliths to µ Services
- Read through cache

## Chaos Engineering
- Failure Injection
    - Introduce failures in dependencies in a slow but gradual manner
        - Use iptables or net filters to introduce the packet failures
    - Latency Monkey
    - Use auditing and monitoring while failures being injected in a system

## Failures revisited
- Node failures
    - Deploy clusters not nodes
    - State should be at a service level
    - Unleash chaos monkey
- Switch Failures
- DC interconnect failures
- Region failures
- DNS failures
    - Be prepared to know how to escalate
    - Increase TTL

## Chaos Engineering applied to Human Resources
- Be prepared to not have the full team to deal with outages
- Send your team members on vacation
- Prepare runbooks and dashboard to triage and avoid trival knowledge

## Tools for building resilient systems
- Reactive LB
- Circuit Breakers
    - Guard client calls with CB
- Dynamic Cluster schedulers
- Dynamic Service Discovery
- Reactive Scaling
- Immutable Infrastructure
    - Cattle and not pets
    - Infra should be considered disposable

Note - Talk by Jeff Dean - handling latencies for tail end of the user services

## Hope is not a strategy

## References
- Notes on Distributed Systems for the young blood - Jeff Hodges
- How complex systems fail - Richard Cook
- Drift into failure - Sidney Dekkar

<blockquote data-lang="en" class="twitter-tweet"><p dir="ltr" lang="en">Keynote by <a href="https://twitter.com/diptanu">@diptanu</a> on building resilient systems. <a href="https://twitter.com/hashtag/DevOps?src=hash">#DevOps</a> <a href="https://twitter.com/hashtag/rootconf?src=hash">#rootconf</a> <a href="https://t.co/FW7SRwCl8Y">pic.twitter.com/FW7SRwCl8Y</a></p>— Rootconf (@rootconf) <a href="https://twitter.com/rootconf/status/720501956020682753">April 14, 2016</a></blockquote>
