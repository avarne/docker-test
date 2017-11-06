#This will take ubuntu as base image.
FROM ubuntu

#Install pre requisite for Python packages.
RUN apt-get update && \
apt-get install -y build-essential checkinstall && \
apt-get install -y libreadline-gplv2-dev libncursesw5-dev libssl-dev libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev && \
mkdir /app && \
cd /app && \
apt-get install -y wget


RUN wget https://www.python.org/ftp/python/$version/Python-2.7.tgz

RUN tar -xvf Python-$version.tgz
RUN cd Python-2.7

