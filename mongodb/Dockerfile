 # Dockerizing MongoDB: Dockerfile for building MongoDB images
    # Based on ubuntu:latest, installs MongoDB following the instructions from:
    # http://docs.mongodb.org/manual/tutorial/install-mongodb-on-ubuntu/
 # Format: FROM    repository[:version]
FROM       ubuntu:latest
# Format: MAINTAINER Name <email@addr.ess>
MAINTAINER M.Y. freshmendi  <1142040298@qq.com>
    # Installation:
    # Import MongoDB public GPG key AND create a MongoDB list file
RUN apt-get update && apt-get install -y gnupg2
#RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com --recv 7F0CEB10
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10
#RUN apt-get update && apt-get install -y gnupg2
RUN echo 'deb [trusted=yes]  http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' | tee /etc/apt/sources.list.d/10gen.list
# Update apt-get sources AND install MongoDB
RUN apt install ca-certificates -y
##RUN apt-get update  
RUN apt-get install -y -q mongodb-org
# Create the MongoDB data directory
RUN mkdir -p /data/db
# Expose port 27017 from the container to the host
EXPOSE 27017

# Set usr/bin/mongod as the dockerized entry-point application
ENTRYPOINT usr/bin/mongod
