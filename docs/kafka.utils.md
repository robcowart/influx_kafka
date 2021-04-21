# kafka.utils

Applies to the following components:

* Kafka

## Throttler

### Values

Value | Semantic | Description
--- | --- | ---
cleaner-io.Count | totalcounter | The count of times that cleaner-io was throttled.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "kafka.utils_Throttler"
  mbean = "kafka.utils:name=cleaner-io,type=Throttler"
  paths = ["Count"]
  field_prefix = "cleaner-io."
```
