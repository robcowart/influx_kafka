# kafka.admin.client

Applies to the following components:

* ksqlDB
* Confluent Control Center

## admin-client-metrics

### Tags

Tag | Description
--- | ---
client-id |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
connection-close-rate | quantity |  | The number of connections closed per second.
connection-close-total | totalcounter |  | The total number of connections closed.
connection-count | quantity |  | The current number of active connections.
connection-creation-rate | quantity |  | The number of new connections established per second.
connection-creation-total | totalcounter |  | The total number of new connections established.
failed-authentication-rate | quantity |  | The number of connections with failed authentication per second.
failed-authentication-total | totalcounter |  | The total number of connections with failed authentication.
failed-reauthentication-rate | quantity |  | The number of failed re-authentication of connections per second.
failed-reauthentication-total | totalcounter |  | The total number of failed re-authentication of connections.
incoming-byte-rate | quantity | bytes | The number of bytes read off all sockets per second.
incoming-byte-total | totalcounter | bytes | The total number of bytes read off all sockets.
io-ratio | quantity |  | The fraction of time the I/O thread spent doing I/O.
io-time-ns-avg | timeticks | nanoseconds | The average length of time for I/O per select call in nanoseconds.
io-wait-ratio | quantity |  | The fraction of time the I/O thread spent waiting.
io-wait-time-ns-avg | timeticks | nanoseconds | The average length of time the I/O thread spent waiting for a socket ready for reads or writes in nanoseconds.
io-waittime-total | timeticks | milliseconds | The total time the I/O thread spent waiting.
iotime-total | timeticks | milliseconds | The total time the I/O thread spent doing I/O.
network-io-rate | quantity |  | The number of network operations (reads or writes) on all connections per second.
network-io-total | totalcounter |  | The total number of network operations (reads or writes) on all connections.
outgoing-byte-rate | quantity | bytes | The number of outgoing bytes sent to all servers per second.
outgoing-byte-total | totalcounter | bytes | The total number of outgoing bytes sent to all servers.
reauthentication-latency-avg | timeticks | milliseconds | The average latency observed due to re-authentication.
reauthentication-latency-max | timeticks | milliseconds | The max latency observed due to re-authentication.
request-rate | quantity |  | The number of requests sent per second.
request-total | totalcounter |  | The total number of requests sent.
request-size-avg | quantity | bytes | The average size of requests sent.
request-size-max | quantity | bytes | The maximum size of any request sent.
response-rate | quantity |  | The number of responses received per second.
response-total | totalcounter |  | The total number of responses received.
select-rate | quantity |  | The number of times the I/O layer checked for new I/O to perform per second.
select-total | totalcounter |  | The total number of times the I/O layer checked for new I/O to perform.
successful-authentication-no-reauth-total | totalcounter |  | The total number of connections with successful authentication where the client does not support re-authentication.
successful-authentication-rate | quantity |  | The number of connections with successful authentication per second.
successful-authentication-total | totalcounter |  | The total number of connections with successful authentication.
successful-reauthentication-rate | quantity |  | The number of successful re-authentication of connections per second.
successful-reauthentication-total | totalcounter |  | The total number of successful re-authentication of connections.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.admin.client_admin-client-metrics"
  mbean = "kafka.admin.client:client-id=*,type=admin-client-metrics"
  tag_keys = ["client-id"]
```

## admin-client-node-metrics

### Tags

Tag | Description
--- | ---
client-id |
node-id |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
incoming-byte-rate | quantity | bytes | The number of incoming bytes per second.
incoming-byte-total | totalcounter | bytes | The total number of incoming bytes.
outgoing-byte-rate | quantity | bytes | The number of outgoing bytes per second.
outgoing-byte-total | totalcounter | bytes | The total number of outgoing bytes.
request-latency-avg | timeticks | milliseconds | The average request latency.
request-latency-max | timeticks | milliseconds | The maximum request latency.
request-rate | quantity |  | The number of requests sent per second.
request-total | totalcounter |  | The total number of requests sent.
request-size-avg | quantity | bytes | The average size of requests sent.
request-size-max | quantity | bytes | The maximum size of any request sent.
response-rate | quantity |  | The number of responses received per second.
response-total | totalcounter |  | The total number of responses received.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.admin.client_admin-client-node-metrics"
  mbean = "kafka.admin.client:client-id=*,node-id=*,type=admin-client-node-metrics"
  tag_keys = ["client-id","node-id"]
```
