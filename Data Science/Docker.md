### 🔹 1. **Docker**

> Docker is a platform used to **develop, ship, and run applications** inside lightweight, portable **containers**.
### 🔹 2. **Container**

> A container is a **lightweight, standalone, executable package** that includes everything needed to run a piece of software: code, runtime, libraries, and system tools.

- Think of it as a **mini virtual machine**, but much faster and more efficient.
- Container - way to package applications with all the necessary dependencies and configurations
	- portable artifact, easily share and move this package to any environment
	- development and deployment -> efficient n in sync
![[Pasted image 20250807121214.png]]
### 🔹 3.Docker **Image**

> An image is a **read-only template** used to create containers. It includes the application and its environment.

- Example: Python image, Node.js image, Ubuntu image.
![[Pasted image 20250807121246.png]]
### 🔹 4. **Dockerfile**

> A text file containing **instructions to build a Docker image**.
![[Pasted image 20250807121453.png]]
# docker image n container differences
- docker image -> run -> container (start image)
- containerize/ dockerize -> create layers of image
- container -> layers of image
# Docker vs Virtual machine
- both virtualize os
- docker image -> virtualize application layer
	- communicate with host os kernel
- vm ->virtualize application layer AND os kernel  
	- vm has it's own os kernel -> communicate with hardware
![[Pasted image 20250807122058.png]]
- When u install vm, u need allocate seperate resources to it (ram , storage) etc
- Docker -> image size -> small
	- container start n run much faster (only application layer)
	- <mark style="background: #FFF3A3A6;">can't be installed on any os</mark> (can't install linux docker on windows os etc)
- VM -> image size -> huge
	- slower start n run (application+ own kernel)
	- <mark style="background: #FFF3A3A6;">can be installed on any os</mark>


# Docker
- `docker`  or `docker -v` to check if docker is present
- dockerhub -> for public repos
- <mark style="background: #FFF3A3A6;">type the commands in cmd or terminal</mark>
```docker
docker images                 -> shows images
docker pull image_name        -> image gets downloaded
docker run -d -p image_name   -> run container (pulls and runs if image not present locally)
docker ps                 -> container working or not(gives container details)
docker stop container_id      -> stop the container from running
docker image rm image_id      -> remove the image 
docker image rm image_id -f   -> remove the image ,forcefully
```
- extras
```
-d          # detached mode (in background)
-p          # assigning port and mapping port , host to container
```
- u can pull based on tags
	- `:latest` -> pulls the latest version
- <mark style="background: #FFF3A3A6;"> we can run any no of containers on same port</mark>
- 