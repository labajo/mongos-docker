# Mongos Docker

A minimal mongos cluster, with three shard server (run at 29001, 29002 and 29003) and one config server (at 27000). The mongos progress exposed at 27017.

# Usage

```
# run the docker (for example, at 28018)
docker run --name mongos -p 28018:27017 -d karloku/mongos-docker

# add the shards
mongo --port 28018 --eval "printjson(sh.addShard('localhost:29001'));"
mongo --port 28018 --eval "printjson(sh.addShard('localhost:29002'));"
mongo --port 28018 --eval "printjson(sh.addShard('localhost:29003'));"
```

enjoy!
