# Modified by Lynn Calvo
ARG BASE_CONTAINER=guislander/spark-py:v2.4.4
FROM $BASE_CONTAINER

LABEL maintainer="Lynn Calvo <guislander@outlook.com>"

USER root

# add azure blob storage jars
RUN wget -nc -nv -O /opt/spark/jars/azure-storage-8.6.0.jar https://repo1.maven.org/maven2/com/microsoft/azure/azure-storage/8.6.0/azure-storage-8.6.0.jar && \
wget -nc -nv -O /opt/spark/jars/hadoop-azure-2.7.7.jar https://repo1.maven.org/maven2/org/apache/hadoop/hadoop-azure/2.7.7/hadoop-azure-2.7.7.jar


