FROM gcr.io/distroless/java11-debian11

COPY target/hydra-identity-provider-0.0.16-SNAPSHOT.jar /opt/application/identity.jar

CMD ["/opt/application/identity.jar"]

EXPOSE 8080