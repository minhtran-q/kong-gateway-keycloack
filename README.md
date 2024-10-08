# Kong Gateway Keycloack

## Kong API Gateway

### Terminology

<details>
  <summary>Service</summary>
  <br/>
  A Service in Kong represents an upstream API or microservice. It acts as an abstraction layer for the actual backend service. When you define a service, you specify the connection details to the upstream application, such as the `URL`, `protocol`, `host`, `port`, and `path`.
  
</details>
<details>
  <summary>Route</summary>
  <br/>

  A Route defines how incoming requests are matched and forwarded to a service. Routes contain rules that determine which requests should be proxied to which services. These rules can be based on `paths`, `methods`, `headers`, or other request attributes.
  
</details>
<details>
  <summary>Upstream Application</summary>
  <br/>

  An Upstream Application is the actual backend service that handles the requests forwarded by Kong. In Kong, an upstream object can represent a group of backend servers, allowing for load balancing and health checks.
  
</details>

### Fundamental concepts

<details>
  <summary>How Kong API work?</summary>
  <br/>

  + **Client Request:** A client sends a request to Kong.
  + **Route Matching:** Kong evaluates the request against the defined routes to find a match. Routes can be configured to match based on URL paths, HTTP methods, headers, etc.
  + **Service Forwarding:** Once a route is matched, Kong forwards the request to the associated service.
  + **Upstream Handling:** The service then directs the request to the upstream application, which processes the request and sends back a response.
  + **Response:** The response from the upstream application is sent back through the service and route, eventually reaching the client.

  _Example:_ Imagine you have a service called `example-service` that points to an upstream API at `http://example.com`. You create a route that matches requests with the path `/example` and associates it with `example-service`. When a client makes a request to `http://kong-gateway.com/example`, Kong matches this request to the route, forwards it to `example-service`, which then proxies it to `http://example.com`.
</details>
