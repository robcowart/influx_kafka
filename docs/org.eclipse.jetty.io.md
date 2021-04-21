# org.eclipse.jetty.io

Applies to the following components:

* Confluent Control Center
* Confluent Schema Registry
* Confluent REST Proxy

## arraybytebufferpool

### Tags

Tag | Description
--- | ---
context | 
id | 

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
directByteBufferCount | quantity |  | The number of pooled direct ByteBuffers.
directMemory | quantity | bytes | The bytes retained by direct ByteBuffers.
heapByteBufferCount | quantity |  | The number of pooled heap ByteBuffers.
heapMemory | quantity | bytes | The bytes retained by heap ByteBuffers.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "org.eclipse.jetty.io_arraybytebufferpool"
  mbean = "org.eclipse.jetty.io:context=*,id=*,type=arraybytebufferpool"
  tag_keys = ["context","id"]
```

## mappedbytebufferpool

### Tags

Tag | Description
--- | ---
context | 
id | 

### Values

Value | Semantic | Unit | Description
--- | --- | --- | ---
directByteBufferCount | quantity |  | The number of pooled direct ByteBuffers.
directMemory | quantity | bytes | The bytes retained by direct ByteBuffers.
heapByteBufferCount | quantity |  | The number of pooled heap ByteBuffers.
heapMemory | quantity | bytes | The bytes retained by heap ByteBuffers.

### Telegraf Field Configuration

```toml
[[inputs.jolokia2_agent.metric]]
  name = "org.eclipse.jetty.io_mappedbytebufferpool"
  mbean = "org.eclipse.jetty.io:context=*,id=*,type=mappedbytebufferpool"
  tag_keys = ["context","id"]
```
