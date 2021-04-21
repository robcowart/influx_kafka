# kafka.cluster

Applies to the following components:

* Kafka

## Partition

### Tags

Tag | Description
--- | ---
topic | The topic name.
partition | The topic partition number.

### Values

Value | Semantic | Description
--- | --- | ---
AtMinIsr | boolean | Indicates whether the partition meets the minimum number of in-sync replicas.
InSyncReplicasCount | quantity | The number of in-sync replicas.
LastStableOffsetLag | quantity | The last stable offset lag.
ReplicasCount | quantity | The number of replicas.
UnderReplicated | boolean | Indicates whether the partition is under replicated.
UnderMinIsr | boolean | Indicates whether the partition fails to meet the minimum number of in-sync replicas.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.cluster_Partition"
  mbean = "kafka.cluster:name=*,partition=*,topic=*,type=Partition"
  field_name = "$1"
  tag_keys = ["topic","partition"]
```
