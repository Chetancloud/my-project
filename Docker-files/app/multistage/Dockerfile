FROM amazoncorretto:17-alpine AS builder
WORKDIR /home/ubuntu/my-project
# RUN git clone https://github.com/awsbeginnertutorial/my-project.git
# RUN cd my-project && git checkout docker && mvn install
COPY pom.xml .
COPY target/vprofile-v2/WEB-INF/lib/*.jar parent-join-client-5.6.4.jar
                  
FROM amazoncorretto:latest
ENV JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
ENV PATH="${JAVA_HOME}/bin:${PATH}"
WORKDIR /home/ubuntu/my-project

EXPOSE 8080

CMD ["run", "chmod +x \my-project"]
CMD["java","-jar","parent-join-client-5.6.4.jar"]
