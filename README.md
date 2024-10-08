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
