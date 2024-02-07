Title: Real-time Railway Data Processing with Kafka, MySQL, and Node.js

Description:
Welcome to the Real-time Railway Data Processing project, where we delve into the fascinating realm of railway data processing using modern technologies like Kafka, MySQL, and Node.js. This repository houses the scripts and resources necessary to construct a robust real-time railway data processing application capable of ingesting, processing, and storing railway data streams efficiently.

Key Features:

Kafka Integration: Leverage Kafka's distributed streaming platform to seamlessly handle real-time data feeds from railway systems.
MySQL Database: Store processed railway data reliably in a MySQL database for further analysis and retrieval.
Node.js Backend: Harness the power of Node.js to build scalable and efficient server-side applications for processing railway data.
Dependencies:

KafkaJS: A modern Apache Kafka client for Node.js applications, enabling easy interaction with Kafka brokers.
MySQL: A MySQL client library for Node.js applications, facilitating connectivity to MySQL databases.
Stompit: A Node.js client library for STOMP (Simple Text Oriented Messaging Protocol), used for connecting to message brokers like ActiveMQ.
Dockerized Environment:
This project utilizes Docker to orchestrate a containerized environment for running Zookeeper and Kafka. Docker simplifies the setup process by encapsulating Zookeeper and Kafka instances within containers, allowing for easy deployment and management. Below are the commands to set up and run the Docker containers:

Start Zookeper Container and expose PORT 2181.

docker run -p 2181:2181 zookeeper

Start Kafka Container, expose PORT 9092 and setup ENV variables.

docker run -p 9092:9092 -e KAFKA_ZOOKEEPER_CONNECT=<PRIVATE_IP>:2181 -e KAFKA_ADVERTISED_LISTENERS=PLAINTEXT://<PRIVATE_IP>:9092 -e KAFKA_OFFSETS_TOPIC_REPLICATION_FACTOR=1 confluentinc/cp-kafka



Scripts Included:

client.js: Configuration script for Kafka and MySQL clients, providing connectivity settings.
producer.js: Generates synthetic railway data and sends it to Kafka topics for ingestion.
consumer.js: Subscribes to Kafka topics, processes incoming data streams, and stores processed data into the MySQL database.
admin.js: Manages Kafka topics, including creation, configuration, and maintenance.
Message Types:
The application handles two types of messages:

Message Type 0001 (Train Activation): Indicates the activation of a train, containing information such as the train ID and activation location.
Message Type 0002 (Train Cancellation): Denotes the cancellation of a train, including details like the train ID, cancellation reason code, and cancellation location.
Additional Data Types:
In addition to train activation and cancellation messages, the Network Rail API provides various other data types, including but not limited to:

Train Movement Messages: Providing real-time updates on train movements, including departure and arrival times, locations, and schedules.
Signal Messages: Offering insights into signal status and changes along the railway network.
Incident Messages: Alerting about incidents, delays, and disruptions on the rail lines.
Getting Started:
To embark on your journey with the Real-time Railway Data Processing project, follow these steps:

Clone this repository to your local machine.
Install dependencies using npm install.
Configure Kafka and MySQL connection settings in client.js.
Set up Docker and run Zookeeper and Kafka containers using the provided commands.
Run the scripts to commence ingesting, processing, and storing railway data in real-time.
Contributing:
Contributions to this project are encouraged! Whether it's bug fixes, feature enhancements, or documentation improvements, feel free to submit pull requests or open issues to enrich the project.

License:
This project is licensed under the MIT License, allowing for open collaboration and usage.

Feedback:
Questions, suggestions, or feedback? Feel free to reach out or open an issue. Your input is invaluable in shaping the future of this project.

Embark on the Journey of Real-time Railway Data Processing and Unlock Actionable Insights!

