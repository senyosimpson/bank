# Representational State Transfer

Representational State Transfer (REST) is an *architectural style* that defines a set of constraints for building web services. It was invented by Roy Fielding in his PhD disseteration. A web service is described as RESTful if it follows the set of constraints. It should not be confused with a protocol. REST does not define what protocol is used to request/receive data or the format of that data, only the set of constraints necessary for a RESTful service.

## Core Tenets

REST is defined by 6 core tenets/constraints. They are

1. Client-server - The client and the server are independent of each other (decoupled). The client only has knowledge of the requests it can make and where to direct them while the server handles fetching the data and returning the response. This separates the implementation of each component, making it more portable and flexible.
2. Stateless - Session state is kept by the client. The request must have enough information to understand the request meaning no stored context (state) is contained by the server.
3. Cacheable - Data in a response should be labeled as cacheable or non-cacheable. Caching allows for faster retrievals on consecutive equivalent requests.
4. Uniform interface - This constraint contains 4 tents
    1. Resource identification in requests - Resources are identified in the request sent to the server
    2. Resource manipulation through representations - 
    3. Self-descriptive messages - The response sent to the client must contain enough information to describe how to process the information
    4. Hypermedia as the engine of application state - 
5. Layered system - Additional layers can be added in the client-server system. These layers offer additional features like load-balancing, security, caching etc.
6. Code on demand (optional) - The client can extend its functionality by receiving and downloading executable code

## References

1. [What is an API? - Red Hat](https://www.redhat.com/en/topics/api/what-are-application-programming-interfaces)
2. [What is REST?](https://restfulapi.net)