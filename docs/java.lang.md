# java.lang

Provides classes that are fundamental to the design of the Java programming language.

Applies to the following components:

* Zookeeper
* Kafka
* ksqlDB
* Kafka Connect
* Confluent Control Center
* Confluent Schema Registry
* Confluent REST Proxy

## ClassLoading

### Values

Value | Semantic | Description
--- | --- | ---
LoadedClassCount | quantity | The number of classes currently loaded in the JVM.
TotalLoadedClassCount | totalcounter | The number of classes that have been loaded since the JVM was started.
UnloadedClassCount | totalcounter | Classes are unloaded when the Classloader that loaded them is garbage-collected. This is the number of classes that have been unloaded from the JVM since it was started.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "java.lang_ClassLoading"
  mbean = "java.lang:type=ClassLoading"
  paths = ["LoadedClassCount","UnloadedClassCount","TotalLoadedClassCount"]
```

## Compilation

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
TotalCompilationTime | timeticks | milliseconds | The accumulated time spent in just-in-time (JIT) compilation.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "java.lang_Compilation"
  mbean = "java.lang:type=Compilation"
  paths = ["TotalCompilationTime"]
```

## GarbageCollector

### Tags

Tag | Description
--- | ---
name | Possible values incl. `G1 Old Generation`, `G1 Young Generation`

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
CollectionCount | totalcounter |  | The number of garbage collection events fired since the JVM was launched.
CollectionTime | timeticks | milliseconds | The total time spent doing garbage collection.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "java.lang_GarbageCollector"
  mbean = "java.lang:name=*,type=GarbageCollector"
  paths = ["CollectionTime","CollectionCount"]
  tag_keys = ["name"]
```

## Memory

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
HeapMemoryUsage.committed | quantity | bytes | The current heap memory allocated. This amount of memory is guaranteed for the JVM to use.
HeapMemoryUsage.init | quantity | bytes | The amount of heap that the JVM initially requests from the operating system.
HeapMemoryUsage.max | quantity | bytes | The maximum amount of heap that can be used for memory management. This amount of memory is not guaranteed to be available if it is greater than the amount of committed memory. The JVM may fail to allocate memory even if the amount of used memory does not exceed this maximum size.
HeapMemoryUsage.used | quantity | bytes | The current heap memory used.
NonHeapMemoryUsage.committed | quantity | bytes | The current non-heap memory allocated. This amount of memory is guaranteed for the JVM to use.
NonHeapMemoryUsage.init | quantity | bytes | The amount of non-heap that the JVM initially requests from the operating system.
NonHeapMemoryUsage.max | quantity | bytes | The maximum amount of non-heap that can be used for memory management. This amount of memory is not guaranteed to be available if it is greater than the amount of committed memory. The JVM may fail to allocate memory even if the amount of used memory does not exceed this maximum size.
NonHeapMemoryUsage.used | quantity | bytes | The current non-heap memory used.
ObjectPendingFinalizationCount | quantity |  | Approximate number of objects that are pending finalization.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "java.lang_Memory"
  mbean = "java.lang:type=Memory"
  paths = ["ObjectPendingFinalizationCount","HeapMemoryUsage","NonHeapMemoryUsage"]
```

## OperatingSystem

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
AvailableProcessors | quantity |  | The number of available CPU cores.
CommittedVirtualMemorySize | quantity | bytes | The amount of memory that is guaranteed to be available for use by the JVM.
FreePhysicalMemorySize | quantity | bytes | The amount of free physical memory in the host (`free = total – (used + shared + cached + buffered)`).
FreeSwapSpaceSize | quantity | bytes | The amount of swap memory still available in the host.
MaxFileDescriptorCount | quantity |  | The number of file descriptors that can be opened in the same process, as determined by the operating system.
OpenFileDescriptorCount | quantity |  | The current number of opened file descriptors. If this reaches the `MaxFileDescriptorCount`, the application will throw an `IOException: Too many open files`.
ProcessCpuLoad | quantity |  | The CPU load of this process.
ProcessCpuTime | timeticks | nanoseconds | The time the CPU has spent running this process.
SystemCpuLoad | quantity |  | Represents the current CPU load of the host system.
SystemLoadAverage | quantity |  | The average load of the host system.
TotalPhysicalMemorySize | quantity | bytes | The host memory size.
TotalSwapSpaceSize | quantity | bytes | The host swap memory size.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "java.lang_OperatingSystem"
  mbean = "java.lang:type=OperatingSystem"
  paths = ["OpenFileDescriptorCount","CommittedVirtualMemorySize","FreePhysicalMemorySize","SystemLoadAverage","ProcessCpuLoad","FreeSwapSpaceSize","TotalPhysicalMemorySize","TotalSwapSpaceSize","ProcessCpuTime","MaxFileDescriptorCount","SystemCpuLoad","AvailableProcessors"]
```

## Runtime

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
StartTime | epochticks | milliseconds | Time JVM started in the Unix Epoch format.
Uptime | timeticks | milliseconds | Number of milliseconds the JVM has been running.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "java.lang_Runtime"
  mbean = "java.lang:type=Runtime"
  paths = ["Uptime","StartTime"]
```

## Threading

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
CurrentThreadCpuTime | timeticks | nanoseconds | The total CPU time for the current thread.
CurrentThreadUserTime | timeticks | nanoseconds | The CPU time that the current thread has executed in user mode.
DaemonThreadCount | quantity |  | The current number of live daemon threads.
PeakThreadCount | quantity |  | The peak live thread count since the JVM started or peak was reset.
ThreadCount | quantity |  | The current number of live threads including both daemon and non-daemon threads.
TotalStartedThreadCount | totalcounter |  | The total number of threads created and also started since the JVM started.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "java.lang_Threading"
  mbean = "java.lang:type=Threading"
  paths = ["TotalStartedThreadCount","CurrentThreadUserTime","PeakThreadCount","CurrentThreadCpuTime","ThreadCount","DaemonThreadCount"]
```

## MemoryPool

### Tags

Tag | Description
--- | ---
name | Possible values incl. `Code Cache`, `CodeHeap 'non-nmethods'`, `CodeHeap 'non-profiled nmethods'`, `CodeHeap 'profiled nmethods'`, `Compressed Class Space`, `G1 Eden Space`, `G1 Old Gen`, `G1 Survivor Space`, `Metaspace`

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
CollectionUsage.committed | quantity | bytes | The committed size of the memory pool after garbaged collection.
CollectionUsage.init | quantity | bytes | The initial size of the memory pool after garbaged collection.
CollectionUsage.max | quantity | bytes | The maximum size of the memory pool after garbaged collection.
CollectionUsage.used | quantity | bytes | The current size of the memory pool after garbaged collection.
PeakUsage.committed | quantity | bytes | The committed peak usage of a memory pool since the JVM was started or the peak was reset.
PeakUsage.init | quantity | bytes | The initial peak usage of a memory pool since the JVM was started or the peak was reset.
PeakUsage.max | quantity | bytes | The maximum peak usage of a memory pool since the JVM was started or the peak was reset.
PeakUsage.used | quantity | bytes | The current peak usage of a memory pool since the JVM was started or the peak was reset.
Usage.committed | quantity | bytes | An estimate of the current memory committed to a memory pool.
Usage.init | quantity | bytes | An estimate of the initial usage of a memory pool.
Usage.max | quantity | bytes | An estimate of the maximum usage of a memory pool.
Usage.used | quantity | bytes | An estimate of the current usage of a memory pool. For a garbage-collected memory pool, the amount of used memory includes the memory occupied by all objects in the pool including both reachable and unreachable objects.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "java.lang_MemoryPool"
  mbean = "java.lang:name=*,type=MemoryPool"
  paths = ["Usage","PeakUsage","CollectionUsage"]
  tag_keys = ["name"]
```
