# MongoDB Graphdat Plugin

### Pre Reqs

The statistics are pulled from http://hostname:(port+1000)/_status.  If you did not change the mongo default port, we will use 28107.

**Please verify that you can view the statistics from the URL (http://localhost:28017/_status)**

If you cannot view the page, you may need to enable the [Mongo REST interface](http://docs.mongodb.org/manual/reference/configuration-options/#net.http.RESTInterfaceEnabled)

**Please make sure this port is open in your firewall if you are polling remotely.**

If the relay is running locally, you can use **localhost** for the hostname and bypass any firewall restrictions.

### Installation & Configuration

* The `hostname` used to contact the mongo server
* The `port` used to contact the mongo server, defaults to 27017
* The `username` used to contact the mongo server
* The `passsword` used to contact the mongo server
* The `source` to prefix the display in the legend for the mongo data.  It will default to the hostname of the server.

#### Tracks the following metrics for [MongoDB](http://www.mongodb.org/)
* MONGO_BTREE_HITS -the number of times an accessed index was return from memory
* MONGO_BTREE_MISSES - the number of times an accessed index was not in memory"
* MONGO_BTREE_MISS_RATIO - Ratio of hits to misses [ hits / (hits+misses) ]"
* MONGO_CONNECTIONS - The number of open connections
* MONGO_CONNECTIONS_AVAILABLE - The number of available connections
* MONGO_CONNECTION_LIMIT - The ratio of used connections [used / (used+avail)]
* MONGO_GLOBAL_LOCK - Percentage of time spent in the global lock
* MONGO_MEM_RESIDENT - The amount of RAM being used by Mongo
* MONGO_MEM_VIRTUAL - The amount of virtual memory used by Mongo
* MONGO_MEM_MAPPED - Mongo uses memory-mapped files, this will be about the size of the DB
* MONGO_OPS_INSERTS - The number of mongo insert operations
* MONGO_OPS_QUERY - The number of mongo query operations
* MONGO_OPS_UPDATE - The number of mongo update operations
* MONGO_OPS_DELETE - The number of mongo delete operations
* MONGO_OPS_GETMORE - The number of mongo getmore operations
* MONGO_OPS_COMMAND - The number of mongo commands issued
