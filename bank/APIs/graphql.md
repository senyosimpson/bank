# GraphQL

## What is GraphQL?

The official GraphQL website describes it as, "a query language for your API and a runtime for fulfilling those queries with your existing data". It is a syntax that describes how to ask for data and returns only the data you need. [Graphene](https://docs.graphene-python.org/en/latest/quickstart/) mentions that GraphQL provides a standard way to

* Describe data provided by a server in a statically typed Schema
* Request data in query which exactly describes your data requirements
* Receive data in a response containing only the you requested

GraphQL APIs are flexible as they can be layered on top of other services such as REST APIs and databases. This is an additional advantage as it means there is no need for a serious overhaul of the current system. For my current use cases, layering it on top of a REST API is most relevant. This wiki will cover implementing this in Python and Golang.

## Core Tenets

* You should receive only the data you need
* Queries have the exact same shape as the result. This makes it unambiguous and the server knows exactly what fields the client is asking for.


## Best Practices


## References

1. [GraphQL official website](https://graphql.org/learn/)
2. [So what is this GraphQL thing I keep hearing about?](https://www.freecodecamp.org/news/so-whats-this-graphql-thing-i-keep-hearing-about-baf4d36c20cf/)
3. [Graphene](https://docs.graphene-python.org/en/latest/quickstart/)
