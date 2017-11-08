# INSTALL PYTHON 2.7 STARTS
#This will take ubuntu as base image.
FROM centos:6

#Install pre requisite for Python packages.
RUN yum install -y centos-release-SCL

#Install Python2.7
RUN yum install -y python27

# INSTALL PYTHON 2.7 ENDS 

# INSTALL MONGO DB 3.4 STARTS

#Configure the package management system.

#Adding MongoDB to the repo
RUN printf "[mongodb]\nname=MongoDB Repository\nbaseurl=http://downloads-distro.mongodb.org/repo/redhat/os/`uname -m`/\ngpgcheck=0\nenabled=1" > /etc/yum.repos.d/mongodb.repo

#Updating Repo Sources 
RUN yum -y update

#Installing Latest Stable Version 
RUN yum install -y mongodb-org

#Expose mongo db ports to connect db remotely using Host Ip
EXPOSE 27017


# INSTALL MONGO DB 3.4 ENDS

# INSTALL APACHE TOMCAT 7 STARTS

RUN yum install -y wget;  yum clean all

# Set correct environment variables.
ENV	LANG en_US.UTF-8
ENV	LC_ALL en_US.UTF-8

ENV JDK_VERSION 8u151
ENV JDK_BUILD_VERSION b12
ENV JDK_DL_ID e758a0de34e24606bca991d704f6dcbf
RUN wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/$JDK_VERSION-$JDK_BUILD_VERSION/$JDK_DL_ID/jdk-$JDK_VERSION-linux-i586.rpm?" && rpm -i jdk-$JDK_VERSION-linux-i586.rpm; rm -f jdk-$JDK_VERSION-linux-i586.rpm; yum clean all
ENV JAVA_HOME /usr/java/default

RUN yum remove curl; yum clean all

# Install Tomcat
# Download Apache Tomcat 7 
RUN cd /tmp;wget http://www-us.apache.org/dist/tomcat/tomcat-7/v7.0.82/bin/apache-tomcat-7.0.82.tar.gz

# untar and move to proper location 
RUN cd /tmp;tar xvf apache-tomcat-7.0.82.tar.gz
RUN cd /tmp;mv apache-tomcat-7.0.82 /opt/tomcat7
RUN chmod -R 755 /opt/tomcat7/

ENV CATALINA_HOME=/opt/tomcat7/
ENV PATH=/opt/tomcat7/bin:$PATH

EXPOSE 8080/tcp
WORKDIR /opt/tomcat7/bin 

#USER tomcat
CMD ["catalina.sh", "start"]

# INSTALL APACHE TOMCAT 7 ENDS