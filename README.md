# Spring Boot Application on Cloud

This project is an example for Spring Boot on Cloud. It includes the steps to get the latest java and install the same into the EC2 instance. 

## Instance and Software Setup
### Download Latest Java Archive
* Login to ec2 instance using putty.
* $ sudo su
* $ cd /opt/
* $ wget --no-cookies --no-check-certificate --header "Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/8u181-b13/96a7b8442fe848ef90c96a2fad6ed6d1/jdk-8u181-linux-x64.tar.gz"
* $ tar xzf jdk-8u181-linux-x64.tar.gz

### Install Java8 with Alternatives
* $ cd /opt/jdk1.8.0_181/
* $ alternatives --install /usr/bin/java java /opt/jdk1.8.0_181/bin/java 2
* $ alternatives --config java

### Setup javac and jar commands
* $ alternatives --install /usr/bin/jar jar /opt/jdk1.8.0_181/bin/jar 2
* $ alternatives --install /usr/bin/javac javac /opt/jdk1.8.0_181/bin/javac 2
* $ alternatives --set jar /opt/jdk1.8.0_181/bin/jar
* $ alternatives --set javac /opt/jdk1.8.0_181/bin/javac

### Check Installed Java Version
* $ java -version

### Setup Java Environment Variables
* $ export JAVA_HOME=/opt/jdk1.8.0_181
* $ export JRE_HOME=/opt/jdk1.8.0_181/jre
* $ export PATH=$PATH:/opt/jdk1.8.0_181/bin:/opt/jdk1.8.0_181/jre/bin

## Application Setup
### Move the application from localhost to EC2 Instance
* Use WinSCP to move the latest jar file to EC2 instance

### Start the application
* $ java -jar spring-boot-jpa-0.0.1-SNAPSHOT.jar
