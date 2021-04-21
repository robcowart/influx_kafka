# kafka.consumer

Applies to the following components:

* ksqlDB
* Kafka Connect
* Confluent Control Center
* Confluent Schema Registry

## consumer-coordinator-metrics

### Tags

Tag | Description
--- | ---
client-id |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
partition-lost-latency-max | timeticks | milliseconds | The max time taken for a partition-lost rebalance listener callback.
failed-rebalance-rate-per-hour | quantity |  | The number of failed rebalance events per hour.
commit-latency-avg | timeticks | milliseconds | The average time taken for a commit request.
rebalance-latency-total | timeticks | milliseconds | The total time this consumer has spent in successful rebalances since creation.
partition-assigned-latency-max | timeticks | milliseconds | The max time taken for a partition-assigned rebalance listener callback.
failed-rebalance-total |  |  | The total number of failed rebalance events.
last-heartbeat-seconds-ago | timeticks | seconds | The time since the last coordinator heartbeat was sent.
commit-latency-max | timeticks | milliseconds | The max time taken for a commit request.
join-time-avg | timeticks | milliseconds | The average time taken for a group rejoin.
sync-total | totalcounter |  | The total number of group syncs.
last-rebalance-seconds-ago | timeticks | seconds | The time since the last successful rebalance event.
partition-revoked-latency-max | timeticks | milliseconds | The max time taken for a partition-revoked rebalance listener callback.
heartbeat-total | totalcounter |  | The total number of heartbeats.
partition-assigned-latency-avg | timeticks | milliseconds | The average time taken for a partition-assigned rebalance listener callback.
rebalance-latency-avg | timeticks | milliseconds | The average time taken for a group to complete a successful rebalance, which may be composed of several failed re-trials until it succeeded.
join-total | totalcounter |  | The total number of group joins.
join-time-max | timeticks | milliseconds | The max time taken for a group rejoin.
sync-time-avg | timeticks | milliseconds | The average time taken for a group sync.
join-rate | quantity |  | The number of group joins per second.
assigned-partitions | quantity |  | The number of partitions currently assigned to this consumer.
commit-rate | quantity |  | The number of commit calls per second.
partition-revoked-latency-avg | timeticks | milliseconds | The average time taken for a partition-revoked rebalance listener callback.
rebalance-total | totalcounter |  | The total number of successful rebalance events, each event is composed of several failed re-trials until it succeeded.
heartbeat-rate | quantity |  | The number of heartbeats per second.
partition-lost-latency-avg | timeticks | milliseconds | The average time taken for a partition-lost rebalance listener callback.
rebalance-latency-max | timeticks | milliseconds | The max time taken for a group to complete a successful rebalance, which may be composed of several failed re-trials until it succeeded.
sync-time-max | timeticks | milliseconds | The max time taken for a group sync.
rebalance-rate-per-hour | quantity |  | The number of successful rebalance events per hour, each event is composed of several failed re-trials until it succeeded.
commit-total | totalcounter |  | The total number of commit calls.
heartbeat-response-time-max | timeticks | milliseconds | The max time taken to receive a response to a heartbeat request.
sync-rate | quantity |  | The number of group syncs per second.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.consumer_consumer-coordinator-metrics"
  mbean = "kafka.consumer:client-id=*,type=consumer-coordinator-metrics"
  tag_keys = ["client-id"]
```

## consumer-metrics

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
io-time-ns-avg | quantity | nanoseconds | The average length of time for I\/O per select call in nanoseconds.
io-wait-ratio | quantity |  | The fraction of time the I/O thread spent waiting.
io-wait-time-ns-avg | quantity | nanoseconds | The average length of time the I/O thread spent waiting for a socket ready for reads or writes in nanoseconds.
io-waittime-total | totalcounter | milliseconds | The total time the I/O thread spent waiting.
iotime-total | totalcounter | milliseconds | The total time the I/O thread spent doing I/O.
last-poll-seconds-ago | timeticks | seconds | The number of seconds since the last poll() invocation.
network-io-rate | quantity |  | The number of network operations (reads or writes) on all connections per second.
network-io-total | totalcounter |  | The total number of network operations (reads or writes) on all connections.
outgoing-byte-rate | quantity | bytes | The number of outgoing bytes sent to all servers per second.
outgoing-byte-total | totalcounter | bytes | The total number of outgoing bytes sent to all servers.
poll-idle-ratio-avg | quantity |  | The average fraction of time the consumer's poll() is idle as opposed to waiting for the user code to process records.
reauthentication-latency-avg | quantity | milliseconds | The average latency observed due to re-authentication.
reauthentication-latency-max | quantity | milliseconds | The max latency observed due to re-authentication.
request-rate | quantity |  | The number of requests sent per second.
request-size-avg | quantity | bytes | The average size of requests sent.
request-size-max | quantity | bytes | The maximum size of any request sent.
request-total | totalcounter |  | The total number of requests sent.
response-rate | quantity |  | The number of responses received per second.
response-total | totalcounter |  | The total number of responses received.
select-rate | quantity |  | The number of times the I/O layer checked for new I/O to perform per second.
select-total | totalcounter |  | The total number of times the I\/O layer checked for new I\/O to perform.
successful-authentication-no-reauth-total | totalcounter |  | The total number of connections with successful authentication where the client does not support re-authentication.
successful-authentication-rate | quantity |  | The number of connections with successful authentication per second.
successful-authentication-total | totalcounter |  | The total number of connections with successful authentication.
successful-reauthentication-rate | quantity |  | The number of successful re-authentication of connections per second.
successful-reauthentication-total | totalcounter |  | The total number of successful re-authentication of connections.
time-between-poll-avg | quantity | milliseconds | The average delay between invocations of poll().
time-between-poll-max | quantity | milliseconds | The max delay between invocations of poll().

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.consumer_consumer-metrics"
  mbean = "kafka.consumer:client-id=*,type=consumer-metrics"
  tag_keys = ["client-id"]
```

## consumer-node-metrics

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
  name = "kafka.consumer_consumer-node-metrics"
  mbean = "kafka.consumer:client-id=*,node-id=*,type=consumer-node-metrics"
  tag_keys = ["client-id","node-id"]
```

## consumer-fetch-manager-metrics (client)

### Tags

Tag | Description
--- | ---
client-id |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
bytes-consumed-rate | quantity | bytes | The average number of bytes consumed per second.
bytes-consumed-total | totalcounter | bytes | The total number of bytes consumed.
fetch-latency-avg | quantity | milliseconds | The average time taken for a fetch request.
fetch-latency-max | quantity | milliseconds | The max time taken for any fetch request.
fetch-rate | quantity |  | The number of fetch requests per second.
fetch-total | totalcounter |  | The total number of fetch requests.
fetch-size-avg | quantity | bytes | The average number of bytes fetched per request.
fetch-size-max | quantity | bytes | The maximum number of bytes fetched per request.
fetch-throttle-time-avg | quantity | milliseconds | The average throttle time.
fetch-throttle-time-max | quantity | milliseconds | The maximum throttle time.
records-consumed-rate | quantity |  | The average number of records consumed per second.
records-consumed-total | totalcounter |  | The total number of records consumed.
records-lag-max | quantity |  | The maximum lag in terms of number of records for any partition in this window.
records-lead-min | quantity |  | The minimum lead in terms of number of records for any partition in this window.
records-per-request-avg | quantity |  | The average number of records in each request.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.consumer_consumer-fetch-manager-metrics"
  mbean = "kafka.consumer:client-id=*,type=consumer-fetch-manager-metrics"
  tag_keys = ["client-id"]
```

## consumer-fetch-manager-metrics (client/topic)

### Tags

Tag | Description
--- | ---
client-id |
topic |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
bytes-consumed-rate | quantity | bytes | The average number of bytes consumed per second for a topic.
bytes-consumed-total | totalcounter | bytes | The total number of bytes consumed for a topic.
fetch-size-avg | quantity | bytes | The average number of bytes fetched per request for a topic.
fetch-size-max | quantity | bytes | The maximum number of bytes fetched per request for a topic.
records-consumed-rate | quantity |  | The average number of records consumed per second for a topic.
records-consumed-total | totalcounter |  | The total number of records consumed for a topic.
records-per-request-avg | quantity |  | The average number of records in each request for a topic.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.consumer_consumer-fetch-manager-metrics_topic"
  mbean = "kafka.consumer:client-id=*,topic=*,type=consumer-fetch-manager-metrics"
  tag_keys = ["client-id","topic"]
```

## consumer-fetch-manager-metrics (client/topic/partition)

### Tags

Tag | Description
--- | ---
client-id |
topic |
partition |

### Values

Value | Semantic | Description
--- | --- | ---
preferred-read-replica | identifier | The current read replica for the partition, or -1 if reading from leader.
records-lag | quantity | The latest lag of the partition.
records-lag-avg | quantity | The average lag of the partition.
records-lag-max | quantity | The max lag of the partition.
records-lead | quantity | The latest lead of the partition.
records-lead-avg | quantity | The average lead of the partition.
records-lead-min | quantity | The min lead of the partition.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.consumer_consumer-fetch-manager-metrics_partition"
  mbean = "kafka.consumer:client-id=*,partition=*,topic=*,type=consumer-fetch-manager-metrics"
  tag_keys = ["client-id","topic","partition"]
```
