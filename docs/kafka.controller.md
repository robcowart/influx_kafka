# kafka.controller

Applies to the following components:

* Kafka

## ControllerChannelManager

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
TotalQueueSize | quantity | bytes | The total queue size across all brokers.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerChannelManager"
  mbean = "kafka.controller:name=TotalQueueSize,type=ControllerChannelManager"
  field_name = "TotalQueueSize"
```

## ControllerChannelManager (per broker)

### Tags

Tag | Description
--- | ---
broker-id | The ID of the broker.

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
RequestQueueSize | quantity | bytes | The size of the request queue.
RequestCount | totalcounter |  | The total number of requests.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerChannelManager"
  mbean = "kafka.controller:broker-id=*,name=QueueSize,type=ControllerChannelManager"
  field_name = "RequestQueueSize"
  tag_keys = ["broker-id"]

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerChannelManager"
  mbean = "kafka.controller:broker-id=*,name=RequestRateAndQueueTimeMs,type=ControllerChannelManager"
  paths = ["Count"]
  field_name = "RequestCount"
  tag_keys = ["broker-id"]
```

## ControllerEventManager

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
EventQueueSize | quantity | bytes | The size of the event queue.
EventCount | totalcounter |  | The total number of events.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerEventManager"
  mbean = "kafka.controller:name=EventQueueSize,type=ControllerEventManager"
  field_name = "EventQueueSize"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerEventManager"
  mbean = "kafka.controller:name=EventQueueTimeMs,type=ControllerEventManager"
  paths = ["Count"]
  field_name = "EventCount"
```

## ControllerStats

### Values

Value | Semantic | Description
--- | ---  | ---
AutoLeaderBalanceCount | totalcounter | The count of auto-leader balances.
ControlledShutdownCount | totalcounter | The count of controlled shutdowns.
ControllerChangeCount | totalcounter | The count of controller changes.
ControllerShutdownCount | totalcounter | The count of controller shutdowns.
IsrChangeCount | totalcounter | The count of ISR changes.
LeaderAndIsrResponseReceivedCount | totalcounter | The count of leader and ISR responses received.
LeaderElectionCount | totalcounter | The count of leader elections.
ListPartitionReassignmentCount | totalcounter | The count of list partition reassignments.
LogDirChangeCount | totalcounter | The count of LogDir changes.
ManualLeaderBalanceCount | totalcounter | The count of manual leader balances.
PartitionReassignmentCount | totalcounter | The count of partition reassignments.
TopicChangeCount | totalcounter | The count of topic changes.
TopicDeletionCount | totalcounter | The count of topic deletions.
TopicUncleanLeaderElectionEnableCount | totalcounter | The count of times topic unclean leader election was enabled.
UncleanLeaderElectionEnableCount | totalcounter | The count of times unclean leader election was enabled.
UncleanLeaderElectionCount | totalcounter | The count of unclean leader elections.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=AutoLeaderBalanceRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "AutoLeaderBalanceCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=ControlledShutdownRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "ControlledShutdownCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=ControllerChangeRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "ControllerChangeCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=ControllerShutdownRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "ControllerShutdownCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=IsrChangeRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "IsrChangeCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=LeaderAndIsrResponseReceivedRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "LeaderAndIsrResponseReceivedCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=LeaderElectionRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "LeaderElectionCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=ListPartitionReassignmentRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "ListPartitionReassignmentCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=LogDirChangeRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "LogDirChangeCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=ManualLeaderBalanceRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "ManualLeaderBalanceCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=PartitionReassignmentRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "PartitionReassignmentCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=TopicChangeRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "TopicChangeCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=TopicDeletionRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "TopicDeletionCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=TopicUncleanLeaderElectionEnableRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "TopicUncleanLeaderElectionEnableCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=UncleanLeaderElectionEnableRateAndTimeMs,type=ControllerStats"
  paths = ["Count"]
  field_name = "UncleanLeaderElectionEnableCount"

[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_ControllerStats"
  mbean = "kafka.controller:name=UncleanLeaderElectionsPerSec,type=ControllerStats"
  paths = ["Count"]
  field_name = "UncleanLeaderElectionCount"
```

## KafkaController

### Values

Value | Semantic | Description
--- | --- | ---
ActiveControllerCount | quantity | The number of active controllers.
ControllerState | identifier | The state of the controller.
GlobalPartitionCount | quantity | The number of global partitions.
GlobalTopicCount | quantity | The number of global topics.
OfflinePartitionsCount | quantity | The number of offline partitions.
PreferredReplicaImbalanceCount | quantity | The number of preferred replicas imbalanced.
ReplicasIneligibleToDeleteCount | quantity | The number of replicas ineligible to be deleted.
ReplicasToDeleteCount | quantity | The number of replicas to be deleted.
TopicsIneligibleToDeleteCount | quantity | The number of topics ineligible to be deleted.
TopicsToDeleteCount | quantity | The number of topics to be deleted.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.controller_KafkaController"
  mbean = "kafka.controller:name=*,type=KafkaController"
  field_name = "$1"
```
