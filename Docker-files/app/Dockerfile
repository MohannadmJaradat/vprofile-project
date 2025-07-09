# This will be a multi stage docker file, which is used to build the artifact and put it in the target image.
FROM maven:3.9.9-eclipse-temurin-21-jammy AS BUILD_IMAGE
RUN git clone https://github.com/MohannadmJaradat/vprofile-project.git
# We combined the following commands using && in order to decrease the number of layers in the image.
RUN cd vprofile-project && git checkout containers && mvn install

# The previous commands will build the artifact, the following ones will use it.

FROM tomcat:10-jdk21
# Remove the default application present in the tomcat image
RUN rm -rf /usr/local/tomcat/webapps/*
# Copy the artifact we just build usdin the name we assigne into this image
Copy --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]

# The reason we made this Dockerfile a multi stage Dockerfile (used 2 images) is to prevent the tomcat image from getting heavy by putting everything in it.
# The only thing we want from the maven image is the artifact, and not the tools and dependencies used to build it.
# That's why we kept the build image (maven) separate from the service image (tomcat).
# Whenever you have an application that needs to be built and then hosted, you need to have a multi stage Dockerfile.