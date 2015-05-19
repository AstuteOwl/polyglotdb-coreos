# polyglotdb-coreos
The CoreOS PoC for the PolyglotDB

To get started:
```
vagrant up
vagrant status
vagrant ssh core-01 -- -A
```
From this point you may interact with etcd from any of the machines with:
```
curl http://localhost:4001/v2/keys/message -XPUT -d value="Hello etcd"
curl http://localhost:4001/v2/keys/message
```
The key-value pairs you PUT will be available from any node in the cluster.

config.rb contains the number of cluster instances to start
