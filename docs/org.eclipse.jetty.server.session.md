# org.eclipse.jetty.server.session

Applies to the following components:

* Confluent Control Center
* Confluent Schema Registry
* Confluent REST Proxy

## defaultsessioncache

### Tags

Tag | Description
--- | ---
context |
id |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
sessionsCurrent | quantity |  | The number of sessions currently cached.
sessionsMax | quantity |  | The maximum number of sessions cached.
sessionsTotal | totalcounter |  | The total number of sessions cached.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "org.eclipse.jetty.server.session_defaultsessioncache"
  mbean = "org.eclipse.jetty.server.session:context=*,id=*,type=defaultsessioncache"
  paths = ["sessionsMax","sessionsTotal","sessionsCurrent"]
  tag_keys = ["context","id"]
```

## sessionhandler

### Tags

Tag | Description
--- | ---
context |
id |

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
sessionsCreated | totalcounter |  | The number of sessions created by this node.
sessionTimeMax | timeticks | seconds | The maximum amount of time sessions have remained active.
sessionTimeMean | timeticks | seconds | The mean time sessions remain valid.
sessionTimeStdDev | timeticks | seconds | The standard deviation of time that a session remained valid.
sessionTimeTotal | timeticks | seconds | The total time sessions have remained valid.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "org.eclipse.jetty.server.session_sessionhandler"
  mbean = "org.eclipse.jetty.server.session:context=*,id=*,type=sessionhandler"
  paths = ["sessionTimeMean","sessionTimeTotal","sessionTimeMax","sessionsCreated","sessionTimeStdDev"]
  tag_keys = ["context","id"]
```
