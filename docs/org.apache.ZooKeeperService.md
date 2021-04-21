# org.apache.ZooKeeperService

Applies to the following components:

* Zookeeper

## name#

### Tags

Tag | Description
--- | ---
nameX | where X is a number 0-9

### Values

Example Paths:

* `name0=StandaloneServer_port2181`

Value | Semantic | Unit | Description
--- | --- | --- | ---
AvgRequestLatency | timeticks | milliseconds | AvgRequestLatency
ClientPort | default |  | ClientPort (string)
DataDirSize | quantity | bytes | DataDirSize
FsyncThresholdExceedCount |  |  | FsyncThresholdExceedCount
JuteMaxBufferSize | quantity | bytes | JuteMaxBufferSize
LastClientResponseSize | quantity | bytes | LastClientResponseSize
LogDirSize | quantity | bytes | LogDirSize
MaxClientCnxnsPerHost | quantity |  | MaxClientCnxnsPerHost
MaxClientResponseSize | quantity | bytes | MaxClientResponseSize
MaxRequestLatency | timeticks | milliseconds | MaxRequestLatency
MaxSessionTimeout | timeticks |  | MaxSessionTimeout
MinClientResponseSize | quantity |  | MinClientResponseSize
MinRequestLatency | timeticks | milliseconds | MinRequestLatency
MinSessionTimeout | timeticks |  | MinSessionTimeout
NumAliveConnections | quantity |  | NumAliveConnections
PacketsReceived | totalcounter |  | PacketsReceived
SecureClientAddress | default |  | SecureClientAddress (string)
SecureClientPort | default |  | SecureClientPort (string)
StartTime | default |  | StartTime (string)
TickTime | timeticks |  | TickTime
TxnLogElapsedSyncTime | timeticks |  | TxnLogElapsedSyncTime
Version | default |  | Version (string)

### Values (Connections)

Example Paths:

* `name0=StandaloneServer_port2181,name1=Connections,name2=172.17.0.1,name3=0x1001d8e0f590028`
* `name0=ReplicatedServer_id2,name1=replica.2,name2=Leader,name3=Connections,name4=192.0.2.10,name5=0x2001ea62e9d0001`

Value | Semantic | Unit | Description
--- | --- | --- | ---
PacketsReceived | totalcounter |  | PacketsReceived
PacketsSent | totalcounter |  | PacketsSent
LastResponseTime | default |  | LastResponseTime (string)
EphemeralNodes | default |  | EphemeralNodes (string)
OutstandingRequests | quantity |  | OutstandingRequests
LastZxid | default |  | LastZxid (string)
LastCxid | default |  | LastCxid (string)
SourceIP | default |  | SourceIP (string)
SessionTimeout | timeticks |  | SessionTimeout
MinLatency | timeticks | milliseconds | MinLatency
AvgLatency | timeticks | milliseconds | AvgLatency
LastOperation | default |  | LastOperation (string)
StartedTime | default |  | StartedTime (string)
LastLatency | timeticks | milliseconds | LastLatency
SessionId | default |  | SessionId (string)
MaxLatency | timeticks | milliseconds | MaxLatency

### Values (InMemoryDataTree)

Example Paths:

* `name0=StandaloneServer_port2181,name1=InMemoryDataTree`
* `name0=ReplicatedServer_id2,name1=replica.2,name2=Leader,name3=InMemoryDataTree`

Value | Semantic | Unit | Description
--- | --- | --- | ---
LastZxid | default |  | LastZxid (string)
NodeCount | quantity |  | NodeCount
WatchCount | quantity |  | WatchCount

### Values (Leader)

Example Paths:

* `name0=ReplicatedServer_id2,name1=replica.2,name2=Leader`

Value | Semantic | Unit | Description
--- | --- | --- | ---
MaxSessionTimeout | timeticks |  | MaxSessionTimeout
AvgRequestLatency | timeticks | milliseconds | AvgRequestLatency
MaxRequestLatency | timeticks | milliseconds | MaxRequestLatency
ClientPort | default |  | ClientPort (string)
MinClientResponseSize | quantity |  | MinClientResponseSize
CurrentZxid | default |  | CurrentZxid (string)
MinRequestLatency | timeticks | milliseconds | MinRequestLatency
FsyncThresholdExceedCount |  |  | FsyncThresholdExceedCount
Version | default |  | Version (string)
ElectionTimeTaken | timeticks |  | ElectionTimeTaken
MaxClientResponseSize | quantity | bytes | MaxClientResponseSize
PacketsReceived | totalcounter |  | PacketsReceived
PacketsSent | totalcounter |  | PacketsSent
NumAliveConnections | quantity |  | NumAliveConnections
TickTime | timeticks |  | TickTime
JuteMaxBufferSize | quantity | bytes | JuteMaxBufferSize
StartTime | default |  | StartTime (string)
LastProposalSize | quantity | bytes | LastProposalSize
OutstandingRequests | quantity |  | OutstandingRequests
MaxClientCnxnsPerHost | quantity |  | MaxClientCnxnsPerHost
DataDirSize | quantity | bytes | DataDirSize
LastClientResponseSize | quantity | bytes | LastClientResponseSize
MinProposalSize | quantity | bytes | MinProposalSize
MaxProposalSize | quantity | bytes | MaxProposalSize
SecureClientAddress | default |  | SecureClientAddress (string)
MinSessionTimeout | timeticks |  | MinSessionTimeout
TxnLogElapsedSyncTime | timeticks |  | TxnLogElapsedSyncTime
SecureClientPort | default |  | SecureClientPort (string)
LogDirSize | quantity | bytes | LogDirSize

### Values

Example Paths:

* `name0=ReplicatedServer_id2,name1=replica.3`

Value | Semantic | Unit | Description
--- | --- | --- | ---
LearnerType | default |  | LearnerType (string)
Leader | boolean |  | Leader
ClientAddress | default |  | ClientAddress (string)
ElectionAddress | default |  | ElectionAddress (string)
QuorumAddress | default |  | QuorumAddress (string)
Name | default |  | Name (string)

### Values

Example Paths:

* `name0=ReplicatedServer_id2,name1=replica.2`

Value | Semantic | Unit | Description
--- | --- | --- | ---
MaxSessionTimeout | timeticks |  | MaxSessionTimeout
LearnerType | default |  | LearnerType (string)
Leader | boolean |  | Leader
TickTime | timeticks |  | TickTime
ConfigVersion | identifier |  | ConfigVersion
StartTime | default |  | StartTime (string)
ClientAddress | default |  | ClientAddress (string)
ElectionAddress | default |  | ElectionAddress (string)
MaxClientCnxnsPerHost | quantity |  | MaxClientCnxnsPerHost
PartOfEnsemble | boolean |  | PartOfEnsemble
InitLimit | quantity |  | InitLimit
QuorumAddress | default |  | QuorumAddress (string)
Name | default |  | Name (string)
MinSessionTimeout | timeticks |  | MinSessionTimeout
State | default |  | State (string)
ElectionType | identifier |  | ElectionType
Tick | quantity |  | Tick
SyncLimit | quantity |  | SyncLimit
QuorumSystemInfo | default |  | QuorumSystemInfo (string)

### Values ()

Example Paths:

* `name0=ReplicatedServer_id2`

Value | Semantic | Unit | Description
--- | --- | --- | ---
PortUnification | boolean |  | PortUnification
QuorumSize | quantity |  | QuorumSize
SslQuorum | boolean |  | SslQuorum
Name | default |  | Name (string)

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "org.apache.ZooKeeperService"
  mbean = "org.apache.ZooKeeperService:name0=*"
  tag_keys = ["name0"]
    
[[inputs.jolokia2_agent.metric]]
  name = "org.apache.ZooKeeperService"
  mbean = "org.apache.ZooKeeperService:name0=*,name1=*"
  tag_keys = ["name0","name1"]
    
[[inputs.jolokia2_agent.metric]]
  name = "org.apache.ZooKeeperService"
  mbean = "org.apache.ZooKeeperService:name0=*,name1=*,name2=*"
  tag_keys = ["name0","name1","name2"]
    
[[inputs.jolokia2_agent.metric]]
  name = "org.apache.ZooKeeperService"
  mbean = "org.apache.ZooKeeperService:name0=*,name1=*,name2=*,name3=*"
  tag_keys = ["name0","name1","name2","name3"]
    
[[inputs.jolokia2_agent.metric]]
  name = "org.apache.ZooKeeperService"
  mbean = "org.apache.ZooKeeperService:name0=*,name1=*,name2=*,name3=*,name4=*"
  tag_keys = ["name0","name1","name2","name3","name4"]
    
[[inputs.jolokia2_agent.metric]]
  name = "org.apache.ZooKeeperService"
  mbean = "org.apache.ZooKeeperService:name0=*,name1=*,name2=*,name3=*,name4=*,name5=*"
  tag_keys = ["name0","name1","name2","name3","name4","name5"]
```
