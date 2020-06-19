FROM phusion/baseimage:18.04-1.0.0

RUN apt-get update && \
    apt-get install --no-install-recommends -y openjdk-8-jdk autossh python3-pip && 


ENV SPARK_VERSION 2.4.5
ENV SPARK_INSTALL /usr/local
ENV SPARK_HOME $SPARK_INSTALL/spark
ENV HADOOP_VERSION 2.7
ENV PYSPARK_PYTHON python3
ENV PYSPARK_DRIVER_PYTHON python3

RUN curl -s http://mirror.synyx.de/apache/spark/spark-$SPARK_VERSION/spark-$SPARK_VERSION-bin-hadoop$HADOOP_VERSION.tgz | tar -xz -C $SPARK_INSTALL && \
    cd $SPARK_INSTALL && ln -s spark-$SPARK_VERSION-bin-hadoop$HADOOP_VERSION spark

RUN apt-get autoremove && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*


