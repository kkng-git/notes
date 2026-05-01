# Day 1

## Completed Tasks

### Docker Overview

- **Key: What is a container?**
  - Containers are a loosely isolated environment which packages applications and all their requirements for execution.
  - Since the container contains all of the installations required for the application, you don't need to rely on the host device's packages.

- **Image vs. Container**
  - **Image:**
    - A read only template with instructions on how to build a Docker container. It is configurable, and you can modify base images to create new images. For example, you can take a Ubuntu image and add a web server, your application, and other configurations that are needed to make your application run.
    - To build your own image, you create a Dockerfile that has instructions needed to create an image and run it. Each instruction in a Dockerfile creates a layer in the image.
  - **Container:**
    - Runnable instance of an image. You can create, start, stop, move or delete a container using Docker API or CLI. You can connect a network to it, attach a storage, and create new images based on the state.
    - You can configure a container during creation or start, and it is defined by its image.
    - A container itself is not persistent, but you can save state changes to a persistent storage before deleting a container.

- **Immutable packaging**
  - Packaging a docker container is done through configuring a Docker Image. Once an image is built, it is immutable, so the configuration is identical across all uses of the image. Building a container using the same image will produce the same container every time.
  - To update or make changes to an existing image, you need to create a new image.

- **Portability**
  - Since everything needed for an application is containerized, then it makes it really easy to reproduce onto any other device.

- **Startup speed**
  - Docker streamlines the development lifecycle by standardizing development environments inside containers.
  - When Dockerfiles are changed and images are rebuilt, then only the new layers (instructions) get rebuilt (advantage compared to other virtualization technologies).

- **Additional notes**
  - **Docker Daemon:** A process that handles building, running, and distributing Docker containers. Can be remote or local. Listens for Docker API requests and manages Docker objects such as images, containers, networks and volumes. Daemon can also connect to other daemons to manage Docker services.
  - **Docker client:** Primary way to interact with Docker. Commands such as "docker run" are delivered from the client to the daemon, using the Docker API. A client can connect to more than one daemon.

### Containers vs. VMs

- **Virtual Machine**
  - A virtual machine emulates an entire computer. This means it has its own guest OS, virtualized CPU, memory, disk, and network.
  - It runs on a hypervisor, which sits either on the OS or on the hardware.
  - Advantages include that it can emulate different operating systems on a single device and that it has strong isolation.
  - Disadvantages are that it is much heavier (takes more memory) and has slower startup time because it needs to emulate all the components of the computer.

  - **Hypervisor**
    - Software layer that allows multiple VMs to share the same hardware safely and efficiently.
    - It handles resource allocation and controls traffic.
    - To virtualize CPUs, it schedules VM processes onto the host's physical cores.
    - To virtualize memory, it maps virtual memory to physical RAM
    - It also emulates Network Interface Cards, file system disks, and Graphics Processing Units.
    - Finally, it isolates the virtual machines so that there is no interference.

    - **Type 1: Bare-Metal hypervisor**
      - This type of hypervisor sits directly on the hardware. It has better performance because there is no extra OS layer, and has stronger isolation.
      - This is used in cloud infrastructures like AWS, Azure, GCP

    - **Type 2: Hosted Hypervisor**
      - This type of hypervisor sits ontop of the host OS. This makes it easier to install with the cost of slightly more overhead.

  - **System VM vs Process VM**
    - System VM is the type that we have been describing as of now. It emulates the entire computer system by virtualizing different components of the computer. Each VM has its own kernel + OS, but it is very isolated and memory heavy.
    - Process VM runs a single process in a virtualized environment. It starts up when the process runs, and closes when the process closes. This is lighter than a container. It abstracts on the host OS by translating development code into any sort of machine code, making the language runnable on any sort of OS. Not the same as a container
    - KEY: Containers package the environment around the app, while process VMs translate code so that it can be run in any environment.

- **Container**
  - A container packages application dependencies, but utilizes the host OS instead of emulating a new OS.
  - Advantages are that it is much lighter (takes less memory), has a faster startup time, and can be used in high density, meaning that many instances of containers can be running on a device at one time.

## Questions

- **Why are containers faster than VMs?**
  - In terms of system VMs, containers do not emulate a guest OS like the VM does. Although, they both abstract hardware devices like file system, network cards, and memory.

- **Why do developers like containers?**
  - Containers are contained and portable, which means the applications and all of the dependencies are packaged into one instance. Its also lightweight, so many instances can run at the same time on the same device.
