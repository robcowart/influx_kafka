# kafka.producer

Applies to the following components:

* Kafka
* Kafka Connect
* Confluent Control Center
* Confluent Schema Registry

## producer-metrics

### Tags

Tag | Description
--- | ---
client-id |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
batch-size-avg | quantity | bytes | The average number of bytes sent per partition per-request.
batch-size-max | quantity | bytes | The max number of bytes sent per partition per-request.
batch-split-rate | quantity |  | The average number of batch splits per second.
batch-split-total | totalcounter |  | The total number of batch splits.
buffer-available-bytes | quantity | bytes | The total amount of buffer memory that is not being used (either unallocated or in the free list).
buffer-exhausted-rate | quantity |  | The average per-second number of record sends that are dropped due to buffer exhaustion.
buffer-exhausted-total | totalcounter |  | The total number of record sends that are dropped due to buffer exhaustion.
buffer-total-bytes | quantity | bytes | The maximum amount of buffer memory the client can use (whether or not it is currently used).
bufferpool-wait-ratio | quantity |  | The fraction of time an appender waits for space allocation.
bufferpool-wait-time-total | totalcounter |  | The total time an appender waits for space allocation.
compression-rate-avg | quantity |  | The average compression rate of record batches.
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
io-wait-time-ns-avg | timeticks | nanoseconds | The average length of time the I/O thread spent waiting for a socket ready for reads or writes.
io-waittime-total | totalcounter |  | The total time the I/O thread spent waiting.
iotime-total | totalcounter |  | The total time the I/O thread spent doing I/O.
metadata-age | timeticks | seconds | The age in seconds of the current producer metadata being used.
network-io-rate | quantity |  | The number of network operations (reads or writes) on all connections per second.
network-io-total | totalcounter |  | The total number of network operations (reads or writes) on all connections.
outgoing-byte-rate | quantity | bytes | The number of outgoing bytes sent to all servers per second.
outgoing-byte-total | totalcounter | bytes | The total number of outgoing bytes sent to all servers.
produce-throttle-time-avg | timeticks | milliseconds | The average time in ms a request was throttled by a broker.
produce-throttle-time-max | timeticks | milliseconds | The maximum time a request was throttled by a broker.
reauthentication-latency-avg | timeticks | milliseconds | The average latency observed due to re-authentication.
reauthentication-latency-max | timeticks | milliseconds | The max latency observed due to re-authentication.
record-error-rate | quantity |  | The average per-second number of record sends that resulted in errors.
record-error-total | totalcounter |  | The total number of record sends that resulted in errors.
record-queue-time-avg | timeticks | milliseconds | The average time record batches spent in the send buffer.
record-queue-time-max | timeticks | milliseconds | The maximum time in ms record batches spent in the send buffer.
record-retry-rate | quantity |  | The average per-second number of retried record sends.
record-retry-total | totalcounter |  | The total number of retried record sends.
record-send-rate | quantity |  | The average number of records sent per second.
record-send-total | totalcounter |  | The total number of records sent.
record-size-avg | quantity | bytes | The average record size.
record-size-max | quantity | bytes | The maximum record size.
records-per-request-avg | quantity |  | The average number of records per request.
request-latency-avg | timeticks | milliseconds | The average request latency.
request-latency-max | timeticks | milliseconds | The maximum request latency.
request-rate | quantity |  | The number of requests sent per second.
request-size-avg | quantity | bytes | The average size of requests sent.
request-size-max | quantity | bytes | The maximum size of any request sent.
request-total | quantity |  | The total number of requests sent.
requests-in-flight | quantity |  | The current number of in-flight requests awaiting a response.
response-rate | quantity |  | The number of responses received per second.
response-total | totalcounter |  | The total number of responses received.
select-rate | quantity |  | The number of times the I/O layer checked for new I/O to perform per second.
select-total | totalcounter |  | The total number of times the I/O layer checked for new I/O to perform.
successful-authentication-no-reauth-total | quantity |  | The total number of connections with successful authentication where the client does not support re-authentication.
successful-authentication-rate | quantity |  | The number of connections with successful authentication per second.
successful-authentication-total | totalcounter |  | The total number of connections with successful authentication.
successful-reauthentication-rate | quantity |  | The number of successful re-authentication of connections per second.
successful-reauthentication-total | totalcounter |  | The total number of successful re-authentication of connections.
waiting-threads | quantity |  | The number of user threads blocked waiting for buffer memory to enqueue their records.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.producer_producer-metrics"
  mbean = "kafka.producer:client-id=*,type=producer-metrics"
  tag_keys = ["client-id"]
```

## producer-node-metrics

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
request-rate | quantity |  | The number of requests sent per second.
request-total | totalcounter |  | The total number of requests sent.
request-latency-avg | timeticks | milliseconds | The average request latency.
request-latency-max | timeticks | milliseconds | The maximum request latency.
request-size-avg | quantity | bytes | The average size of requests sent.
request-size-max | quantity | bytes | The maximum size of any request sent.
response-rate | quantity |  | The number of responses received per second.
response-total | totalcounter |  | The total number of responses received.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.producer_producer-node-metrics"
  mbean = "kafka.producer:client-id=*,node-id=*,type=producer-node-metrics"
  tag_keys = ["client-id","node-id"]
```

## producer-topic-metrics

### Tags

Tag | Description
--- | ---
client-id |
topic |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
byte-rate | quantity | bytes | The average number of bytes sent per second for a topic.
byte-total | quantity | bytes | The total number of bytes sent for a topic.
compression-rate | quantity |  | The average compression rate of record batches for a topic.
record-error-rate | quantity |  | The average per-second number of record sends that resulted in errors for a topic.
record-error-total | quantity |  | The total number of record sends that resulted in errors for a topic.
record-retry-rate | quantity |  | The average per-second number of retried record sends for a topic.
record-retry-total | quantity |  | The total number of retried record sends for a topic.
record-send-rate | quantity |  | The average number of records sent per second for a topic.
record-send-total | quantity |  | The total number of records sent for a topic.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.producer_producer-topic-metrics"
  mbean = "kafka.producer:client-id=*,topic=*,type=producer-topic-metrics"
  tag_keys = ["client-id","topic"]
```
