# Docker

Docker is a tool that helps package software into containers. Package software means it bundles everything your application needs into one neat unit.

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
In Docker we create containers which are just like VMs  but they are not VMs. This allocates memory for each container once it is activated and returns back the memory to host memory post deactivation, so that other containers can utilize this memory.  
One more advantage is it does not require to install os in the container it just takes it form the docker hub when activated making it light weight.  
  - **Dynamic Memory Management:** Containers only use memory when active and release it when inactive
  - **Resource Efficiency:** Other containers can utilize freed memory
  - **Lightweight Design:** No need to install separate operating systems for each container
  - **On-Demand Resources:** Container images are pulled from Docker Hub when needed

This approach makes Docker more efficient, cost-effective, and flexible compared to traditional virtual machines.

## Docker points
- Docker is a open source centralised platform designed to create, deploy and run applications.
- Docker uses containers on the host OS to run applications. It allows applications to use the same linux kernal as a system on the host computer rather than creating a whole virtual os.
- We can install docke on any Os but docker wgine runs natively on Liux distribution.
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
![image](https://github.com/user-attachments/assets/85cefc98-548c-4c02-89fb-822a1f755d82)
