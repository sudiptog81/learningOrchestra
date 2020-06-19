FROM spark_image

ENV SPARK_INSTALL /usr/local
ENV SPARK_HOME $SPARK_INSTALL/spark
ENV SPARK_ROLE master
ENV SPARK_MASTER_PORT 7077
ENV SPARK_WORKER_PORT 41352
ENV SPARK_MASTER_HOST "0.0.0.0"
ENV DOCKERIZE_VERSION v0.2.0



RUN curl -L -O https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz && \
    tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz && \
    rm -rf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

WORKDIR $SPARK_HOME

RUN mkdir /etc/service/spark
ADD script/spark.sh /etc/service/spark/run
RUN chmod +x /etc/service/**/*

EXPOSE 4040 6066 7077 7078 8080 8081 8888 41352

VOLUME ["$SPARK_HOME/logs"]

CMD ["/sbin/my_init"]