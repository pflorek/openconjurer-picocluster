# OpenConjurer.org PicoCluster

[OpenConjurers](http://openconjurer.org/) running on [PicoCluster](https://www.picocluster.com/collections/pico-5/products/pico-5-odroid-c2-advanced-cluster-kit) powered by [docker](https://www.docker.com/). 

## Getting started
### Download Monolith

Download Monolith to _./app_ folder:

Via **curl**

```bash
curl -X GET -u svn-read -L "http://nexus.openconjurer.org/service/local/artifact/maven/redirect?g=org.openconjurer&a=service-monolith&v=LATEST&r=snapshots&e=jar" -o service-monolith-1.0-SNAPSHOT.jar
```

Via **wget**

```bash
wget "http://nexus.openconjurer.org/service/local/artifact/maven/redirect?g=org.openconjurer&a=service-monolith&v=LATEST&r=snapshots&e=jar" --user=svn-read --ask-password -O service-monolith-1.0-SNAPSHOT.jar
```

Or manually copy service-monolith-1.0-SNAPSHOT.jar into _./app_ folder

_Use our technical-user/password credentials or ask our admin for permissions._

### Build images and start services

Manually:
```bash
docker build -t mongo mongo
docker build -t app app
docker run -itd --name mongo -v /data/db:/data/db mongo
docker run -itd --name app -p 80:8080 --link mongo:mongo app
```

Automatically via [docker compose](https://docs.docker.com/compose/compose-file):

```bash
docker-compose up -d
```

## Useful commands

**Stop all containers**
```bash
docker stop $(docker ps -a -q)
```

**Delete all containers**

```bash
docker rm $(docker ps -a -q)
```

**Delete all images**

```bash
docker rmi $(docker images -q)
```

## References

[PicoCluster Getting Started Guide](https://www.picocluster.com/pages/picocluster-getting-started-guide)
[Docker Compose file reference](https://docs.docker.com/compose/compose-file)
[Docker Engine CLI reference](https://docs.docker.com/engine/reference/commandline/docker)