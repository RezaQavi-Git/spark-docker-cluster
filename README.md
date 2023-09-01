# Spark Docker Cluster

This YAML file is used for configuring a minimal Apache Spark cluster using Docker containers. It defines two services: "spark-master" and "spark-worker."

## `spark-master` service:
    Uses the official Apache Spark Docker image with the "latest" tag.
    Assigns the container the name "spark-master."
    Maps host ports 8080 and 7077 to container ports 8080 and 7077, respectively.

## `spark-worker` service:
    Also uses the official Apache Spark Docker image with the "latest" tag.
    Assigns the container the name "spark-worker."
    Sets an environment variable SPARK_MASTER to specify the Spark master's location as "spark://spark-master:7077."
    Depends on the "spark-master" service, ensuring it starts after the master.
    This YAML file provides the basic configuration to set up a Spark cluster with one master and one worker node, making it easy to run Spark applications in a containerized environment.