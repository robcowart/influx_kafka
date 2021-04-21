# kafka.network

Applies to the following components:

* Kafka

## RequestMetrics

### Tags

Tag | Description
--- | ---
request | The type of request.

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
MessageConversionsTimeMsMax | timeticks | milliseconds | The maximum message conversion time.
MessageConversionsTimeMsMean | timeticks | milliseconds | The average message conversion time.
LocalTimeMsMax | timeticks | milliseconds | The maximum local processing time.
LocalTimeMsMean | timeticks | milliseconds | The average local processing time.
RemoteTimeMsMax | timeticks | milliseconds | The maximum remote processing time.
RemoteTimeMsMean | timeticks | milliseconds | The average remote processing time.
RequestBytesMax | quantity | bytes | The maximum request bytes.
RequestBytesMean | quantity | bytes | The average request bytes.
RequestQueueTimeMsMax | timeticks | milliseconds | The maximum request queue time.
RequestQueueTimeMsMean | timeticks | milliseconds | The average request queue time.
ResponseQueueTimeMsMax | timeticks | milliseconds | The maximum response queue time.
ResponseQueueTimeMsMean | timeticks | milliseconds | The average response queue time.
ResponseSendTimeMsMax | timeticks | milliseconds | The maximum response send time.
ResponseSendTimeMsMean | timeticks | milliseconds | The average response send time.
TemporaryMemoryBytesMax | quantity | bytes | The maximum temporary memory used.
TemporaryMemoryBytesMean | quantity | bytes | The average temporary memory used.
ThrottleTimeMsMax | timeticks | milliseconds | The maximum throttle time.
ThrottleTimeMsMean | timeticks | milliseconds | The average throttle time.
TotalTimeMsMax | timeticks | milliseconds | The maximum total time.
TotalTimeMsMean | timeticks | milliseconds | The average total time.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.network_RequestMetrics"
  mbean = "kafka.network:name=*,request=*,type=RequestMetrics"
  paths = ["Max","Mean"]
  field_prefix = "$1"
  tag_keys = ["request"]
```

## RequestMetrics (ErrorCount)

### Tags

Tag | Description
--- | ---
error | The type of error.
request | The type of request.

### Values

Value | Semantic | Description
--- | --- | ---
ErrorCount | totalcounter | The total number of requests.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.network_RequestMetrics"
  mbean = "kafka.network:error=*,name=ErrorsPerSec,request=*,type=RequestMetrics"
  paths = ["Count"]
  field_name = "ErrorCount"
  tag_keys = ["error","request"]
```

## RequestMetrics (RequestCount)

### Tags

Tag | Description
--- | ---
request | The type of request.
version |

### Values

Value | Semantic | Description
--- | --- | ---
RequestCount | totalcounter | The total number of requests.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.network_RequestMetrics"
  mbean = "kafka.network:name=RequestsPerSec,request=*,type=RequestMetrics,version=*"
  paths = ["Count"]
  field_prefix = "RequestCount"
  tag_keys = ["request","version"]
```

## RequestChannel

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
RequestQueueSize | quantity | bytes | The size of the request queue.
ResponseQueueSize | quantity | bytes | The size of the response queue.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.network_RequestChannel"
  mbean = "kafka.network:name=*,type=RequestChannel"
  field_name = "$1"
```

## RequestChannel (processor)

### Tags

Tag | Description
--- | ---
processor |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
ResponseQueueSize | quantity | bytes | The size of the response queue.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.network_RequestChannel"
  mbean = "kafka.network:name=*,processor=*,type=RequestChannel"
  field_name = "$1"
  tag_keys = ["processor"]
```

## SocketServer

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
ControlPlaneExpiredConnectionsKilledCount | totalcounter |  | The total number of control plane expired connections killed.
ControlPlaneNetworkProcessorAvgIdlePercent | percent |  | The control plane network processor average idle time percentage.
ExpiredConnectionsKilledCount | totalcounter |  | The total number of expired connections killed.
MemoryPoolAvailable | quantity | bytes | The size of the memory pool that is available.
MemoryPoolUsed | quantity | bytes | The size of the memory pool that is used.
NetworkProcessorAvgIdlePercent | percent |  | The network processor average idle time percentage.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.network_SocketServer"
  mbean = "kafka.network:name=*,type=SocketServer"
  field_name = "$1"
```

## Processor

### Tags

Tag | Description
--- | ---
networkProcessor | The network processor ID.

### Values

Value | Semantic | Description
--- | --- | ---
IdlePercent | percent | The network processor idle time percentage.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.network_Processor"
  mbean = "kafka.network:name=*,networkProcessor=*,type=Processor"
  field_name = "$1"
  tag_keys = ["networkProcessor"]
```

## Acceptor

### Tags

Tag | Description
--- | ---
listener | The name of the listener.

### Values

Value | Semantic | Description
--- | --- | ---
AcceptorBlockedPercent | percent | The percentage of time that the acceptor was blocked.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.network_Acceptor"
  mbean = "kafka.network:listener=*,name=AcceptorBlockedPercent,type=Acceptor"
  paths = ["OneMinuteRate"]
  field_prefix = "AcceptorBlockedPercent"
  tag_keys = ["listener"]
```
