FROM  spark_image

WORKDIR /usr/src/projection
COPY . /usr/src/projection

RUN pip3 install -r requirements.txt

ENV PROJECTION_HOST_NAME "projection"
ENV PROJECTION_HOST_PORT 5001
ENV PROJECTION_HOST_IP "0.0.0.0"
ENV SPARK_LOCAL_IP "0.0.0.0"
ENV SPARKMASTER_HOST "sparkmaster"
ENV SPARKMASTER_PORT 7077
ENV SPARK_DRIVER_PORT 41000

RUN pyspark --packages org.mongodb.spark:mongo-spark-connector_2.11:2.4.1

CMD ["python", "server.py"]