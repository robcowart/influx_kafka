# org.eclipse.jetty.util.thread

Applies to the following components:

* Confluent Control Center
* Confluent Schema Registry
* Confluent REST Proxy

## queuedthreadpool

### Tags

Tag | Description
--- | ---
id |

### Values

Value | Semantic | Description
--- | --- | --- | ---
busyThreads | quantity | The number of busy threads in the pool.
idleThreads | quantity | The number of idle threads in the pool.
maxThreads | quantity | The maximum number of threads in the pool.
minThreads | quantity | The minimum number of threads in the pool.
queueSize | quantity | The size of the job queue.
reservedThreads | quantity | The the number of reserved threads in the pool.
threads | quantity | The number of threads in the pool.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "org.eclipse.jetty.util.thread_queuedthreadpool"
  mbean = "org.eclipse.jetty.util.thread:id=*,type=queuedthreadpool"
  paths = ["busyThreads","idleThreads","maxThreads","minThreads","queueSize","reservedThreads","threads"]
  tag_keys = ["id"]
```

## reservedthreadexecutor

### Tags

Tag | Description
--- | ---
id |

### Values

Value | Semantic | Description
--- | --- | --- | ---
available | quantity | The number of available reserved threads.
capacity | quantity | The maximum number of reserved threads.
pending | quantity | The number of pending reserved threads.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "org.eclipse.jetty.util.thread_reservedthreadexecutor"
  mbean = "org.eclipse.jetty.util.thread:id=*,type=reservedthreadexecutor"
  paths = ["available","capacity","pending"]
  tag_keys = ["id"]
```
