FROM java:8

RUN curl -sf -o /opt/countries-assembly-1.0.1.jar https://s3-eu-west-1.amazonaws.com/devops-assesment/countries-assembly-1.0.1.jar 

ADD countries-assembly-1.0.1.sha1 /opt/countries-assembly-1.0.1.sha1

RUN cd /opt && cat countries-assembly-1.0.1.sha1 | sha1sum -c -

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "/opt/countries-assembly-1.0.1.jar"]

