FROM resin/rpi-raspbian:jessie

RUN apt-get update
RUN apt-get install -y mongodb

EXPOSE 27017

CMD service mongod start
