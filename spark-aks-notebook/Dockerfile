# Copyright (c) Jupyter Development Team.
# Distributed under the terms of the Modified BSD License.
# Modified by Lynn Calvo
ARG BASE_CONTAINER=jupyter/pyspark-notebook:7a0c7325e470
FROM $BASE_CONTAINER

LABEL maintainer="Lynn Calvo <guislander@outlook.com>"

# downgrade from python 3.7 to 3.6 for Spark 2.4.4
RUN conda install -y -q python=3.6

USER root

# add azure blob storage jars
RUN wget -nc -nv -O /usr/local/spark/jars/azure-storage-8.6.0.jar https://repo1.maven.org/maven2/com/microsoft/azure/azure-storage/8.6.0/azure-storage-8.6.0.jar && \
wget -nc -nv -O /usr/local/spark/jars/hadoop-azure-2.7.7.jar https://repo1.maven.org/maven2/org/apache/hadoop/hadoop-azure/2.7.7/hadoop-azure-2.7.7.jar

# Kubectl
RUN apt-get update && \
apt-get -y install curl && \
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl && \
chmod +x ./kubectl && \
mv ./kubectl /usr/local/bin/kubectl


USER $NB_UID

