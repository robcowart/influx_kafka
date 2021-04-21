# confluent.controlcenter

Applies to the following components:

* Confluent Control Center

## consumer-group

### Tags

Tag | Description
--- | ---
groupId |

### Values

Value | Semantic | Description
--- | --- | ---
total-lag | quantity | Total consumer group lag across all topics and partitions.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "confluent.controlcenter_consumer-group"
  mbean = "confluent.controlcenter:groupId=*,type=consumer-group"
  tag_keys = ["groupId"]
```

## healthcheck

### Values

Value | Semantic | Description
--- | --- | --- | ---
missing-topic-configurations | quantity | The number of missing topic configurations.
cluster-offline | quantity | The number of clusters offline.
misconfigured-topics | quantity | The number of misconfigured topics.
broker-log-persistent-dir | quantity |
streams-status | quantity |

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "confluent.controlcenter_healthcheck"
  mbean = "confluent.controlcenter:type=healthcheck"
```

## jersey-metrics

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
kafka.acls.get.request-byte-rate | quantity | bytes | Bytes/second of incoming requests.
kafka.acls.get.request-error-rate | quantity |  | The average number of requests per second that resulted in HTTP error responses.
kafka.acls.get.request-latency-95 | timeticks | milliseconds | The 95th percentile request latency.
kafka.acls.get.request-latency-99 | timeticks | milliseconds | The 99th percentile request latency.
kafka.acls.get.request-latency-avg | timeticks | milliseconds | The average request latency.
kafka.acls.get.request-latency-max | timeticks | milliseconds | The maximum request latency.
kafka.acls.get.request-rate | quantity |  | The average number of HTTP requests per second.
kafka.acls.get.request-size-avg | quantity | bytes | The average request size in bytes.
kafka.acls.get.request-size-max | quantity | bytes | The maximum request size in bytes.
kafka.acls.get.response-byte-rate | quantity | bytes | Bytes/second of outgoing responses.
kafka.acls.get.response-rate | quantity |  | The average number of HTTP responses per second.
kafka.acls.get.response-size-avg | quantity | bytes | The average response size in bytes.
kafka.acls.get.response-size-max | quantity | bytes | The maximum response size in bytes.
kafka.get.topic-default-config.request-byte-rate | quantity | bytes | Bytes/second of incoming requests.
kafka.get.topic-default-config.request-error-rate | quantity |  | The average number of requests per second that resulted in HTTP error responses.
kafka.get.topic-default-config.request-latency-95 | timeticks | milliseconds | The 95th percentile request latency.
kafka.get.topic-default-config.request-latency-99 | timeticks | milliseconds | The 99th percentile request latency.
kafka.get.topic-default-config.request-latency-avg | timeticks | milliseconds | The average request latency.
kafka.get.topic-default-config.request-latency-max | timeticks | milliseconds | The maximum request latency.
kafka.get.topic-default-config.request-rate | quantity |  | The average number of HTTP requests per second.
kafka.get.topic-default-config.request-size-avg | quantity | bytes | The average request size in bytes.
kafka.get.topic-default-config.request-size-max | quantity | bytes | The maximum request size in bytes.
kafka.get.topic-default-config.response-byte-rate | quantity | bytes | Bytes/second of outgoing responses.
kafka.get.topic-default-config.response-rate | quantity |  | The average number of HTTP responses per second.
kafka.get.topic-default-config.response-size-avg | quantity | bytes | The average response size in bytes.
kafka.get.topic-default-config.response-size-max | quantity | bytes | The maximum response size in bytes.
kafka.get.topic-defaults.request-byte-rate | quantity | bytes | Bytes/second of incoming requests.
kafka.get.topic-defaults.request-error-rate | quantity |  | The average number of requests per second that resulted in HTTP error responses.
kafka.get.topic-defaults.request-latency-95 | timeticks | milliseconds | The 95th percentile request latency.
kafka.get.topic-defaults.request-latency-99 | timeticks | milliseconds | The 99th percentile request latency.
kafka.get.topic-defaults.request-latency-avg | timeticks | milliseconds | The average request latency.
kafka.get.topic-defaults.request-latency-max | timeticks | milliseconds | The maximum request latency.
kafka.get.topic-defaults.request-rate | quantity |  | The average number of HTTP requests per second.
kafka.get.topic-defaults.request-size-avg | quantity | bytes | The average request size in bytes.
kafka.get.topic-defaults.request-size-max | quantity | bytes | The maximum request size in bytes.
kafka.get.topic-defaults.response-byte-rate | quantity | bytes | Bytes/second of outgoing responses.
kafka.get.topic-defaults.response-rate | quantity |  | The average number of HTTP responses per second.
kafka.get.topic-defaults.response-size-avg | quantity | bytes | The average response size in bytes.
kafka.get.topic-defaults.response-size-max | quantity | bytes | The maximum response size in bytes.
kafka.topic.replicas.request-byte-rate | quantity | bytes | Bytes/second of incoming requests.
kafka.topic.replicas.request-error-rate | quantity |  | The average number of requests per second that resulted in HTTP error responses.
kafka.topic.replicas.request-latency-95 | timeticks | milliseconds | The 95th percentile request latency.
kafka.topic.replicas.request-latency-99 | timeticks | milliseconds | The 99th percentile request latency.
kafka.topic.replicas.request-latency-avg | timeticks | milliseconds | The average request latency.
kafka.topic.replicas.request-latency-max | timeticks | milliseconds | The maximum request latency.
kafka.topic.replicas.request-rate | quantity |  | The average number of HTTP requests per second.
kafka.topic.replicas.request-size-avg | quantity | bytes | The average request size in bytes.
kafka.topic.replicas.request-size-max | quantity | bytes | The maximum request size in bytes.
kafka.topic.replicas.response-byte-rate | quantity | bytes | Bytes/second of outgoing responses.
kafka.topic.replicas.response-rate | quantity |  | The average number of HTTP responses per second.
kafka.topic.replicas.response-size-avg | quantity | bytes | The average response size in bytes.
kafka.topic.replicas.response-size-max | quantity | bytes | The maximum response size in bytes.
kafka.topics.get.request-byte-rate | quantity | bytes | Bytes/second of incoming requests.
kafka.topics.get.request-error-rate | quantity |  | The average number of requests per second that resulted in HTTP error responses.
kafka.topics.get.request-latency-95 | timeticks | milliseconds | The 95th percentile request latency.
kafka.topics.get.request-latency-99 | timeticks | milliseconds | The 99th percentile request latency.
kafka.topics.get.request-latency-avg | timeticks | milliseconds | The average request latency.
kafka.topics.get.request-latency-max | timeticks | milliseconds | The maximum request latency.
kafka.topics.get.request-rate | quantity |  | The average number of HTTP requests per second.
kafka.topics.get.request-size-avg | quantity | bytes | The average request size in bytes.
kafka.topics.get.request-size-max | quantity | bytes | The maximum request size in bytes.
kafka.topics.get.response-byte-rate | quantity | bytes | Bytes/second of outgoing responses.
kafka.topics.get.response-rate | quantity |  | The average number of HTTP responses per second.
kafka.topics.get.response-size-avg | quantity | bytes | The average response size in bytes.
kafka.topics.get.response-size-max | quantity | bytes | The maximum response size in bytes.
metrics.topic.all.detail.request-byte-rate | quantity | bytes | Bytes/second of incoming requests.
metrics.topic.all.detail.request-error-rate | quantity |  | The average number of requests per second that resulted in HTTP error responses.
metrics.topic.all.detail.request-latency-95 | timeticks | milliseconds | The 95th percentile request latency.
metrics.topic.all.detail.request-latency-99 | timeticks | milliseconds | The 99th percentile request latency.
metrics.topic.all.detail.request-latency-avg | timeticks | milliseconds | The average request latency.
metrics.topic.all.detail.request-latency-max | timeticks | milliseconds | The maximum request latency.
metrics.topic.all.detail.request-rate | quantity |  | The average number of HTTP requests per second.
metrics.topic.all.detail.request-size-avg | quantity | bytes | The average request size in bytes.
metrics.topic.all.detail.request-size-max | quantity | bytes | The maximum request size in bytes.
metrics.topic.all.detail.response-byte-rate | quantity | bytes | Bytes/second of outgoing responses.
metrics.topic.all.detail.response-rate | quantity |  | The average number of HTTP responses per second.
metrics.topic.all.detail.response-size-avg | quantity | bytes | The average response size in bytes.
metrics.topic.all.detail.response-size-max | quantity | bytes | The maximum response size in bytes.
metrics.topic.replicas.request-byte-rate | quantity | bytes | Bytes/second of incoming requests.
metrics.topic.replicas.request-error-rate | quantity |  | The average number of requests per second that resulted in HTTP error responses.
metrics.topic.replicas.request-latency-95 | timeticks | milliseconds | The 95th percentile request latency.
metrics.topic.replicas.request-latency-99 | timeticks | milliseconds | The 99th percentile request latency.
metrics.topic.replicas.request-latency-avg | timeticks | milliseconds | The average request latency.
metrics.topic.replicas.request-latency-max | timeticks | milliseconds | The maximum request latency.
metrics.topic.replicas.request-rate | quantity |  | The average number of HTTP requests per second.
metrics.topic.replicas.request-size-avg | quantity | bytes | The average request size in bytes.
metrics.topic.replicas.request-size-max | quantity | bytes | The maximum request size in bytes.
metrics.topic.replicas.response-byte-rate | quantity | bytes | Bytes/second of outgoing responses.
metrics.topic.replicas.response-rate | quantity |  | The average number of HTTP responses per second.
metrics.topic.replicas.response-size-avg | quantity | bytes | The average response size in bytes.
metrics.topic.replicas.response-size-max | quantity | bytes | The maximum response size in bytes.
metrics.topic.size.request-byte-rate | quantity | bytes | Bytes/second of incoming requests.
metrics.topic.size.request-error-rate | quantity |  | The average number of requests per second that resulted in HTTP error responses.
metrics.topic.size.request-latency-95 | timeticks | milliseconds | The 95th percentile request latency.
metrics.topic.size.request-latency-99 | timeticks | milliseconds | The 99th percentile request latency.
metrics.topic.size.request-latency-avg | timeticks | milliseconds | The average request latency.
metrics.topic.size.request-latency-max | timeticks | milliseconds | The maximum request latency.
metrics.topic.size.request-rate | quantity |  | The average number of HTTP requests per second.
metrics.topic.size.request-size-avg | quantity | bytes | The average request size in bytes.
metrics.topic.size.request-size-max | quantity | bytes | The maximum request size in bytes.
metrics.topic.size.response-byte-rate | quantity | bytes | Bytes/second of outgoing responses.
metrics.topic.size.response-rate | quantity |  | The average number of HTTP responses per second.
metrics.topic.size.response-size-avg | quantity | bytes | The average response size in bytes.
metrics.topic.size.response-size-max | quantity | bytes | The maximum response size in bytes.
request-byte-rate | quantity | bytes | Bytes/second of incoming requests.
request-error-rate | quantity |  | The average number of requests per second that resulted in HTTP error responses.
request-latency-95 | timeticks | milliseconds | The 95th percentile request latency.
request-latency-99 | timeticks | milliseconds | The 99th percentile request latency.
request-latency-avg | timeticks | milliseconds | The average request latency.
request-latency-max | timeticks | milliseconds | The maximum request latency.
request-rate | quantity |  | The average number of HTTP requests per second.
request-size-avg | quantity | bytes | The average request size in bytes.
request-size-max | quantity | bytes | The maximum request size in bytes.
response-byte-rate | quantity | bytes | Bytes/second of outgoing responses.
response-rate | quantity |  | The average number of HTTP responses per second.
response-size-avg | quantity | bytes | The average response size in bytes.
response-size-max | quantity | bytes | The maximum response size in bytes.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "confluent.controlcenter_jersey-metrics"
  mbean = "confluent.controlcenter:type=jersey-metrics"
```

## jersey-metrics (http_status_code)

### Tags

Tag | Description
--- | ---
http_status_code |

### Values

Value | Semantic | Description
--- | --- | ---
kafka.acls.get.request-error-rate | quantity | The average number of Kafka ACLs GET requests per second.
kafka.get.topic-default-config.request-error-rate | quantity | The average number of Kafka topic default config requests per second.
kafka.get.topic-defaults.request-error-rate | quantity | The average number of Kafka GET topic defaults requests per second.
kafka.topic.replicas.request-error-rate | quantity | The average number of Kafka topic replicas requests per second.
kafka.topics.get.request-error-rate | quantity | The average number of Kafka topic GET requests per second.
metrics.topic.all.detail.request-error-rate | quantity | The average number of metrics topic all requests per second.
metrics.topic.replicas.request-error-rate | quantity | The average number of metrics topic replicas requests per second.
metrics.topic.size.request-error-rate | quantity | The average number of metrics topic size requests per second.
request-error-rate | quantity | The average number of requests per second.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "confluent.controlcenter_jersey-metrics_http_status_code"
  mbean = "confluent.controlcenter:http_status_code=*,type=jersey-metrics"
  tag_keys = ["http_status_code"]
```

## jetty-metrics

### Values

Value | Semantic | Description
--- | --- | ---
connections-accepted-rate | quantity | The average rate per second of accepted Jetty TCP connections.
connections-active | quantity | Total number of active Jetty TCP connections.
connections-closed-rate | quantity | The average rate per second of closed Jetty TCP connections.
connections-opened-rate | quantity | The average rate per second of opened Jetty TCP connections.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "confluent.controlcenter_jetty-metrics"
  mbean = "confluent.controlcenter:type=jetty-metrics"
```
