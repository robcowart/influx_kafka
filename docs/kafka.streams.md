# kafka.streams

Applies to the following components:

* Confluent Control Center

## stream-metrics

### Tags

Tag | Description
--- | ---
client-id |

### Values

Value | Semantic | Description
--- | --- | ---
alive-stream-threads | quantity | The current number of alive stream threads that are running or participating in rebalance.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.streams_stream-metrics"
  mbean = "kafka.streams:client-id=*,type=stream-metrics"
  paths = ["alive-stream-threads"]
  tag_keys = ["client-id"]
```

## stream-processor-node-metrics

### Tags

Tag | Description
--- | ---
processor-node-id |
task-id |
thread-id |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
idempotent-update-skip-rate | quantity |  | The average number of skipped idempotent updates per second.
idempotent-update-skip-total | totalcounter |  | The total number of skipped idempotent updates.
process-rate | quantity |  | The average number of calls to process per second.
process-total | totalcounter |  | The total number of calls to process.
record-e2e-latency-max | timeticks | milliseconds | The maximum end-to-end latency of a record, measuring by comparing the record timestamp with the system time when it has been fully processed by the node.
record-e2e-latency-min | timeticks | milliseconds | The minimum end-to-end latency of a record, measuring by comparing the record timestamp with the system time when it has been fully processed by the node.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.streams_stream-processor-node-metrics"
  mbean = "kafka.streams:processor-node-id=*,task-id=*,thread-id=*,type=stream-processor-node-metrics"
  tag_keys = ["processor-node-id","task-id","thread-id"]
```

## stream-record-cache-metrics

### Tags

Tag | Description
--- | ---
record-cache-id |
task-id |
thread-id |

### Values

Value | Semantic | Description
--- | --- | ---
hit-ratio-avg | percentage | The average cache hit ratio.
hit-ratio-max | percentage | The maximum cache hit ratio.
hit-ratio-min | percentage | The minimum cache hit ratio.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.streams_stream-record-cache-metrics"
  mbean = "kafka.streams:record-cache-id=*,task-id=*,thread-id=*,type=stream-record-cache-metrics"
  tag_keys = ["record-cache-id","task-id","thread-id"]
```

## stream-state-metrics (in-memory-lru-state)

### Tags

Tag | Description
--- | ---
in-memory-lru-state-id |
task-id |
thread-id |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
all-rate | quantity |  | The average number of calls to all per second.
all-latency-avg | timeticks | milliseconds | The average latency of calls to all.
all-latency-max | timeticks | milliseconds | The maximum latency of calls to all.
delete-rate | quantity |  | The average number of calls to delete per second.
delete-latency-avg | timeticks | milliseconds | The average latency of calls to delete.
delete-latency-max | timeticks | milliseconds | The maximum latency of calls to delete.
flush-rate | quantity |  | The average number of calls to flush per second.
flush-latency-avg | timeticks | milliseconds | The average latency of calls to flush.
flush-latency-max | timeticks | milliseconds | The maximum latency of calls to flush.
get-rate | quantity |  | The average number of calls to get per second.
get-latency-avg | timeticks | milliseconds | The average latency of calls to get.
get-latency-max | timeticks | milliseconds | The maximum latency of calls to get.
put-rate | quantity |  | The average number of calls to put per second.
put-latency-avg | timeticks | milliseconds | The average latency of calls to put.
put-latency-max | timeticks | milliseconds | The maximum latency of calls to put.
put-all-rate | quantity |  | The average number of calls to put-all per second.
put-all-latency-avg | timeticks | milliseconds | The average latency of calls to put-all.
put-all-latency-max | timeticks | milliseconds | The maximum latency of calls to put-all.
put-if-absent-rate | quantity |  | The average number of calls to put-if-absent per second.
put-if-absent-latency-avg | timeticks | milliseconds | The average latency of calls to put-if-absent.
put-if-absent-latency-max | timeticks | milliseconds | The maximum latency of calls to put-if-absent.
range-rate | quantity |  | The average number of calls to range per second.
range-latency-avg | timeticks | milliseconds | The average latency of calls to range.
range-latency-max | timeticks | milliseconds | The maximum latency of calls to range.
restore-rate | quantity |  | The average number of restorations per second.
restore-latency-avg | timeticks | milliseconds | The average latency of restorations.
restore-latency-max | timeticks | milliseconds | The maximum latency of restorations.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.streams_stream-state-metrics_in-memory-lru-state"
  mbean = "kafka.streams:in-memory-lru-state-id=*,task-id=*,thread-id=*,type=stream-state-metrics"
  tag_keys = ["in-memory-lru-state-id","task-id","thread-id"]
```

## stream-state-metrics (rocksdb-state)

### Tags

Tag | Description
--- | ---
rocksdb-state-id |
task-id |
thread-id |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
all-rate | quantity |  | The average number of calls to all per second.
all-latency-avg | timeticks | milliseconds | The average latency of calls to all.
all-latency-max | timeticks | milliseconds | The maximum latency of calls to all.
block-cache-data-hit-ratio | percent |  | Ratio of block cache hits for data relative to all lookups for data to the block cache.
block-cache-filter-hit-ratio | percent |  | Ratio of block cache hits for filters relative to all lookups for filters to the block cache.
block-cache-index-hit-ratio | percent |  | Ratio of block cache hits for indexes relative to all lookups for indexes to the block cache.
bytes-read-rate | quantity | bytes | Average number of bytes read per second from the RocksDB state store.
bytes-read-total | totalcounter | bytes | Total number of bytes read from the RocksDB state store.
bytes-read-compaction-rate | quantity | bytes | Average number of bytes read per second during compaction.
bytes-written-rate | quantity | bytes | Average number of bytes written per second to the RocksDB state store.
bytes-written-total | totalcounter | bytes | Total number of bytes written to the RocksDB state store.
bytes-written-compaction-rate | quantity | bytes | Average number of bytes written per second during compaction.
delete-rate | quantity |  | The average number of calls to delete per second.
delete-latency-avg | timeticks | milliseconds | The average latency of calls to delete.
delete-latency-max | timeticks | milliseconds | The maximum latency of calls to delete.
flush-rate | quantity |  | The average number of calls to flush per second.
flush-latency-avg | timeticks | milliseconds | The average latency of calls to flush.
flush-latency-max | timeticks | milliseconds | The maximum latency of calls to flush.
get-rate | quantity |  | The average number of calls to get per second.
get-latency-avg | timeticks | milliseconds | The average latency of calls to get.
get-latency-max | timeticks | milliseconds | The maximum latency of calls to get.
memtable-bytes-flushed-rate | quantity | bytes | Average number of bytes flushed per second from the memtable to disk.
memtable-bytes-flushed-total | totalcounter | bytes | Total number of bytes flushed from the memtable to disk.
memtable-hit-ratio | percent |  | Ratio of memtable hits relative to all lookups to the memtable.
number-file-errors-total | totalcounter |  | Total number of file errors occurred.
number-open-files | quantity |  | Number of currently open files.
put-all-rate | quantity |  | The average number of calls to put-all per second.
put-all-latency-avg | timeticks | milliseconds | The average latency of calls to put-all.
put-all-latency-max | timeticks | milliseconds | The maximum latency of calls to put-all.
put-if-absent-rate | quantity |  | The average number of calls to put-if-absent per second.
put-if-absent-latency-avg | timeticks | milliseconds | The average latency of calls to put-if-absent.
put-if-absent-latency-max | timeticks | milliseconds | The maximum latency of calls to put-if-absent.
put-rate | quantity |  | The average number of calls to put per second.
put-latency-avg | timeticks | milliseconds | The average latency of calls to put.
put-latency-max | timeticks | milliseconds | The maximum latency of calls to put.
range-rate | quantity |  | The average number of calls to range per second.
range-latency-avg | timeticks | milliseconds | The average latency of calls to range.
range-latency-max | timeticks | milliseconds | The maximum latency of calls to range.
restore-rate | quantity |  | The average number of restorations per second.
restore-latency-avg | timeticks | milliseconds | The average latency of restorations.
restore-latency-max | timeticks | milliseconds | The maximum latency of restorations.
write-stall-duration-avg | timeticks | milliseconds | Average duration of write stalls.
write-stall-duration-total | timeticks | milliseconds | Total duration of write stalls.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.streams_stream-state-metrics_rocksdb-state"
  mbean = "kafka.streams:rocksdb-state-id=*,task-id=*,thread-id=*,type=stream-state-metrics"
  tag_keys = ["rocksdb-state-id","task-id","thread-id"]
```

## stream-state-metrics (rocksdb-window-state)

### Tags

Tag | Description
--- | ---
rocksdb-window-state-id |
task-id |
thread-id |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
block-cache-data-hit-ratio | percent |  | Ratio of block cache hits for data relative to all lookups for data to the block cache.
block-cache-filter-hit-ratio | percent |  | Ratio of block cache hits for filters relative to all lookups for filters to the block cache.
block-cache-index-hit-ratio | percent |  | Ratio of block cache hits for indexes relative to all lookups for indexes to the block cache.
bytes-read-rate | quantity | bytes | Average number of bytes read per second from the RocksDB state store.
bytes-read-total | totalcounter | bytes | Total number of bytes read from the RocksDB state store.
bytes-read-compaction-rate | quantity | bytes | Average number of bytes read per second during compaction.
bytes-written-rate | quantity | bytes | Average number of bytes written per second to the RocksDB state store.
bytes-written-total | totalcounter | bytes | Total number of bytes written to the RocksDB state store.
bytes-written-compaction-rate | quantity | bytes | Average number of bytes written per second during compaction.
fetch-rate | quantity |  | The average number of calls to fetch per second.
fetch-latency-avg | timeticks | milliseconds | The average latency of calls to fetch.
fetch-latency-max | timeticks | milliseconds | The maximum latency of calls to fetch.
flush-rate | quantity |  | The average number of calls to flush per second.
flush-latency-avg | timeticks | milliseconds | The average latency of calls to flush.
flush-latency-max | timeticks | milliseconds | The maximum latency of calls to flush.
memtable-bytes-flushed-rate | quantity | bytes | Average number of bytes flushed per second from the memtable to disk.
memtable-bytes-flushed-total | totalcounter | bytes | Total number of bytes flushed from the memtable to disk.
memtable-hit-ratio | percent |  | Ratio of memtable hits relative to all lookups to the memtable.
number-file-errors-total | totalcounter |  | Total number of file errors occurred.
number-open-files | quantity |  | Number of currently open files.
put-rate | quantity |  | The average number of calls to put per second.
put-latency-avg | timeticks | milliseconds | The average latency of calls to put.
put-latency-max | timeticks | milliseconds | The maximum latency of calls to put.
restore-rate | quantity |  | The average number of restorations per second.
restore-latency-avg | timeticks | milliseconds | The average latency of restorations.
restore-latency-max | timeticks | milliseconds | The maximum latency of restorations.
write-stall-duration-avg | timeticks | milliseconds | Average duration of write stalls.
write-stall-duration-total | timeticks | milliseconds | Total duration of write stalls.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.streams_stream-state-metrics_rocksdb-window-state"
  mbean = "kafka.streams:rocksdb-window-state-id=*,task-id=*,thread-id=*,type=stream-state-metrics"
  tag_keys = ["rocksdb-window-state-id","task-id","thread-id"]
```

## stream-task-metrics

### Tags

Tag | Description
--- | ---
task-id |
thread-id |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
active-buffer-count | quantity |  | The count of buffered records that are polled from consumer and not yet processed for this active task.
active-process-ratio | quantity |  | The fraction of time the thread spent on processing this task among all assigned active tasks.
dropped-records-rate | quantity |  | The average number of dropped records per second.
dropped-records-total | totalcounter |  | The total number of dropped records.
enforced-processing-rate | quantity |  | The average number of occurrences of enforced-processing operations per second.
enforced-processing-total | totalcounter |  | The total number of occurrences of enforced-processing operations.
process-latency-avg | timeticks | milliseconds | The average latency of calls to process.
process-latency-max | timeticks | milliseconds | The maximum latency of calls to process.
process-rate | quantity |  | The average number of calls to process per second.
process-total | totalcounter |  | The total number of calls to process.
punctuate-latency-avg | timeticks | milliseconds | The average latency of calls to punctuate.
punctuate-latency-max | timeticks | milliseconds | The maximum latency of calls to punctuate.
punctuate-rate | quantity |  | The average number of calls to punctuate per second.
punctuate-total | totalcounter |  | The total number of calls to punctuate.
record-lateness-avg | timeticks | milliseconds | The observed average lateness of records, measured by comparing the record timestamp with the current stream time.
record-lateness-max | timeticks | milliseconds | The observed maximum lateness of records, measured by comparing the record timestamp with the current stream time.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.streams_stream-task-metrics"
  mbean = "kafka.streams:task-id=*,thread-id=*,type=stream-task-metrics"
  tag_keys = ["task-id","thread-id"]
```

## stream-thread-metrics

### Tags

Tag | Description
--- | ---
thread-id |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
commit-latency-avg | timeticks | milliseconds | The average commit latency.
commit-latency-max | timeticks | milliseconds | The maximum commit latency.
commit-ratio | percent |  | The fraction of time the thread spent on committing all tasks.
commit-rate | quantity |  | The average per-second number of calls to commit.
commit-total | totalcounter |  | The total number of calls to commit.
poll-rate | quantity |  | The average per-second number of calls to poll.
poll-total | totalcounter |  | The total number of calls to poll.
poll-latency-avg | timeticks | milliseconds | The average poll latency.
poll-latency-max | timeticks | milliseconds | The maximum poll latency.
poll-ratio | percent |  | The fraction of time the thread spent on polling records from consumer.
poll-records-avg | quantity |  | The average number of records polled from consumer within an iteration"
poll-records-max | quantity |  | The maximum number of records polled from consumer within an iteration.
process-latency-avg | timeticks | milliseconds | The average process latency.
process-latency-max | timeticks | milliseconds | The maximum process latency.
process-ratio | percent |  | The fraction of time the thread spent on processing active tasks.
process-rate | quantity |  | The average per-second number of calls to process.
process-total | totalcounter |  | The total number of calls to process.
process-records-avg | quantity |  | The average number of records processed within an iteration.
process-records-max | quantity |  | The maximum number of records processed within an iteration.
punctuate-latency-avg | timeticks | milliseconds | The average punctuate latency.
punctuate-latency-max | timeticks | milliseconds | The maximum punctuate latency.
punctuate-ratio | percent |  | The fraction of time the thread spent on punctuating active tasks.
punctuate-rate | quantity |  | The average per-second number of calls to punctuate.
punctuate-total | totalcounter |  | The total number of calls to punctuate.
task-closed-rate | quantity |  | The average per-second number of closed tasks.
task-closed-total | totalcounter |  | The total number of closed tasks.
task-created-rate | quantity |  | The average per-second number of newly created tasks.
task-created-total | totalcounter |  | The total number of newly created tasks.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.streams_stream-thread-metrics"
  mbean = "kafka.streams:thread-id=*,type=stream-thread-metrics"
  tag_keys = ["thread-id"]
```
