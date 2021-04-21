# kafka.log

Applies to the following components:

* Kafka

## Log

### Tags

Tag | Description
--- | ---
topic | The topic name.
partition | The topic partition number.

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
Size | quantity | bytes | The size of the partition.
LogEndOffset | identifier |  | The offset value at the end of the partition.
LogStartOffset | identifier |  | The offset value at the start of the partition.
NumLogSegments | quantity |  | The number of log segments.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.log_Log"
  mbean = "kafka.log:name=*,partition=*,topic=*,type=Log"
  field_name = "$1"
  tag_keys = ["topic","partition"]
```

## LogFlushStats

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
LogFlushes | totalcounter |  | The number of log flushes.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.log_LogFlushStats"
  mbean = "kafka.log:name=LogFlushRateAndTimeMs,type=LogFlushStats"
  field_name = "LogFlushes"
  paths = ["Count"]
```

## LogCleaner

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
cleaner-recopy-percent | percent |  | Log cleaner recopy percentage.
DeadThreadCount | totalcounter |  | The count of dead threads.
max-buffer-utilization-percent | percent |  | The maximum buffer utilization.
max-clean-time-secs | timeticks | seconds | The maximum clean time.
max-compaction-delay-secs | timeticks | seconds | The maximum compaction delay.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.log_LogCleaner"
  mbean = "kafka.log:name=*,type=LogCleaner"
  field_name = "$1"
```

## LogCleanerManager

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
max-dirty-percent | percent |  | The maximum percentage of logs that are dirty.
OfflineLogDirectoryCount | quantity |  | The number of log directories that are offline.
time-since-last-run-ms | timeticks | milliseconds | The amount of time since the log cleaner was last run.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.log_LogCleanerManager"
  mbean = "kafka.log:name=*,type=LogCleanerManager"
  field_name = "$1"
```

## LogCleanerManager (logDirectory)

### Tags

Tag | Description
--- | ---
logDirectory | The path to the log directory.

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
uncleanable-bytes | quantity | bytes | The number of uncleanable bytes.
uncleanable-partitions-count | quantity |  | The number of uncleanable partitions.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.log_LogCleanerManager"
  mbean = "kafka.log:logDirectory=*,name=*,type=LogCleanerManager"
  field_name = "$2"
  tag_keys = ["logDirectory"]
```

## LogManager

### Tags

Tag | Description
--- | ---
logDirectory | The path to the log directory.

### Values

Value | Semantic | Description
--- | --- | ---
LogDirectoryOffline | boolean | Indicates if the log directory is offline.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.log_LogManager"
  mbean = "kafka.log:logDirectory=*,name=*,type=LogManager"
  field_name = "$2"
  tag_keys = ["logDirectory"]
```
