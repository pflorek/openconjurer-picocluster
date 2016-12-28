FROM resin/rpi-raspbian:jessie

ARG MONGO_MINOR
ENV MONGO_MINOR ${MONGO_MINOR:3.2}

ARG MONGO_VERSION
ENV MONGO_VERSION ${MONGO_VERSION:3.2.11}

# https://docs.mongodb.com/v3.2/tutorial/install-mongodb-on-debian/

# Import the public key used by the package management system.
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927

# Create a /etc/apt/sources.list.d/mongodb-org-${MONGO_MINOR}.list file for MongoDB.
RUN echo "deb http://repo.mongodb.org/apt/debian jessie/mongodb-org/${MONGO_MINOR} main" | tee "/etc/apt/sources.list.d/mongodb-org-${MONGO_MINOR}.list"

# Reload local package database.
RUN apt-get update

# Install the MongoDB packages.
RUN apt-get install -y \
	mongodb-org=$MONGO_VERSION \
	mongodb-org-server=$MONGO_VERSION \
	mongodb-org-shell=$MONGO_VERSION \
	mongodb-org-mongos=$MONGO_VERSION \
	mongodb-org-tools=$MONGO_VERSION

# Inform listening ports.
EXPOSE 27017

# Start MongoDB.
CMD service mongod start
