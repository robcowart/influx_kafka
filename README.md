# influx_kafka

THIS IS A WORK-IN-PROGRESS - Please check in later for the complete solution.

Monitor Kafka environments including components of Confluent Platform with InfluxDB and Telegraf via Jolokia

![screenshots](https://user-images.githubusercontent.com/10326954/97915664-20380c80-1d52-11eb-82e4-5820d7b606ec.png)

## Contents

Path | Contents
--- | ---
chronograf | JSON documents for each dashboard to be imported into Chronograf.
docs | Markdown files containing documentation for the various JMX metrics provided by the various Kafka/Confluent Platform applications.
jolokia | The JAR file of the version of Jolokia used to develop this solution.
telegraf | The Telegraf configuration files which can be used to easily setup metrics collection for a Kafka/Confluent Platform environment, including hardware and operating system resources.
