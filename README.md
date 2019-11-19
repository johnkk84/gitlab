# Gitlab workshoops

## Before You start

1. Make sure that you have docker on board:

`rpm -qa | grep -i docker`

desired output:
```
docker-ce-cli-19.03.4-3.el7.x86_64
docker-ce-19.03.4-3.el7.x86_64
```

If you have no docker on your computer please install it using below instruction:
[Install docker for RHEL and CentOS](https://docs.docker.com/v17.12/install/linux/docker-ce/centos/)

2. Make sure that your operational user belongs do docker group.

If your user do not belong to docker group please add it! This is important
to have access into docker socket and docker operations!

Open console and type:
`id`

If you will see following output:

```
uid=1000(<your user>) gid=1001(plp12439) groups=1001(plp12439),0(root),10(wheel),18(dialout),106(docker)
```

It means that you have access. Moreover you can type:

`docker ps`

If you have no containers running will see something similar:
```
CONTAINER ID        IMAGE                     COMMAND                  CREATED             STATUS                 PORTS                                                                      NAMES

```
Otherwise you got an error!

3. Make sure that docker-compse has been installed
From your operational user type:

`docker-compose`

If is installed you should received:

```
Define and run multi-container applications with Docker.

Usage:
  docker-compose [-f <arg>...] [options] [COMMAND] [ARGS...]
  docker-compose -h|--help

Options:
  -f, --file FILE             Specify an alternate compose file
                              (default: docker-compose.yml)
  -p, --project-name NAME     Specify an alternate project name
                              (default: directory name)
  --verbose                   Show more output
  --log-level LEVEL           Set log level (DEBUG, INFO, WARNING, ERROR, CRITICAL)
  --no-ansi                   Do not print ANSI control characters
  -v, --version               Print version and exit
  -H, --host HOST             Daemon socket to connect to

  --tls                       Use TLS; implied by --tlsverify
  --tlscacert CA_PATH         Trust certs signed only by this CA
  --tlscert CLIENT_CERT_PATH  Path to TLS certificate file
  --tlskey TLS_KEY_PATH       Path to TLS key file
  --tlsverify                 Use TLS and verify the remote
  --skip-hostname-check       Don't check the daemon's hostname against the
                              name specified in the client certificate
  --project-directory PATH    Specify an alternate working directory
                              (default: the path of the Compose file)
  --compatibility             If set, Compose will attempt to convert keys
                              in v3 files to their non-Swarm equivalent

Commands:
  build              Build or rebuild services
  bundle             Generate a Docker bundle from the Compose file
  config             Validate and view the Compose file
  create             Create services
  down               Stop and remove containers, networks, images, and volumes
  events             Receive real time events from containers
  exec               Execute a command in a running container
  help               Get help on a command
  images             List images
  kill               Kill containers
  logs               View output from containers
  pause              Pause services
  port               Print the public port for a port binding
  ps                 List containers
  pull               Pull service images
  push               Push service images
  restart            Restart services
  rm                 Remove stopped containers
  run                Run a one-off command
  scale              Set number of containers for a service
  start              Start services
  stop               Stop services
  top                Display the running processes
  unpause            Unpause services
  up                 Create and start containers
  version            Show the Docker-Compose version information
```

If you have hos such as command go through below instruction and install compose: [Install docker-compose for RHEL and CentOS](https://docs.docker.com/compose/install/)

Hint: Please click Linux tab!

4. Git installation.
I hope that you have already git installed. This is base tool for manage code and without it, DevOps does not exist. if otherwise, please install git using yum.

### Theory
Gitlab is CICD system often usage for build applications. It is totally It is a
system similar to Jeknkins but nevertheless using similar mechanisms but it is
not the same!

System has several main functions:

- Continous Integration and Delivery/Deployment
- Source Code Management(SCM)
- Auto DevOps
- DevSecOps
- Agile Planning
- Value Stream Management Tools (Cycle Analitics)

Below you will find the main advantages and characteristics:

* two versions available;
 - comminuty Edition;
 - enterprise Edition;

* based on rubby on rails
* do not have endlessly list of plugins like jenkins;
* uses gitlab runners;
* was written mainly in GO;
* supprots DSL;
* supports AutoDevops;
* supports webhook and many other integrations;
* compatible with Kubernetes and docker


### Exercises

1. [Start Gitlab server using docker-compose.](workshoop/exercise1.md)
2. [Enable SSL Self Sign On secure communication.](workshoop/exercise2.md)
3. [Setup gitlab runner for feature project uses](workshoop/excercise3.md)
4. [Build your first project.](workshoop/exercise4.md)
5. [Build artifacts and using them in projects.](workshoop/exercise5.md)
6. [Applied changes in project (pipeline observation).](workshoop/excercise6.md)
