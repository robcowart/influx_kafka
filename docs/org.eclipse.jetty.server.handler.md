# org.eclipse.jetty.server.handler

Applies to the following components:

* Confluent Control Center
* Confluent Schema Registry
* Confluent REST Proxy

## statisticshandler

### Tags

Tag | Description
--- | ---
id |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
asyncDispatches | totalcounter |  | The number of requested that have been asynchronously dispatched.
asyncRequests | totalcounter |  | The total number of async requests.
asyncRequestsWaiting | quantity |  | The currently waiting async requests.
asyncRequestsWaitingMax | quantity |  | The maximum number of waiting async requests.
dispatched | totalcounter |  | The number of dispatches.
dispatchedActive | quantity |  | The number of dispatches currently active.
dispatchedActiveMax | quantity |  | The maximum number of active dispatches being handled.
dispatchedTimeMax | timeticks | milliseconds | The maximum time spent in dispatch handling.
dispatchedTimeMean | timeticks | milliseconds | The mean time spent in dispatch handling.
dispatchedTimeStdDev | timeticks | milliseconds | The standard deviation of time spent in request handling.
dispatchedTimeTotal | timeticks | milliseconds | The total time spent in dispatch handling.
expires | totalcounter |  | The number of async requests requests that have expired.
requests | totalcounter |  | The number of requests.
requestsActive | quantity |  | The number of requests currently active.
requestsActiveMax | quantity |  | The maximum number of active requests.
requestTimeMax | timeticks | milliseconds | The maximum time spent handling requests.
requestTimeMean | timeticks | milliseconds | The mean time spent handling requests.
requestTimeStdDev | timeticks | milliseconds | The standard deviation of time spent in dispatch handling.
requestTimeTotal | timeticks | milliseconds | The total time spent in all request handling.
responses1xx | totalcounter |  | The number of requests with 1xx response status.
responses2xx | totalcounter |  | The number of requests with 2xx response status.
responses3xx | totalcounter |  | The number of requests with 3xx response status.
responses4xx | totalcounter |  | The number of requests with 4xx response status.
responses5xx | totalcounter |  | The number of requests with 5xx response status.
responsesBytesTotal | totalcounter | bytes | The total number of bytes across all responses.
statsOnMs | timeticks | milliseconds | The time in milliseconds that stats have been collected.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "org.eclipse.jetty.server.handler_statisticshandler"
  mbean = "org.eclipse.jetty.server.handler:id=*,type=statisticshandler"
  paths = ["asyncDispatches","asyncRequests","asyncRequestsWaiting","asyncRequestsWaitingMax","dispatched","dispatchedActive","dispatchedActiveMax","dispatchedTimeMax","dispatchedTimeMean","dispatchedTimeStdDev","dispatchedTimeTotal","expires","requests","requestsActive","requestsActiveMax","requestTimeMax","requestTimeMean","requestTimeStdDev","requestTimeTotal","responses1xx","responses2xx","responses3xx","responses4xx","responses5xx","responsesBytesTotal","statsOnMs"]
  tag_keys = ["id"]
```
