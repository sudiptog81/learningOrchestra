FROM 127.0.0.1:5050/spark:spark


WORKDIR /usr/src/projection
COPY . /usr/src/projection

RUN pip3 install -r requirements.txt
RUN pyspark --packages org.mongodb.spark:mongo-spark-connector_2.11:2.4.1

ENV PROJECTION_HOST_NAME "projection"
ENV PROJECTION_HOST_PORT 5001
ENV PROJECTION_HOST_IP "0.0.0.0"
ENV SPARK_LOCAL_IP "0.0.0.0"
ENV SPARKMASTER_HOST "sparkmaster"
ENV SPARKMASTER_PORT 7077
ENV SPARK_DRIVER_PORT 41000

ENV SPARK_VERSION 2.4.5
ENV SPARK_INSTALL /usr/local
ENV SPARK_HOME $SPARK_INSTALL/spark
ENV HADOOP_VERSION 2.7
ENV PYSPARK_PYTHON python3
ENV PYSPARK_DRIVER_PYTHON python3


RUN pyspark --packages org.mongodb.spark:mongo-spark-connector_2.11:2.4.1
CMD ["python", "server.py"]