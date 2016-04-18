# Design patterns in Microservices using Gilmour

From Piyush Verma, [@mesos10][1], Software consultant at datascale.io

### SOA (vs Servers)
#### What are services
- Logical Entities
    - Independent
    - Comprised of more services
- Multiple servers for load and tolerance
- Scalability
- Flexibility

> To err is human, to balme it on someone is management potential.

#### Why Services?
- Software Problem
    - Scalability
- Management Problem
    - Authority
    - Responsibility

#### Request Response
Explains what's a Request Response paradigm in general
##### When to use?
- Confirmed Delivery
- Response or Error guaranteed
- Http like
- Sender responsible for errors

#### Signal Slots
Reference - http://doc.qt.io/qt-4.8/signalsandslots.html
##### When to use?
- UDP-Like
- Broadcasting
- Wildcard topics
- Unreliable delivery
- Receiver responsible for errors

#### Service Discovery and Load Balancing
##### No Load balancing
- Gilmour works on Redis Subscriber Publisher
- No Querying discovery process
- Call service and not servers

#### Errors: Detection & Handling
- Timeouts
    - Server side - execution timed out
    - Client side - response too late
- confirm subscribers

##### Error Handling
- Ignore
- Publish
- Queue

You can compose in Gilmour - Pipe, AndAnd, OrOr

#### Tools
- [Gilmour][2]



  [1]: https://twitter.com/meson10
  [2]: https://github.com/gilmour-libs/gilmour-e-go