# Steps to install and use Kafka

## Installation of Kafka

### Installing Maven and OpenJDK

Using the following commands, install Maven and OpenJDK and verify them. If we already have these, we can just update using ``` choco upgrade all -y ```

1. choco install maven -y
1. choco install openjdk -y
1. refreshenv
1. choco list -l
1. java --version
1. mvn --v

### Installing Kafka

1. To install the latest source tgz file to C:\, go to (Install Kafka)[https://kafka.apache.org/quickstart]
1. Un-tar this file using Bash commands
- tar -xzf <filename>
- cd <folder>

### Environment Varibales - Setup

1. Go to Windows and select Edit the System Environment Variables / Environment Variables / System variables
1. Set up the system variables as follows and use the versions that you've installed
- JAVA_HOME = C:\Program Files\OpenJDK\jdk-version folder
- KAFKA_HOME =  C:\kafka-version folder
- M2_HOME = C:\ProgramData\chocolatey\lib\maven\apache-maven-version
1. Path must have the following
- %JAVA_HOME%\bin OR C:\Program Files\OpenJDK\jdk-version\bin (or similar, NOT both!)
- %M2_HOME%\bin
- %KAFKA_HOME%\bin
- %KAFKA_HOME%\bin\windows

## Kafka Commands

1. To run the Zookeeper service

``` .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties ```

1. To run Kafka service

``` .\bin\windows\kafka-server-start.bat .\config\server.properties ```

1. To execute create, list and delete commands

``` .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic fav-marvel-superheroes ```

and

``` .\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list ```

1. To run Kafka producer

``` .\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic fav-marvel-superheroes ```

1. To run Kafka Consumer

``` .\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic fav-marvel-superheroes --from-beginning ```
