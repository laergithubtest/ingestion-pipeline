FROM ubuntu:16.04
RUN apt-get update
RUN apt-get install -y gnupg
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 9DA31620334BD75D9DCB49F368818C72E52529D4
RUN echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/4.0 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-4.0.list
RUN apt-get install -y apt-transport-https
RUN apt-get update
RUN apt-get install -y mongodb-org
RUN mkdir -p /data/db
EXPOSE 27017
CMD /usr/bin/mongod --port 27017 --bind_ip 0.0.0.0 --smallfiles --dbpath /data/db
