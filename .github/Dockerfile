FROM adoptopenjdk/openjdk12 as build


RUN jlink \
    --add-modules jdk.unsupported,java.sql,java.desktop,java.naming,java.management,java.instrument,java.security.jgss \
    --verbose \
    --strip-debug \
    --compress 2 \
    --no-header-files \
    --no-man-pages \
    --output /opt/java/jdk

FROM panga/alpine:3.8-glibc2.27


COPY --from=build /opt/java/jdk /opt/java/jdk
COPY target/hydra-identity-provider-*.jar /opt/application/identity-provider.jar

ENTRYPOINT ["/opt/java/jdk/bin/java", "-jar", "/opt/application/identity-provider.jar"]

EXPOSE 8080