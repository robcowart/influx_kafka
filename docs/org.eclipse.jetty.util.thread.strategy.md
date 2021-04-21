# org.eclipse.jetty.util.thread.strategy

Applies to the following components:

* Confluent Control Center
* Confluent Schema Registry
* Confluent REST Proxy

## eatwhatyoukill

### Tags

Tag | Description
--- | ---
context |
id |

### Values

Value | Semantic | Description
--- | --- | ---
ePCTasksConsumed | quantity | The number of tasks consumed with EPC mode.
pCTasksConsumed | quantity | The number of tasks consumed with PC mode.
pECTasksExecuted | quantity | The number of tasks executed with PEC mode.
pICTasksExecuted | quantity | The number of tasks executed with PIC mode.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "org.eclipse.jetty.util.thread.strategy_eatwhatyoukill"
  mbean = "org.eclipse.jetty.util.thread.strategy:context=*,id=*,type=eatwhatyoukill"
  paths = ["pCTasksConsumed","pECTasksExecuted","ePCTasksConsumed","pICTasksExecuted"]
  tag_keys = ["context","id"]
```
