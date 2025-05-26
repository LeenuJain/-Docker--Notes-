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

# Docker vs Virtual Machines

## Virtual Machines
Virtual machines (VMs) enable running multiple operating systems simultaneously on a single physical machine without affecting the host operating system.

**Memory allocation in VMs:** For each VM specific amount of memeory is allocated from the host memory based on the OS type and software and which cannot be changed even if it is not utilized fully.
- VMs require fixed memory allocation from the host system
- Memory is reserved regardless of actual utilization
- **Example:** With an 8GB host machine:
  - Creating two 4GB VMs is possible
  - Creating one 4GB VM and one 6GB VM is impossible due to fixed allocation constraints

## Cloud Computing
When using AWS EC2 instances:
  - Each instance occupies a standard amount of memory
  - Higher memory usage directly increases costs
  - Resources remain allocated even when underutilized

## Docker
- In Docker we create containers which are just like VMs  but they are not VMs.  
- This allocates memory for each container once it is activated and returns back the memory to host memory post deactivation, so that other containers can utilize this memory.  
- Also one more advantage is it does not require to install os in the container it just takes it form the docker hub when activated making it light weight.
  
  - **Dynamic Memory Management:** Containers only use memory when active and release it when inactive
  - **Resource Efficiency:** Other containers can utilize freed memory
  - **Lightweight Design:** No need to install separate operating systems for each container
  - **On-Demand Resources:** Container images are pulled from Docker Hub when needed

This approach makes Docker more efficient, cost-effective, and flexible compared to traditional virtual machines.
