# Kafka_neo4j

pastiin lu udah punya confluent full set dan udah up semua servisnya,kalo belom punya cek repo gue ada disini https://github.com/rakaay431/confluent_local_for_kafka_connect
![image](https://user-images.githubusercontent.com/77326619/159466518-1705cbce-d65a-419d-8035-df975d32d9a1.png)

trus kalo semua udah up servicenya lu install dulu connector neo4j kafka nya
$CONFLUENT_HOME/bin/confluent-hub install  neo4j/kafka-connect-neo4j:2.0.2
kalo udah restart service kafka nya
confluent local services stop && confluent local services start
![image](https://user-images.githubusercontent.com/77326619/159467837-b023401e-7ccb-431a-8341-4b49d0583a5d.png)

trus lu masuk ke confluent ui lu trus pencet tab connect
![image](https://user-images.githubusercontent.com/77326619/159468084-92eefb26-49f8-423f-872c-bde88685e5da.png)
trus lu pencet add conector buat ngecek udah ada belom connector neo4j nya
![image](https://user-images.githubusercontent.com/77326619/159468285-4f086a8f-518e-4de2-8891-bf01cd20fb1a.png)
kalo udah ada kaya gini
![image](https://user-images.githubusercontent.com/77326619/159468372-41c29a45-1742-4417-88e2-030121c47cc1.png)



kalo udah lu udah ready 




langkah pertama lu bikin file connectorneo4j.json kalo gue namanya bebas.json
isinya nanti gue taro diatas ye
![image](https://user-images.githubusercontent.com/77326619/159466809-57f0c0ac-f689-4c74-81e9-0341f4b13f3d.png)
![image](https://user-images.githubusercontent.com/77326619/159466871-7cfc4bfe-fc84-47d8-ad7b-f6ee16565bfe.png)

abis itu lu tembak dah tuh bebas.json atau file json yang lu buat
curl -i -X POST -H "Accept:application/json" -H  "Content-Type:application/json" http://localhost:8083/connectors/ -d @bebas.json
![image](https://user-images.githubusercontent.com/77326619/159467094-d259d4e8-22b6-4d95-a892-195cd4b0f27b.png)
trus lu cek dah topik lu masuk ga 
disini topic gue namanya my-topic karena di bebas.json gue ngisinya my-topic
bin/kafka-topics --bootstrap-server localhost:9092 --list
trus kalo udah ada topicnya lu run
bin/kafka-console-consumer --bootstrap-server localhost:9092 --topic my-topic
![image](https://user-images.githubusercontent.com/77326619/159467500-2ce5b023-9176-4988-9d1e-01ddbf51e4cf.png)




