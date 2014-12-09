Boundary MongoDB Plugin
-----------------------
Collects metrics from a MongoDB instance. MongoDB statistics are pulled via a REST API call.

### Platforms
- Windows
- Linux
- OS X
- SmartOS

### Prerequisites
- node version 0.8.0 or later
- npm version 1.4.21 or later

### Plugin Setup

The statistics are pulled from http://hostname:(port+1000)/_status.  If you did not change the mongo default port, we will use 28107.

1. Verify that you have access to the MongoDB statics by using curl by running the following command:
     ```bash
     $ curl http://localhost:28017/_status
     ```
2. If you cannot view the page, you may need to enable the [Mongo REST interface](http://docs.mongodb.org/manual/reference/configuration-options/#net.http.RESTInterfaceEnabled)

3. If after enabling the Mongo REST interface, you are still unable to collect information from the REST interface and if you are polling remotely, ensure that the port that is serving the Mongo REST interfaces is open. You can bypasss any firewall restrictions by running locally where the MongoDB is running.

### Plugin Configuration Fields

|Field Name|Description                                                                                                           |
|:---------|:---------------------------------------------------------------------------------------------------------------------|
|Hostname  |The hostname of MongoDB                                                                                               |
|Port      |Port to use when accessing MongoDB                                                                                     |
|Username  |(optional) Username to access MongoDB                                                                                 |
|Password  |(optional) Pasword to access MongoDB                                                                                   |
|Source    |(optional) The Source to display in the legend for the MongoDB data.  It will default to the hostname of the server|

### Metrics Collected

Tracks the following metrics for [MongoDB](http://www.mongodb.org/)

|Metric Name            |Description                                                           |
|:----------------------|:--------------------------------------------------------------------|
|Mongo hits             |the number of times an accessed index was return from memory         |
|Mongo misses           |the number of times an accessed index was not in memory               |
|Mongo miss ratio       |Ratio of hits to misses [ hits / (hits+misses) ]                     |
|Mongo connections      |The number of open connections                                       |
|Mongo avail conns      |The number of available connections                                   |
|Mongo conn limit       |The ratio of used connections [used / (used+avail)]                   |
|Mongo global lock ratio|Percentage of time spent in the global lock                           |
|Mongo resident memory  |The amount of RAM being used by Mongo                                 |
|Mongo virtual memory   |The amount of virtual memory used by Mongo                           |
|Mongo mapped memory    |Mongo uses memory-mapped files, this will be about the size of the DB|
|Mongo inserts          |The number of mongo insert operations                                 |
|Mongo queries          |The number of mongo query operations                                 |
|Mongo updates          |The number of mongo update operations                                 |
|Mongo deletes          |The number of mongo delete operations                                 |
|Mongo getmore          |The number of mongo getmore operations                               |
|Mongo commands         |The number of mongo commands issued                                   |

