# Docker
- Docker is an open-source platform that enables developers to package their applications and dependencies into lightweight containers.  
- These containers encapsulate everything an application needs to run, including code, runtime, system tools, and libraries.  
- Docker containers are portable, scalable, and consistent across different environments, making it easier to develop, deploy, and manage applications.

Think of containers as lightweight, portable boxes that include everything needed to run a piece of software:  
- The code
- Runtime environment
- System tools
- Libraries
- Settings

## Key Benefits

- **Consistency**: Your application runs the same way everywhere
- **Isolation**: Applications don't interfere with each other
- **Efficiency**: Uses fewer resources than virtual machines
- **Portability**: Build once, run anywhere (laptop, cloud, etc.)

Docker makes it easy to develop, ship, and run applications without worrying about "but it works on my machine" problems.

## Real-World Example

Imagine you built a website using Python:

- **Without packaging**: You'd need to tell others "Install Python 3.9, then these 15 libraries, configure these settings..."
- **With Docker packaging**: You create one container image with everything included, and simply say "Run this Docker container"

It's like putting all ingredients for a recipe into one box, so anyone can easily cook the same dish without hunting for each ingredient separately.

## Docker vs Virtual Machines

### Virtual Machines
Virtual machines (VMs) enable running multiple operating systems simultaneously on a single physical machine without affecting the host operating system.

**Memory allocation in VMs:** For each VM specific amount of memeory is allocated from the host memory based on the OS type and software and which cannot be changed even if it is not utilized fully.
- VMs require fixed memory allocation from the host system
- Memory is reserved regardless of actual utilization
- **Example:** With an 8GB host machine:
  - Creating two 4GB VMs is possible
  - Creating one 4GB VM and one 6GB VM is impossible due to fixed allocation constraints

### Cloud Computing
When using AWS EC2 instances:
  - Each instance occupies a standard amount of memory
  - Higher memory usage directly increases costs
  - Resources remain allocated even when underutilized

### Docker
In Docker we create containers which are just like VMs but they are not VMs. This allocates memory for each container once it is activated and returns back the memory to host post deactivation, so that other containers can utilize this memory.  
One more advantage is it does not require to install os in the container it just takes it form the docker hub when activated making it light weight.  
  - **Dynamic Memory Management:** Containers only use memory when active and release it when inactive
  - **Resource Efficiency:** Other containers can utilize freed memory
  - **Lightweight Design:** No need to install separate operating systems for each container
  - **On-Demand Resources:** Container images are pulled from Docker Hub when needed

This approach makes Docker more efficient, cost-effective, and flexible compared to traditional virtual machines.

## Docker points
- Docker is a open source centralised platform designed to create, deploy and run applications.
- Docker uses containers on the host OS to run applications. It allows applications to use the same linux kernal as a system on the host computer rather than creating a whole virtual os.
- We can install docker on any os but docker engine runs natively on Linux distribution.
- Docker is written in 'go' language.
- Docker was first released in March 2013 and it is developed by Solomon Hykes and Sebastian Pahl.
- Docker is a set of Paltofrm as a Service that uses **Os level virtualisation** whereas VMware uses **Hardware level Virtualisation**.

## Advantages
- No preallocation of RAM
- CI Efficiency : Docker enables you to build a container image and use that  same image accross every step  of the deployment process (can reuse the image)
- Less cost
- light in weight
- It can run on physical hardware/ Virtual hardware or on cloud
- it takes very less time to create a container

## Disadvantages
- Docker is not a good solution for application that requires rich GUI
- Difficult to manage large amount of containers
- Docker does not provide cross-platform compatability means if an application is designed to run in a docker container on windows, then it can't run on linux or vice versa
- Docker is suitable when the deployement os and testing os are same. if the os is different we should use VMs.
- No soultion for data recovery and backup

## Docker Architecture
![image](https://github.com/user-attachments/assets/8aa1df16-8792-4566-9a56-f0e78fe4a8df)  
### Docker Engine:
- The Docker Engine is the heart of the Docker platform. It comprises two main components:
- **Docker Daemon (dockerd)** : The Docker daemon runs on the host machine and is responsible for managing Docker objects, such as images, containers, networks, and volumes.
- **Docker Client** : The Docker client is a command-line interface (CLI) tool that allows users to interact with the Docker daemon through commands. Users can build, run, stop, and manage Docker containers using the Docker CLI.Docker client uses commands and REST API to communicate with the docker daemon.
- The CLI processes your commands, converts them to API requests, and waits for the response from the Docker daemon. It’s the daemon that’s responsible for actually starting containers, building images, and handling the other Docker operations you invoke with the CLI.  
### Docker Images:
- Docker images are the building blocks of containers. They are read-only templates that contain the application code, runtime, system tools, libraries, and other dependencies. Docker images are created from Dockerfiles, which are text files containing instructions for building the image layer by layer.
- ways to create a docker image:
    - take image from docker hub
    - create image from docker file
    - create image from existing docker containers  
### Docker Containers:
- Docker containers are runnable instances of Docker images. They encapsulate the application and its dependencies, providing an isolated environment for execution. Containers can be created, started, stopped, moved, and deleted using Docker commands.  
### Docker Registry:
- Docker Registry is a centralized repository for storing and sharing Docker images. The default public registry is Docker Hub, where users can find a vast collection of images. Organizations can also set up private registries to store proprietary images securely.  
### Docker Compose:
- Docker Compose is a tool for defining and running multi-container Docker applications. It uses a YAML file (docker-compose.yml) to specify services, networks, volumes, and other configurations required for the application. Docker Compose simplifies the management of complex applications composed of multiple interconnected containers.  
### Docker Volumes:
- Docker volumes are used for persisting data generated by and used by Docker containers. They provide a way for containers to store and share data independently of the container lifecycle, ensuring data persistence and portability.  
### Docker Networking:
- Docker provides networking capabilities for containers to communicate with each other and with external networks. It uses software-defined networks (SDN) to create virtual networks, enabling connectivity and isolation. Users can create custom networks, connect containers to networks, and define network policies using Docker commands or Docker Compose.

![image](https://github.com/user-attachments/assets/8e013942-1ebf-40f7-bdb2-437c64b974b0)

## Commands in Docker
| **Docker Command** | Description |
| ------------------ | ----------- |
| **`service docker status`** | checks service is started or not |
| **`docker images`** | Lists all images present in your machine |
| **`docker search jenkins`** | To search for jenkins images in docker |
| **`docker ps`** | Shows running containers |
| **`docker ps -a`** | Shows all containers (running and stopped) |
| **`docker pull <image>`** | Downloads an image from Docker Hub. example: docker pull jenkins. This will download jenkins image |
| **`docker run <image>`** | Creates and starts a container from an image. ex: docker run jenkins |
| **`docker stop <container>`** | Stops a running container. ex: docker stop jenkinscontainer |
| **`docker start <container>`** | starts a containers. ex: docker start <LOCATION> |
| **`docker attach <container>`** | goes inside a containers. ex: docker attach jenkinscontainer |
| **`docker rm <container>`** | Removes a stopped container ex: docker rm jenkinscontainer  |
| **`docker rmi <image>`** | Removes an image ex: docker rmi jenkins |
| **`docker exec -it <container> <command>`** | Executes a command in a running container |
| **`docker build -t <name>`** | Builds an image from a <LOCATION> in current directory |
| **`docker commit <container_id/name> <new_image_name>`** | Creates a new image from an existing container with its changes. This command is useful when you've made changes to a container (installed software, modified files, etc.) and want to save those changes as a new image. |
| **`docker diff <container_id/name>`** | Shows changes to files and directories in a container's filesystem compared to its base image. This displays the files that were added (A), deleted (D), or modified (C) in the container compared to its original image. |

## Docker file
- Docker is basically a text file. It contains some set of instructions.
- Automation of docker image creation.

### Dockerfile Instructions
| **Instruction** | **Description** |
| --------------- | --------------- |
| **`FROM <image>`** | Defines a base for your image. |
| **`MAINTAINER <name>`** | Specifies the author of the image (deprecated, use LABEL instead). |
| **`RUN <command>`** | Executes any commands in a new layer on top of the current image and commits the result. RUN also has a shell form for running commands. |
| **`WORKDIR <directory>`** | Sets the working directory for any RUN, CMD, ENTRYPOINT, COPY, and ADD instructions that follow it in the Dockerfile. |
| **`COPY <src> <dest>`** | Copies new files or directories from <src> and adds them to the filesystem of the container at the path <dest>. |
| **`ADD <src> <dest>`** | Similar to COPY but with additional features - can handle remote URLs and automatically extract compressed files. |
| **`EXPOSE <port>`** | Informs Docker that the container listens on the specified network port(s) at runtime. for exmaple to expose ports such as 8080 port for tomcat. port 80 for nginx etc |
| **`CMD <command>`** | Lets you define the default program that is run once you start the container based on this image. Each Dockerfile only has one CMD, and only the last CMD instance is respected when multiple exist. |
| **`ENTRYPOINT <command>`** | Configures the container to run as an executable. Often used with CMD, where ENTRYPOINT specifies the executable and CMD specifies the parameters. |
| **`ENV <key>=<value>`** | Sets environment variables in the container. These values will be available to processes running inside the container. |


  
