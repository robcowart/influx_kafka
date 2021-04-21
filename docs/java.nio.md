# java.nio

Applies to the following components:

* Zookeeper
* Kafka
* ksqlDB
* Kafka Connect
* Confluent Control Center
* Confluent Schema Registry
* Confluent REST Proxy

## BufferPool

### Tags

Tag | Description
--- | ---
name | Possible values incl. `direct`, `mapped`

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
Count | quantity |  | An estimate of the number of buffers in the pool.
MemoryUsed | quantity | bytes | An estimate of the memory that the JVM is using for this buffer pool.
TotalCapacity | quantity | bytes | An estimate of the total capacity of the buffers in this pool.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "java.nio"
  mbean = "java.nio:name=*,type=BufferPool"
  paths = ["TotalCapacity","MemoryUsed","Count"]
  tag_keys = ["name"]
```
