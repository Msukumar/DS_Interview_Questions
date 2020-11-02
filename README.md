# DS_Interview_Questions
Zookeeper properties
------------------------

TO run zooker server
------------------------
kafka main folder-> cmd
zookeeper-server-start.bat config\zooper.properties

TO run Kafka server
------------------------
kafka main folder-> cmd
kafka-server-start.bat config\server.properties

in new terminal
------------
kafka-topics --zookeeper 127.0.0.1:1281 --topic first_topic --create --partitions 3 --replication-factor 1 (note: it should be equal to no-of brokors running)

-------------
kafka-topics --zookeeper 127.0.0.1:1281 --list
kafka-topics --zookeeper 127.0.0.1:1281 --topic first_topic --describe
kafka-topics --zookeeper 127.0.0.1:1281 --topic first_topic --delete

producer
-------------------
kafka-console-producer --broker-list 1270.0.1:9092(note kafka server port)  --topic first_topic --producer-property acks=all

consumer
-----------------
kafka-console-consumer --bootstrap-server 1270.0.1:9092(note kafka server port) --topic first_topic

groups: based on the noof consumers load will take in below 3 partitions (red, blue, yello)
note: (group will show only unread messages only)
----------
new Terminal  - kafka-console-consumer --bootstrap-server 1270.0.1:9092(note kafka server port) --topic first_topic --group my-group-id
new Terminal  - kafka-console-consumer --bootstrap-server 1270.0.1:9092(note kafka server port) --topic first_topic --group my-group-id
new Terminal  - kafka-console-consumer --bootstrap-server 1270.0.1:9092(note kafka server port) --topic first_topic --group my-group-id


kafka-console-groups --bootstrap-server localhost:1212 --group --list
kafka-console-groups --bootstrap-server localhost:1212 --group my-group-id --describe
kafka-console-groups ---bootstrap-server localhost:1212 -group --reset-offsets -to-earlist -execute --topic first_topic (it will reset all the messages will display)























