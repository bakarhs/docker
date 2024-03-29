# docker
docker

![img.png](img.png)

## What is docker
Docker is a containerization platform that allows developers to package their applications, along with their dependencies and libraries, into a single unit called a container. Docker containers are lightweight, portable, and can run consistently across different computing environments, making it easier for developers to deploy and manage their applications.

## Why do we use docker
We use Docker to simplify the application deployment process and to ensure that our applications run consistently across different environments. Docker allows us to package our application code, runtime environment, and dependencies into a container image, which can be easily moved between different computing environments, such as development, testing, and production environments.

## How do we use docker?
To use Docker, we first need to install Docker on our local machine or server. Once installed, we can use the Docker command-line interface (CLI) to create and manage containers. We start by creating a Dockerfile, which specifies the instructions to build a container image. We then use the Docker CLI to build the image and run the container.

## WHen do we use docker?
We use Docker when we want to simplify the deployment process, improve application reliability, and increase scalability. Docker allows us to package our application code and dependencies into a single container, which can be easily deployed to different environments without worrying about compatibility issues.

## Who uses docker?
Docker is used by a wide range of organizations, from small startups to large enterprises, and by developers and IT professionals across different industries. It is particularly popular among DevOps and cloud computing professionals, who use Docker to manage and deploy applications in cloud-based environments.

## Benefits of docker

The key benefits of using Docker include:

1. Portability: Docker containers are highly portable, making it easy to move them between different environments, such as development, testing, and production.

2. Consistency: Docker ensures that applications run consistently across different environments, regardless of the underlying infrastructure or operating system.

3. Efficiency: Docker containers are lightweight, which means they require fewer resources to run than traditional virtual machines. This leads to faster deployment times and lower infrastructure costs.

4. Isolation: Docker containers provide a high level of isolation between applications, making it possible to run multiple applications on the same host without worrying about compatibility issues.

5. Security: Docker provides several security features, such as containerization and isolation, which help to prevent unauthorized access and protect the application from external threats.

6. Scalability: Docker makes it easy to scale applications up or down by adding or removing containers as needed.

7. Automation: Docker allows for the automation of the application deployment process, which can save time and reduce the risk of human error.

Overall, Docker provides a more efficient, reliable, and secure way to deploy and manage applications, making it an increasingly popular choice for developers and IT professionals.

## Difference between virtualization and containerization 

Virtualization and containerization are both technologies used to deploy and run applications, but they have some fundamental differences.

Virtualization is the process of creating a virtual version of an operating system, hardware, or network resources. Virtualization allows multiple operating systems to run on a single physical machine, each in its own isolated environment. Each virtual machine runs its own guest operating system, and the hypervisor provides the abstraction layer between the physical resources and the virtual machines.

On the other hand, containerization is a lightweight alternative to virtualization that allows multiple applications to run on a single operating system, each in its own isolated environment. Containers are created from a single operating system and share the same kernel, but each container has its own isolated file system, network, and resources.

The main differences between virtualization and containerization are:

1. Resource utilization: Virtualization uses more resources since each virtual machine requires its own operating system, while containerization shares the host operating system, which leads to better resource utilization.

2. Isolation: Virtual machines provide complete isolation between different guest operating systems, while containers share the same kernel, which provides a lower level of isolation.

3. Deployment time: Virtual machines can take longer to deploy since they require a complete operating system installation, while containers can be quickly deployed since they only require the container image to be downloaded and started.

4. Portability: Containers are highly portable since they can be easily moved between different environments, while virtual machines are less portable due to differences in hardware and underlying operating systems.

In summary, virtualization provides complete isolation between different operating systems, while containerization provides lightweight isolation between applications running on the same operating system. Virtualization is suitable for running multiple operating systems on a single machine, while containerization is suitable for running multiple applications on a single operating system.

## Docker architecture/api

Docker architecture consists of several components that work together to enable containerization and management of containerized applications. The main components of Docker architecture are:

- Docker Daemon: It is a background service that runs on the host machine and manages the containers. It communicates with the Docker client and performs tasks such as building, running, and managing containers.

- Docker Client: It is a command-line interface (CLI) tool that allows users to interact with the Docker daemon. The Docker client sends commands to the daemon to build, run, and manage containers.

- Docker Images: It is a read-only template that contains the application code, runtime environment, libraries, and dependencies required to run a container. Docker images can be built locally or downloaded from Docker Hub, a public repository of Docker images.

- Docker Containers: It is a running instance of a Docker image. Each container is isolated from the host machine and other containers, and has its own file system, network, and resources.

- Docker Registry: It is a service that stores Docker images. Docker Hub is a public registry maintained by Docker, but users can also set up their own private registry to store their own Docker images.

Docker also provides a RESTful API that allows developers to interact with the Docker daemon programmatically. The Docker API provides endpoints for managing containers, images, networks, volumes, and other Docker objects. Developers can use the Docker API to build custom tools and integrations that interact with the Docker daemon. The Docker API is also used by popular container orchestration platforms, such as Kubernetes and Docker Swarm, to manage containers at scale.

## Docker port mapping

Docker port mapping (also known as port forwarding) is a technique used to map network ports on a Docker container to specific ports on the host machine. This allows the container to be accessible from the host machine or from other machines on the network.

Docker containers run in isolation from the host machine, and they have their own IP address and network stack. By default, containers cannot communicate with the outside world. Port mapping enables containers to expose specific ports to the host machine, making it possible to access them from the host or other machines on the network.

To perform port mapping, you can use the `-p` or `--publish` option when running a container with the `docker run` command. This option takes two arguments: the first is the host port, and the second is the container port. For example, to map port 80 in a container to port 8080 on the host machine, you can use the following command:

```
docker run -p 8080:80 my_container
```

## Container lifecycle 

The lifecycle of a container in Docker can be broken down into four primary stages: create, start, stop, and delete.

Create:
The first stage in the container lifecycle is the creation of the container. This involves creating a new container image or pulling an existing image from a registry. When creating a new container, you can specify various configuration options such as the image name, container name, environment variables, ports to expose, volumes to mount, and more.

- Start:
After creating the container, you can start it using the `docker start` command. This initializes the container's runtime environment and launches the processes specified in the container image. The container then runs in the background and can be accessed through the exposed ports or by using the `docker exec` command to execute commands inside the container.

- Stop:
When you're finished with a container, you can stop it using the `docker stop` command. This sends a signal to the container to gracefully stop its processes and shut down. Alternatively, you can use the `docker kill` command to forcefully stop the container's processes. When a container is stopped, it retains its state, including any changes made to its filesystem or data stored in its volumes.

- Delete:
Finally, when you no longer need a container, you can delete it using the `docker rm` command. This removes the container and its associated filesystem, volumes, and network resources. Note that deleting a container does not delete the underlying image; you can still use the image to create new containers.

- It's important to note that containers are designed to be ephemeral, meaning they should be disposable and easily recreated. This is in contrast to traditional virtual machines, which are typically long-lived and stateful. By designing applications to be containerized and ephemeral, you can take advantage of the benefits of containerization, such as fast startup times, easy deployment, and scalability.

## Docker commands

```
Options:
      --config string      Location of client config files (default
                           "C:\\Users\\ashar\\.docker")
  -c, --context string     Name of the context to use to connect to the
                           daemon (overrides DOCKER_HOST env var and
                           default context set with "docker context use")
  -D, --debug              Enable debug mode
  -H, --host list          Daemon socket(s) to connect to
  -l, --log-level string   Set the logging level
                           ("debug"|"info"|"warn"|"error"|"fatal")
                           (default "info")
      --tls                Use TLS; implied by --tlsverify
      --tlscacert string   Trust certs signed only by this CA (default
                           "C:\\Users\\ashar\\.docker\\ca.pem")
      --tlscert string     Path to TLS certificate file (default
                           "C:\\Users\\ashar\\.docker\\cert.pem")
      --tlskey string      Path to TLS key file (default
                           "C:\\Users\\ashar\\.docker\\key.pem")
      --tlsverify          Use TLS and verify the remote
  -v, --version            Print version information and quit

Management Commands:
  builder     Manage builds
  buildx*     Docker Buildx (Docker Inc., v0.10.3)
  compose*    Docker Compose (Docker Inc., v2.15.1)
  config      Manage Docker configs
  container   Manage containers
  context     Manage contexts
  dev*        Docker Dev Environments (Docker Inc., v0.1.0)
  extension*  Manages Docker extensions (Docker Inc., v0.2.18)
  image       Manage images
  manifest    Manage Docker image manifests and manifest lists
  network     Manage networks
  node        Manage Swarm nodes
  plugin      Manage plugins
  sbom*       View the packaged-based Software Bill Of Materials (SBOM) for an imag
e (Anchore Inc., 0.6.0)
  scan*       Docker Scan (Docker Inc., v0.25.0)
  scout*      Command line tool for Docker Scout (Docker Inc., v0.6.0)
  secret      Manage Docker secrets
  service     Manage services
  stack       Manage Docker stacks
  swarm       Manage Swarm
  system      Manage Docker
  trust       Manage trust on Docker images
  volume      Manage volumes

Commands:
  attach      Attach local standard input, output, and error streams to a running c
ontainer
  build       Build an image from a Dockerfile
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  images      List images
  import      Import the contents from a tarball to create a filesystem image
  info        Display system-wide information
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  login       Log in to a Docker registry
  logout      Log out from a Docker registry
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  ps          List containers
  pull        Pull an image or a repository from a registry
  push        Push an image or a repository to a registry
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  run         Run a command in a new container
  save        Save one or more images to a tar archive (streamed to STDOUT by defau
lt)
  search      Search the Docker Hub for images
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  version     Show the Docker version information
  wait        Block until one or more containers stop, then print their exit codes


```

key commands:

```
docker images - shows a list of images

docker run -d -p 80:80 <username>/<docker repo>

docker ps -a

docker start 

docker stop 

docker rm containerID -f

Execute an additional command in a container `docker exec -it containerID bash` `docker exec -it containerID sh`

# If this does not work run this command then use `alias docker="winpty docker"`

```

To navigate to the html file once in our docker container `cd /usr/share/nginx/html`

We should then be able to see our `index.html`

You won't be able to do anything with this until you:

```
apt update -y
apt upgrade-y

apt install nano
```

## How to push an image to your repo

```
docker ps # to fidn your images id

docker commit <id> <username>/<reponame>

docker tag <id> <username/repo>

docker push <username/reponame> # you can aslo put a tag at the end docker push <username/reponame>:v1
```

### Building a docker image

To build a docker image we need to create a Dockerfile

![img_1.png](img_1.png)

![img_2.png](img_2.png)

To build the image run the command:
```
docker build -t <username/repo> .

docker images
```

You can test it by running the image:

```
docker run -d -p 80:80 <username/repo>
```
## Building an image for the node app

- Create a new directory called `nodejs`
- Inside the directory make a new `Dockerfile`
- Copy your app file into your `nodejs` directory
- Enter the following code into your docker file (VScode):

```
FROM node:latest

LABEL MAINTAINER=abubakarhs123@gmail.com

WORKDIR /usr/src/app

COPY app /usr/src/app/
COPY package*.json ./

RUN npm install

EXPOSE 3000

CMD ["npm", "start"]
```

- Test  to see if the app runs properly and if it does you will need to tag the image and push it to docker hub

- **Note** make sure you start/ push the image from the right directory `nodejs`

## Building a docker container on EC2

- Create a an EC2 instance with the correct dependancies
- Make sure to allow ports 22,80,3000

- Commands needed to install docker in ec2 and run a container.
```
sudo apt update
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo docker run -d -p 3000:3000 <username>/<repo>:<tag>
```

# Docker compose

Docker Compose is a tool for defining and running multi-container Docker applications. It allows you to define your application's services, networks, and volumes in a single YAML file, and then spin up your entire application stack with a single command.

With Docker Compose, you can define multiple containers, their dependencies, and configure how they communicate with each other. This makes it easy to manage complex applications that require multiple containers to run together.

Docker Compose also allows you to specify environment variables, volumes, ports, and other settings for your containers. You can also scale your services up or down to handle changes in traffic or demand.

Overall, Docker Compose simplifies the process of deploying and managing complex multi-container applications, making it a popular tool among developers and DevOps teams.

docker-compose.yml file for sparta app

```YAML
version: "3"
services:
  mongo:
    image: mongo:4.4
    container_name: mongo
    volumes:
    - ./database/mongod.conf:/etc/mongod.conf
    ports:
      - "27017:27017"
    
  app:
    container_name: app
    restart: always
    build: .
    environment:
      - DB_HOST=mongodb://mongo:27017/posts
    ports:
      - "80:3000"
    links:
      - mongo:4.4
    command: bash -c "node /usr/src/app/seeds/seed.js && cd /usr/src/app && npm start"
```

This is a Docker Compose file written in YAML format that defines two services: mongo and app.

The mongo service is based on the official mongo Docker image version 4.4, and is given a container name of mongo. It mounts a local mongod.conf file as a volume inside the container and maps the container port 27017 to the host port 27017.

The app service is built from a local Dockerfile using the build command, and is given a container name of app. It specifies that the container should always be restarted if it exits, and exposes port 3000 in the container as port 80 on the host machine.

It also sets the DB_HOST environment variable to mongodb://mongo:27017/posts, which tells the app service to connect to the mongo service over port 27017.

Finally, it links the mongo service to the app service and runs the seed.js script to populate the database with sample data before starting the npm start command to run the application.

- This composer file must be in the same directory as our docker file and app folder (if not you have to specify the path)

- Once you run docker ` docker compose -f docker-compose.yml` this will create 2 new docker images and place them in containers

```
Define and run multi-container applications with Docker.

Usage:
  docker compose [-f <arg>...] [--profile <name>...] [options] [COMMAND] [ARGS...]
  docker compose -h|--help

Options:
  -f, --file FILE             Specify an alternate compose file
                              (default: docker-compose.yml)
  -p, --project-name NAME     Specify an alternate project name
                              (default: directory name)
  --profile NAME              Specify a profile to enable
  --verbose                   Show more output
  --log-level LEVEL           DEPRECATED and not working from 2.0 - Set log level (DEBUG, INFO, WARNING, ERROR, CRITICAL)
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
  --compatibility             If set, Compose will attempt to convert deploy
                              keys in v3 files to their non-Swarm equivalent

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
  version            Show the Docker Compose version information
```
