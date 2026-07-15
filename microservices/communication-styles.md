# Communication Styles

Microservices communications styles are broadly divided into 2  categories namely  Synchronous and Asynchronous . In this article we will try to understand basics of them along with Pros and Cons associated with each of them.

## Synchronous - (Request - Response)

In this style, Caller sends request with required information to service and waits for response from service. In this case caller is blocked until it receives response from service.

### Advantages&#x20;

1. From high availability point of view ,Many active instance can be up and running accepting traffic as no **Infrastructure dependencies** such as shared messaging servers. The Infrastructure management is less.
2. Error at any stage will propagate immediately to caller keeping the system in consistent state without compromising data integrity.

### Disadvantages

1. User or caller has to wait until request is processed by service, as result of that the calling thread will be blocked which will limit scalability of system.
2. This style adds hard dependencies between microservices i.e. If one of the service in service chain fails then entire service chain will  fail .
3. In order to make service successful all the dependent services in chain should be up and running all the time. Many failure scenarios have to be handled using timeout and fallbacks.

## Asynchronous - (Fire and Forget)

In this style service is designed to accept an asynchronous message as input and response will be send in the form of asynchronous message by the service. This exchange of messages is happening using any messaging systems e.g. Kafka or Any Messaging Queues. In this style services are listening to input queue for input messages sent by callers then process the input message asynchronously and return response in the form of output message in output queue which helps in decouples microservices.

### Advantages&#x20;

1. This style provides higher level of scalability because services are independent of each other.
2. Service will be responsive in case of excess load input messages will be queued in messaging server and service can consume the input message (request) at their own pace.Hence slowdown in one service won't have impact on entire service chain.
3. It provides high level of decoupling between services hence testing and maintenance of them is simple.

### Disadvantages

1. In this communication style there will be dependency on external messaging servers .Handling Fault tolerance of messaging servers is complex.
2. Messaging typically works on active -passive semantics hence handling continuous availability of messaging system is harder to achieve.
3. &#x20;Messaging uses persistence storage and high level of I/O handling hence tuning is required.

## Conclusion&#x20;

Each microservices communication style has its own advantages as well as disadvantages. Communication style would be purely determined based on your requirements. &#x20;
