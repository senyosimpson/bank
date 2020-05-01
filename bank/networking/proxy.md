# Proxy

A proxy server is an intermediate server between an end user and the internet. When an end user makes a request to some server, it first flows through the proxy and on return, flows back through the proxy before reaching the end user. This design pattern means a proxy can perform a set of actions before a request is routed to its intended recipient. The most common use cases for proxies are security and network performance. They can act as firewalls, web filters and cache data to speed up requests amongst many other useful features.

## Types of Proxies

* **Transparent Proxy** - This proxy informs websites that it is a proxy server and passes along the IP address of the user. It is mostly used for web filtering (for example in schools)
* **Anonymous Proxy** - This server identifies itself as a proxy server but does not pass along the IP address of the user.
* **Distorting Proxy** - This server also identifies itself as a proxy server but passes along a fake IP address. An example of when this is useful is accessing geo-blocked content. In this case, the IP address appears to originate from a different location.
* **High Anonymity Proxy** - This server periodically changes the IP address it presents to the user in order to obfuscate the origination of the request.

## References

1. [What is a proxy server?](https://www.varonis.com/blog/what-is-a-proxy-server/)