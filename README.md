# polyglotdb-coreos
The CoreOS PoC for the PolyglotDB

To get started:
```
$ vagrant up
$ ssh-add ~/.vagrant.d/insecure_private_key
$ vagrant ssh core-01 -- -A
```
From this point you may interact with etcd from any of the machines with:
```
core@core-01 ~ $ curl http://localhost:4001/v2/keys/message -XPUT -d value="Hello etcd"
core@core-01 ~ $ curl http://localhost:4001/v2/keys/message
```
The key-value pairs you PUT will be available from any node in the cluster:
```
core@core-01 ~ $ exit
$ vagrant ssh core-02 -- -A
core@core-02 ~ $ curl http://localhost:4001/v2/keys/message
```

config.rb contains the number of cluster instances to start
