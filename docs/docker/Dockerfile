# specifies the base image to start with 
FROM amazoncorretto:17.0.11

# use build-time variables, only limited to build stage, not available inside the running container 
ARG APP_VERSION

# set environment variables that persist in the running container and available to the application inside it
ENV APP_VERSION=${APP_VERSION}
ENV DD_PROFILE_ENABLED=true

# run commands 
RUN echo "building with version ${APP_VERSION}"

# set the working directory insider the container
WORKDIR /app

# copy files or directories from the host machine to container's filesystem 
COPY target/backend-0.0.1-SNAPSHOT-app.jar app.jar

# add local or remote files and directories 
ADD https://dtdg.co/latest-java-tracer  dd-java-agent.jar

# indicate which ports the container will listen on 
EXPOSE 8080

# specifies the default command to run when a container starts from the image
# here java is the executable command and everything after are arguments
# Docker execute this as if you run the following on a command line
# `java -javaagent:/dd-java-agent.jar -Ddd.iast.enabled=true -jar ./app.jar`
CMD [ "java" , "-javaagent:/dd-java-agent.jar", "-Ddd.iast.enabled=true", "-jar", "./app.jar"]

