# 连接

> 文档：<https://www.mongodb.com/docs/drivers/node/current/fundamentals/connection/connect/#std-label-node-connect-to-mongodb>

## node 连接

```typescript
const { MongoClient, ServerApiVersion } = require("mongodb");
const uri = "mongodb://host1:27017,host2:27017,host3:27017/?replicaSet=myRs"
new MongoClient(uri,  {
        serverApi: {
            version: ServerApiVersion.v1,
            strict: true,
            deprecationErrors: true,
        }
    }
).connect()
```