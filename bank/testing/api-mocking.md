# API Mock Testing

API mock testing is the use of a mock API server when testing code. A mock server is a server that imitates a live server. It will accept requests and return responses with simulated data. Mock servers can be grouped into static and dynamic servers. Static servers return the same data for each endpoint. This is advantageous as it is simple to use and deterministic - a great use case for testing. The disadvantage is that real servers return different data depending on the input and that data changes over time. Enter, dynamic servers. These return randomly generated data depending on their input. This makes it useful for covering the entire test space. Mock servers are most useful in two use cases. If you're developing a new application and the backend has not been fully developed, a mock server is used to imitate the actual server. This allows frontend components to be built even without a fully operational backend. The other use case is during testing. When testing code, you may need to call an API. Oftentimes, we don't actually want to call a live API. Some reasons include avoiding calls that modify the data, the data returned from the API is dynamic or avoiding make an unnecessary amount of calls to it.

## Mocking Best Practices

These best practices are from reference 2.

* Make the mock 100% technically equivalent - A mock should support the same transport protocols, schemas, etc as the actual API. The mock API should be accessible exactly like the original service and not require any special tooling or libraries.
* Use recording tools or log files to create complex mock behavior - For cases when you are uncertain about messages to return, record them with a proxy or packet-sniffer and then use those recordings to create the mock behavior.
* Use mocks to create negative tests - Simulate unexpected errors, long response times or even invalid messages to make sure your API client handles those gracefully.
* Use mocks to enable continuous testing - of your components; by mocking out external dependencies and APIs you can run your tests as often as you want without affecting those dependencies and without being affected by any unexpected changes or irregularities within them.
* Create your mock so that it can forward requests - If you are using mocking for enabling development, being able to to the actual API as it becomes available for certain operations allows you to partially replace mocked operations / behavior with its real counterpart as required by your scenario.

## References

1. [Mock API Server Testing & API Mocking Guide](https://stoplight.io/mock-api-guide/basics/)
2. [API Mocking: Best Practices & Tips for Getting Started](https://www.soapui.org/learn/mocking/what-is-api-mocking/)