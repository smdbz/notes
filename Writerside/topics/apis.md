# APIs

## Introduction

You can think of APIs as a set of rules for how different software applications can interact with each other. It's up to
the creator of the API to define the rules, but it's helpful to follow best practices, so everyone starts on the same
page.




## RESTful

### Client-server architecture
There should be a serer that is serving the resources and client that is consuming them.

### Stateless
The server does not contain any state of the API client making the call,
so it cannot identify
who is making the request or what their previously requested data was without proper user information.
In fact, the State is only saved on the client machine, not on the server.

### Cacheable
Responses can be saved by a web browser or a server or any system.
This caching process can help to reduce the server load
by using the API results from the cache instead of making an actual request to the server everytime.

### Layered
The entire system architecture can be split or decoupled into layers.
You should be able to remove and replace a layer at any time.
![Screenshot 2024-12-18 172358.png](Screenshot 2024-12-18 172358.png)


