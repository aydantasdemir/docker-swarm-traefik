FROM java:8

RUN curl -sf -o /opt/airports-assembly-1.0.1.jar https://s3-eu-west-1.amazonaws.com/devops-assesment/airports-assembly-1.0.1.jar 

ADD airports-assembly-1.0.1.sha1 /opt/airports-assembly-1.0.1.sha1

RUN cd /opt && cat airports-assembly-1.0.1.sha1 | sha1sum -c -

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "/opt/airports-assembly-1.0.1.jar"]

