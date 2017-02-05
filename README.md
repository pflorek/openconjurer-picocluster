# OpenConjurer.org Picocluster

### 1. Download Monolith:

Via **curl**

curl -X GET -u svn-read -L "http://nexus.openconjurer.org/service/local/artifact/maven/redirect?g=org.openconjurer&a=service-monolith&v=LATEST&r=snapshots&e=jar" -o service-monolith-1.0-SNAPSHOT.jar

Via **wget**

wget "http://nexus.openconjurer.org/service/local/artifact/maven/redirect?g=org.openconjurer&a=service-monolith&v=LATEST&r=snapshots&e=jar" --user=svn-read --ask-password -O service-monolith-1.0-SNAPSHOT.jar

_Use our technical-user/password credentials or ask our admin for permissions._

### 2. Prepare app image

Copy service-monolith-1.0-SNAPSHOT.jar into ./app folder

### 3. Build images



## Useful commands

**Delete all containers**

```docker rm $(docker ps -a -q)```

**Delete all images**

```docker rmi $(docker images -q)```