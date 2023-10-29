# Docker
Docker projects

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

