# Event Store Docker Container

> Source: https://github.com/agentk/eventstore-docker

The docker image will be available via the [Docker Hub Event Store Repository]( https://hub.docker.com/r/agentk/eventstore/)

### Getting Started
Pull the docker image
```
docker pull agentk/eventstore
```
Run the container using 
```
docker run --name eventstore-node -it -p 2113:2113 -p 1113:1113 agentk/eventstore
```

> Note : The admin UI and atom feeds will only work if you publish the node's http port to a matching port on the host. (i.e. you need to run the container with `-p 2113:2113`)

### Web UI

http://[docker-machine]:2113

Username and password is `admin` and `changeit` respectively.

### Using your own configuration

When running the docker image, the user has the ability to provide environment variables.
e.g.
```
docker run -it -p 2113:2113 -e EVENTSTORE_RUN_PROJECTIONS=None agentk/eventstore
```
The environment variables overrides the values supplied via the configuration file. 

More documentation on Event Store's Configuration can be found [here](http://docs.geteventstore.com/server/3.5.0/command-line-arguments/)

