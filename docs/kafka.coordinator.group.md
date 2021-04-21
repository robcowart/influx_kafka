# kafka.coordinator.group

Applies to the following components:

* Kafka

## GroupMetadataManager

### Values

Value | Semantic | Description
--- | --- | ---
NumGroups | quantity | The number of groups.
NumGroupsDead | quantity | The number of dead groups.
NumGroupsEmpty | quantity | The number of empty groups.
NumGroupsStable | quantity | The number of stable groups.
NumGroupsCompletingRebalance | quantity | The number of groups completing rebalance.
NumGroupsPreparingRebalance | quantity | The number of groups preparing to rebalance.
NumOffsets | quantity | The number of offsets.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.coordinator.group_GroupMetadataManager"
  mbean = "kafka.coordinator.group:name=*,type=GroupMetadataManager"
  field_name = "$1"
```
