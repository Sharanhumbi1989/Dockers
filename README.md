# Docker
Docker projects
ubuntu@ip-172-31-10-1:~$ docker --help

Usage:  docker [OPTIONS] COMMAND

A self-sufficient runtime for containers

Common Commands:
  run         Create and run a new container from an image
  exec        Execute a command in a running container
  ps          List containers
  build       Build an image from a Dockerfile
  pull        Download an image from a registry
  push        Upload an image to a registry
  images      List images
  login       Log in to a registry
  logout      Log out from a registry
  search      Search Docker Hub for images
  version     Show the Docker version information
  info        Display system-wide information

Management Commands:
  builder     Manage builds
  container   Manage containers
  context     Manage contexts
  image       Manage images
  manifest    Manage Docker image manifests and manifest lists
  network     Manage networks
  plugin      Manage plugins
  system      Manage Docker
  trust       Manage trust on Docker images
  volume      Manage volumes

Swarm Commands:
  swarm       Manage Swarm

Commands:
  attach      Attach local standard input, output, and error streams to a running container
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  import      Import the contents from a tarball to create a filesystem image
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  wait        Block until one or more containers stop, then print their exit codes

Global Options:
      --config string      Location of client config files (default "/home/ubuntu/.docker")
  -c, --context string     Name of the context to use to connect to the daemon (overrides DOCKER_HOST env var and default context set with
                           "docker context use")
  -D, --debug              Enable debug mode
  -H, --host list          Daemon socket to connect to
  -l, --log-level string   Set the logging level ("debug", "info", "warn", "error", "fatal") (default "info")
      --tls                Use TLS; implied by --tlsverify
      --tlscacert string   Trust certs signed only by this CA (default "/home/ubuntu/.docker/ca.pem")
      --tlscert string     Path to TLS certificate file (default "/home/ubuntu/.docker/cert.pem")
      --tlskey string      Path to TLS key file (default "/home/ubuntu/.docker/key.pem")
      --tlsverify          Use TLS and verify the remote
  -v, --version            Print version information and quit

Run 'docker COMMAND --help' for more information on a command.

For more help on how to use Docker, head to https://docs.docker.com/go/guides/

Install EC2 inctance 

Install docker on EC2 Ubunut instance 
=======================================
sudo apt update
sudo apt install docker.io -y
sudo systemctl status docker
su - ubuntu
docker run hello-word
docker: permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/create": dial unix /var/run/docker.sock: connect: permission denied.

Add ubuntu user to docker group
===============================
sudo usermod -aG docker ubuntu  
logout from ubuntu user and login back
docker run hello-world
sudo systemctl stop docker
sudo systemctl stastus docker
sudo systemctl start docker

CLONE files from git repository
===============================
git clone https://github.com/iam-veeramalla/Docker-Zero-to-Hero
cd  examples

Build Docker image
==================
docker build -t sharanhumbi/my-first-docker-image:latest .

Verify docker image create
==========================
docker images

Run docker container
===================
docker run -it sharanmhumbi/my-first-docker-image:latest

Push docker image to docker hub
===============================
docker login -u sharanhumbi
==>password
docker push sharanhumbi/my-first-docker-image:latest

My docker hub
===============
https://hub.docker.com/repositories/sharanhumbi

Docker Netorking
=================
1. Bridge network
2. Host network
3. Overlay networking

Docker network ls
docker network create -d bridge my_bridge 

docker network ls
run -d --name frontend sharanhumbi/django-python-project
run -d --name backend sharanhumbi/django-python-project
docker run -d --name db --network=secure-net sharanhumbi/django-python-project

login to container
=======================
docker exec -it frontend /bin/bash
apt-get update
apt-get install iputils-ping -y
exit



