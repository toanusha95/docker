FROM ubuntu
RUN apt update
RUN apt install default-jre -y
RUN apt install default-jdk -y
RUN java -version
RUN mkdir /opt/tomcat/
WORKDIR /opt/tomcat
ADD https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.63/bin/apache-tomcat-9.0.63.tar.gz .
RUN tar -xvzf apache-tomcat-9.0.63.tar.gz
RUN mv apache-tomcat-9.0.63/* /opt/tomcat
COPY ./gameoflife-web/target/gameoflife.war /opt/tomcat/webapps
EXPOSE 8080
