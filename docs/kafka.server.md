# kafka.server

Applies to the following components:

* Kafka

## BrokerTopicMetrics

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
BytesInPerSec | quantity | bytes | Bytes in rate.
BytesOutPerSec | quantity | bytes | Bytes out rate.
BytesRejectedPerSec | quantity | bytes | Bytes rejected rate.
FailedFetchRequestsPerSec | quantity |  | Failed fetch request rate.
FailedProduceRequestsPerSec | quantity |  | Failed produce request rate.
FetchMessageConversionsPerSec | quantity |  | Fetch message conversions rate.
InvalidOffsetOrSequenceRecordsPerSec | quantity |  | Invalid offset or sequence record rate.
InvalidMagicNumberRecordsPerSec | quantity |  | Invalid magic number records rate.
InvalidMessageCrcRecordsPerSec | quantity |  | Invalid message CRC records rate.
MessagesInPerSec | quantity |  | Messages in rate.
NoKeyCompactedTopicRecordsPerSec | quantity |  | No key compacted topic records rate.
ProduceMessageConversionsPerSec | quantity |  | Produce message conversion rate.
ReassignmentBytesInPerSec | quantity | bytes | Reassignment bytes in rate.
ReassignmentBytesOutPerSec | quantity | bytes | Reassignment bytes out rate.
ReplicationBytesInPerSec | quantity | bytes | Replication bytes in rate.
ReplicationBytesOutPerSec | quantity | bytes | Replication bytes out rate.
TotalFetchRequestsPerSec | quantity |  | Total fetch request rate.
TotalProduceRequestsPerSec | quantity |  | Total produce request rate.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_BrokerTopicMetrics"
  mbean = "kafka.server:name=*,type=BrokerTopicMetrics"
  paths = ["OneMinuteRate"]
  field_name = "$1"
```

## BrokerTopicMetrics (topic)

### Tags

Tag | Description
--- | ---
topic | The name of the topic.

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
BytesInPerSec | quantity | bytes | Bytes in rate.
BytesOutPerSec | quantity | bytes | Bytes out rate.
BytesRejectedPerSec | quantity | bytes | Bytes rejected rate.
FailedFetchRequestsPerSec | quantity |  | Failed fetch request rate.
FailedProduceRequestsPerSec | quantity |  | Failed produce request rate.
FetchMessageConversionsPerSec | quantity |  | Fetch message conversions rate.
InvalidOffsetOrSequenceRecordsPerSec | quantity |  | Invalid offset or sequence record rate.
InvalidMagicNumberRecordsPerSec | quantity |  | Invalid magic number records rate.
InvalidMessageCrcRecordsPerSec | quantity |  | Invalid message CRC records rate.
MessagesInPerSec | quantity |  | Messages in rate.
NoKeyCompactedTopicRecordsPerSec | quantity |  | No key compacted topic records rate.
ProduceMessageConversionsPerSec | quantity |  | Produce message conversion rate.
ReassignmentBytesInPerSec | quantity | bytes | Reassignment bytes in rate.
ReassignmentBytesOutPerSec | quantity | bytes | Reassignment bytes out rate.
ReplicationBytesInPerSec | quantity | bytes | Replication bytes in rate.
ReplicationBytesOutPerSec | quantity | bytes | Replication bytes out rate.
TotalFetchRequestsPerSec | quantity |  | Total fetch request rate.
TotalProduceRequestsPerSec | quantity |  | Total produce request rate.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_BrokerTopicMetrics_topic"
  mbean = "kafka.server:name=*,topic=*,type=BrokerTopicMetrics"
  paths = ["OneMinuteRate"]
  field_name = "$1"
  tag_keys = ["topic"]
```

## FetcherLagMetrics

### Tags

Tag | Description
--- | ---
clientId |
topic |
partition |

### Values

Value | Semantic | Description
--- | --- | ---
ConsumerLag | quantity | The amount of consumer lag.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_FetcherLagMetrics"
  mbean = "kafka.server:clientId=*,name=*,partition=*,topic=*,type=FetcherLagMetrics"
  field_name = "$2"
  tag_keys = ["clientId","topic","partition"]
```

## ReplicaManager

### Values

Value | Semantic | Description
--- | --- | ---
AtMinIsrPartitionCount | quantity | The number of partitions at minimum ISR.
FailedIsrUpdatesPerSec | quantity | The rate of failed ISR updates.
IsrExpandsPerSec | quantity | The rate of ISR expands.
IsrShrinksPerSec | quantity | The rate of ISR shrinks.
LeaderCount | quantity | The number of leaders.
OfflineReplicaCount | quantity | The number of offline replicas.
PartitionCount | quantity | The number of partitions.
ReassigningPartitions | quantity | The number of partitions reassigning.
UnderReplicatedPartitions | quantity | The number of under-replicated partitions.
UnderMinIsrPartitionCount | quantity | The number partitions under the minimum ISR.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_ReplicaManager"
  mbean = "kafka.server:name=*,type=ReplicaManager"
  paths = ["OneMinuteRate","Value"]
  field_name = "$1"
```

## DelayedOperationPurgatory

### Tags

Tag | Description
--- | ---
delayedOperation | The name of the delayed operation.

### Values

Value | Semantic | Description
--- | --- | ---
NumDelayedOperations | quantity | The number of delayed operations.
PurgatorySize | quantity | The size of the delayed operation purgatory.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_DelayedOperationPurgatory"
  mbean = "kafka.server:delayedOperation=*,name=*,type=DelayedOperationPurgatory"
  field_name = "$2"
  tag_keys = ["delayedOperation"]
```

## FetcherStats

### Tags

Tag | Description
--- | ---
brokerHost | The broker host.
brokerPort | The broker port number.
clientId | The ID of the client.

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
BytesPerSec | quantity | bytes | Byte rate.
RequestsPerSec | quantity |  | Request rate.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_FetcherStats"
  mbean = "kafka.server:brokerHost=*,brokerPort=*,clientId=*,name=*,type=FetcherStats"
  paths = ["OneMinuteRate"]
  field_name = "$4"
  tag_keys = ["brokerHost","brokerPort","clientId"]
```

## SessionExpireListener

### Values

Value | Semantic | Description
--- | --- | ---
ZooKeeperAuthFailuresPerSec | quantity | ZooKeeper authentication failure rate.
ZooKeeperDisconnectsPerSec | quantity | ZooKeeper disconnect rate.
ZooKeeperExpiresPerSec | quantity | ZooKeeper expiration rate.
ZooKeeperReadOnlyConnectsPerSec | quantity | ZooKeeper read-only connection rate.
ZooKeeperSaslAuthenticationsPerSec| quantity | ZooKeeper SASL authentication rate.
ZooKeeperSyncConnectsPerSec | quantity | ZooKeeper synchronization connection rate.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_SessionExpireListener"
  mbean = "kafka.server:name=*,type=SessionExpireListener"
  paths = ["OneMinuteRate"]
  field_name = "$1"
```

## DelayedFetchMetrics

### Tags

Tag | Description
--- | ---
fetcherType | The type of fetcher.

### Values

Value | Semantic | Description
--- | --- | ---
ExpiresPerSec | quantity | The expiration rate.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_DelayedFetchMetrics"
  mbean = "kafka.server:fetcherType=*,name=*,type=DelayedFetchMetrics"
  paths = ["OneMinuteRate"]
  field_name = "$2"
  tag_keys = ["fetcherType"]
```

## ReplicaAlterLogDirsManager

### Tags

Tag | Description
--- | ---
clientId | The ID of the client.

### Values

Value | Semantic | Description
--- | --- | ---
DeadThreadCount | quantity | The number of dead threads.
FailedPartitionsCount | quantity | The number of failed partitions.
MaxLag | quantity | The maximum lag.
MinFetchRate | quantity | The minimum fetch rate.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_ReplicaAlterLogDirsManager"
  mbean = "kafka.server:clientId=*,name=*,type=ReplicaAlterLogDirsManager"
  field_name = "$2"
  tag_keys = ["clientId"]
```

## KafkaServer

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
BrokerState | identifier |  | The state of the broker.
linux-disk-read-bytes | totalcounter | bytes | The total count of bytes read from disk.
linux-disk-write-bytes | totalcounter | bytes | The total count of bytes written to disk.
yammer-metrics-count | quantity |  | The number of yammer metrics.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_KafkaServer"
  mbean = "kafka.server:name=*,type=KafkaServer"
  field_name = "$1"
```

## ReplicaFetcherManager

### Tags

Tag | Description
--- | ---
clientId | The ID of the client.

### Values

Value | Semantic | Description
--- | --- | ---
DeadThreadCount | quantity | The number of dead threads.
FailedPartitionsCount | quantity | The number of failed partitions.
MaxLag | quantity | The maximum lag.
MinFetchRate | quantity | The minimum fetch rate.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_ReplicaFetcherManager"
  mbean = "kafka.server:clientId=*,name=*,type=ReplicaFetcherManager"
  field_name = "$2"
  tag_keys = ["clientId"]
```

## FetchSessionCache

### Values

Value | Semantic | Description
--- | --- | ---
IncrementalFetchSessionEvictionsPerSec | quantity | The incremental fetch session eviction rate.
NumIncrementalFetchPartitionsCached | quantity | The number of incremental fetch partitions cached.
NumIncrementalFetchSessions | quantity | The number of incremental fetch session.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_FetchSessionCache"
  mbean = "kafka.server:name=*,type=FetchSessionCache"
  paths = ["OneMinuteRate","Value"]
  field_name = "$1"
```

## ZooKeeperClientMetrics

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
ZooKeeperRequestLatencyMsMax | timeticks | milliseconds | The maximum ZooKeeper request latency.
ZooKeeperRequestLatencyMsMean | timeticks | milliseconds | The average ZooKeeper request latency.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_ZooKeeperClientMetrics"
  mbean = "kafka.server:name=ZooKeeperRequestLatencyMs,type=ZooKeeperClientMetrics"
  paths = ["Max","Mean"]
  field_prefix = "$1"
```

## KafkaRequestHandlerPool

### Values

Value | Semantic | Description
--- | --- | ---
RequestHandlerAvgIdlePercent | percent | The average percentage of time that the request handler is idle.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_KafkaRequestHandlerPool"
  mbean = "kafka.server:name=RequestHandlerAvgIdlePercent,type=KafkaRequestHandlerPool"
  paths = ["OneMinuteRate"]
  field_name = "RequestHandlerAvgIdlePercent"
```

## socket-server-metrics

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
MemoryPoolAvgDepletedPercent | percent |  | The average memory pool depletion.
MemoryPoolDepletedTimeTotal | timeticks |  | The total memory pool depletion time.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_socket-server-metrics"
  mbean = "kafka.server:type=socket-server-metrics"
```

## socket-server-metrics

### Tags

Tag | Description
--- | ---
listener | The listener name.
networkProcessor | The network processor ID.

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
connection-close-rate | quantity |  | The number of connections closed per second.
connection-close-total | totalcounter |  | The total number of connections closed.
connection-count | quantity |  | The current number of active connections.
connection-creation-rate | quantity |  | The number of new connections established per second.
connection-creation-total | totalcounter |  | The total number of new connections established.
expired-connections-killed-count | totalcounter |  | The total number of expired connections killed.
failed-authentication-rate | quantity |  | The number of connections with failed authentication per second.
failed-authentication-total | totalcounter |  | The total number of connections with failed authentication.
failed-reauthentication-rate | quantity |  | The number of failed re-authentication of connections per second.
failed-reauthentication-total | totalcounter |  | The total number of failed re-authentication of connections.
incoming-byte-rate | quantity | bytes | The number of bytes read off all sockets per second.
incoming-byte-total | totalcounter | bytes | The total number of bytes read off all sockets.
io-ratio | percent |  | The fraction of time the I/O thread spent doing I/O.
io-time-ns-avg | timeticks | nanosecond | The average length of time for I/O per select call in nanoseconds.
io-wait-ratio | percent |  | The fraction of time the I/O thread spent waiting.
io-wait-time-ns-avg | timeticks | nanosecond | The average length of time the I/O thread spent waiting for a socket ready for reads or writes in nanoseconds.
io-waittime-total | timeticks | millisecond | The total time the I/O thread spent waiting.
iotime-total | timeticks | millisecond | The total time the I/O thread spent doing I/O.
network-io-rate | quantity |  | The number of network operations (reads or writes) on all connections per second.
network-io-total | totalcounter |  | The total number of network operations (reads or writes) on all connections.
outgoing-byte-rate | quantity | bytes | The number of outgoing bytes sent to all servers per second.
outgoing-byte-total | totalcounter | bytes | The total number of outgoing bytes sent to all servers.
reauthentication-latency-avg | timeticks | millisecond | The average latency observed due to re-authentication.
reauthentication-latency-max | timeticks | millisecond | The max latency observed due to re-authentication.
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
  name = "kafka.server_socket-server-metrics_listener"
  mbean = "kafka.server:listener=*,networkProcessor=*,type=socket-server-metrics"
  tag_keys = ["listener","networkProcessor"]
```

## socket-server-metrics (clientSoftware)

### Tags

Tag | Description
--- | ---
clientSoftwareName | Client software name.
clientSoftwareVersion | Client software version.
listener | The listener name.
networkProcessor | The network processor ID.

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
connections | quantity | The number of client connections.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_socket-server-metrics_clientSoftware"
  mbean = "kafka.server:clientSoftwareName=*,clientSoftwareVersion=*,listener=*,networkProcessor=*,type=socket-server-metrics"
  tag_keys = ["clientSoftwareName","clientSoftwareVersion","listener","networkProcessor"]
```

## replica-fetcher-metrics

### Tags

Tag | Description
--- | ---
broker-id | The broker ID.
fetcher-id | The fetcher ID.

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
io-ratio | percent |  | The fraction of time the I/O thread spent doing I/O.
io-time-ns-avg | timeticks | nanosecond | The average length of time for I/O per select call in nanoseconds.
io-wait-ratio | percent |  | The fraction of time the I/O thread spent waiting.
io-wait-time-ns-avg | timeticks | nanosecond | The average length of time the I/O thread spent waiting for a socket ready for reads or writes in nanoseconds.
io-waittime-total | timeticks | millisecond | The total time the I/O thread spent waiting.
iotime-total | timeticks | millisecond | The total time the I/O thread spent doing I/O.
network-io-rate | quantity |  | The number of network operations (reads or writes) on all connections per second.
network-io-total | totalcounter |  | The total number of network operations (reads or writes) on all connections.
outgoing-byte-rate | quantity | bytes | The number of outgoing bytes sent to all servers per second.
outgoing-byte-total | totalcounter | bytes | The total number of outgoing bytes sent to all servers.
reauthentication-latency-avg | timeticks | millisecond | The average latency observed due to re-authentication.
reauthentication-latency-max | timeticks | millisecond | The max latency observed due to re-authentication.
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
  name = "kafka.server_replica-fetcher-metrics"
  mbean = "kafka.server:broker-id=*,fetcher-id=*,type=replica-fetcher-metrics"
  tag_keys = ["broker-id","fetcher-id"]
```

## Fetch

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
queue-size | quantity |  | The size of the queue.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_Fetch"
  mbean = "kafka.server:type=Fetch"
```

## LeaderReplication

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
byte-rate | quantity | bytes | Tracking byte-rate for LeaderReplication.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_LeaderReplication"
  mbean = "kafka.server:type=LeaderReplication"
```

## Produce

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
queue-size | quantity |  | Tracks the size of the delay queue.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_Produce"
  mbean = "kafka.server:type=Produce"
```

## Request

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
queue-size | quantity |  | Tracks the size of the delay queue.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_Request"
  mbean = "kafka.server:type=Request"
```

## txn-marker-channel-metrics

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
io-ratio | percent |  | The fraction of time the I/O thread spent doing I/O.
io-time-ns-avg | timeticks | nanosecond | The average length of time for I/O per select call in nanoseconds.
io-wait-ratio | percent |  | The fraction of time the I/O thread spent waiting.
io-wait-time-ns-avg | timeticks | nanosecond | The average length of time the I/O thread spent waiting for a socket ready for reads or writes in nanoseconds.
io-waittime-total | timeticks | millisecond | The total time the I/O thread spent waiting.
iotime-total | timeticks | millisecond | The total time the I/O thread spent doing I/O.
network-io-rate | quantity |  | The number of network operations (reads or writes) on all connections per second.
network-io-total | totalcounter |  | The total number of network operations (reads or writes) on all connections.
outgoing-byte-rate | quantity | bytes | The number of outgoing bytes sent to all servers per second.
outgoing-byte-total | totalcounter | bytes | The total number of outgoing bytes sent to all servers.
reauthentication-latency-avg | timeticks | millisecond | The average latency observed due to re-authentication.
reauthentication-latency-max | timeticks | millisecond | The max latency observed due to re-authentication.
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
  name = "kafka.server_txn-marker-channel-metrics"
  mbean = "kafka.server:type=txn-marker-channel-metrics"
```

## group-coordinator-metrics

### Values

Value | Semantic | Description
--- | --- | ---
group-completed-rebalance-count | totalcounter | The total number of completed rebalance.
group-completed-rebalance-rate | quantity | The rate of completed rebalance.
offset-commit-count | totalcounter | The total number of committed offsets.
offset-commit-rate | quantity | The rate of committed offsets.
offset-expiration-count | totalcounter | The total number of expired offsets.
offset-expiration-rate | quantity | The rate of expired offsets.
offset-deletion-count | totalcounter | The total number of administrative deleted offsets.
offset-deletion-rate | quantity | The rate of administrative deleted offsets.
partition-load-time-avg | quantity | The avg time it took to load the partitions in the last 30sec.
partition-load-time-max | quantity | The max time it took to load the partitions in the last 30sec.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_group-coordinator-metrics"
  mbean = "kafka.server:type=group-coordinator-metrics"
```

## controller-channel-metrics

### Tags

Tag | Description
--- | ---
broker-id | The ID of the broker.

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
io-ratio | percent |  | The fraction of time the I/O thread spent doing I/O.
io-time-ns-avg | timeticks | nanosecond | The average length of time for I/O per select call in nanoseconds.
io-wait-ratio | percent |  | The fraction of time the I/O thread spent waiting.
io-wait-time-ns-avg | timeticks | nanosecond | The average length of time the I/O thread spent waiting for a socket ready for reads or writes in nanoseconds.
io-waittime-total | timeticks | millisecond | The total time the I/O thread spent waiting.
iotime-total | timeticks | millisecond | The total time the I/O thread spent doing I/O.
network-io-rate | quantity |  | The number of network operations (reads or writes) on all connections per second.
network-io-total | totalcounter |  | The total number of network operations (reads or writes) on all connections.
outgoing-byte-rate | quantity | bytes | The number of outgoing bytes sent to all servers per second.
outgoing-byte-total | totalcounter | bytes | The total number of outgoing bytes sent to all servers.
reauthentication-latency-avg | timeticks | millisecond | The average latency observed due to re-authentication.
reauthentication-latency-max | timeticks | millisecond | The max latency observed due to re-authentication.
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
  name = "kafka.server_controller-channel-metrics"
  mbean = "kafka.server:broker-id=*,type=controller-channel-metrics"
  tag_keys = ["broker-id"]
```

## transaction-coordinator-metrics

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
partition-load-time-avg | timeticks |  | The average partition load time.
partition-load-time-max | timeticks |  | The maximum partition load time.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.server_transaction-coordinator-metrics"
  mbean = "kafka.server:type=transaction-coordinator-metrics"
```
