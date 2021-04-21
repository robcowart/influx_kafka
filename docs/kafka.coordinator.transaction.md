# kafka.coordinator.transaction

Applies to the following components:

* Kafka

## TransactionMarkerChannelManager

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
LogAppendRetryQueueSize | quantity |  | The size of the log append retry queue.
UnknownDestinationQueueSize | quantity |  | The size of the unknown destination queue.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.coordinator.transaction_TransactionMarkerChannelManager"
  mbean = "kafka.coordinator.transaction:name=*,type=TransactionMarkerChannelManager"
  field_name = "$1"
```
