# GraphQL

## What is GraphQL?

The official GraphQL website describes it as, "a query language for your API and a runtime for fulfilling those queries with your existing data". It is a syntax that describes how to ask for data and returns only the data you need. [Graphene](https://docs.graphene-python.org/en/latest/quickstart/) mentions that GraphQL provides a standard way to

* Describe data provided by a server in a statically typed Schema
* Request data in query which exactly describes your data requirements
* Receive data in a response containing only the you requested

GraphQL lives between the client and one or more data sources. It allows for querying these data sources and massaging the data into the format requested by the client. This has many benefits

* Reduces the amount of data returned to the client
* Removes the necessity to massage the data on the client side
* Client can use a single query to get all the data necessarymagine a scenario where you have multiple REST API endpoints. When the client requests certain data, all solves the problem 

GraphQL APIs are flexible as they can be layered on top of other services such as REST APIs and databases. This is an additional advantage as it means there is no need for a serious overhaul of the current system.

## Core Tenets

* You should receive only the data you need
* Queries have the exact same shape as the result. This makes it unambiguous and the server knows exactly what fields the client is asking for.


## Tooling

1. [Apollo](https://www.apollographql.com) seems to have some of the best tooling for implementing GraphQL. It is JavaScript specific.
2. [Prisma](https://www.prisma.io/docs/understand-prisma/prisma-in-your-stack/graphql) also offers many tools for implementing GrapQL.
3. [Graphene](https://graphene-python.org) makes implementing GraphQL in Python easy. It uses a code-first approach.


## References

1. [GraphQL official website](https://graphql.org/learn/)
2. [So what is this GraphQL thing I keep hearing about?](https://www.freecodecamp.org/news/so-whats-this-graphql-thing-i-keep-hearing-about-baf4d36c20cf/)
3. [Graphene](https://docs.graphene-python.org/en/latest/quickstart/)
4. [GraphQL: Core Features, Architecture, Pros and Cons](https://www.altexsoft.com/blog/engineering/graphql-core-features-architecture-pros-and-cons/)
