# realtime_transportlayer
learning kafka

## Theory

### Guarantees
- Messages are always appended in an order to the topic::partition
- Messages are always read by the consumes in the same order as stored
- If you have _n_ replication factor, it is guaranteed to operate even when _n-1_ brokers go down
- Tip: Have at least 3 replication factor. Because one can be maintained while the other works as a backup for unexpected impacts.

## Installation on Windows
- download Java 8 sdk (needs oracle account)
- download latest Kafka version (2.4 in this case)
- Install Java 8 sdk
- winRAR kafka file and place it in a sane path: (C:\softwares\kafka>bin\windows\kafka-topics.bat)
- add it to env Path
- Edit zookeeper.properties found in the config folder and replace _dataDir=/tmp/zookeeper_ with _dataDir=C:/softwares/kafka/data/zookeeper_. Make sure _C:/softwares/kafka/data/zookeeper_ is created in the first place.  
- Launch zookeeper: _C:\softwares\kafka>zookeeper-server-start.bat config\zookeeper.properties_ (ensure to see this on command line: INFO ... 0.0.0.0/0.0.0.0:2181)
- Edit server.properties by replacing _log.dirs=/tmp/kafka-logs_ with _log.dirs=C:\softwares\kafka\data\kafka_. Ensure the directory exists in the firstplace.
- Launch Kafka server: _C:\softwares\kafka>kafka-server-start.bat config\server.properties_

## Kafka CLI
