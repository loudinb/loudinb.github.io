# Docker - Getting Started

## Knowledge Check Questions

1.  **True or False:** The `-d` flag in the `docker run` command runs the container in the foreground.

2.  Which of the following docker run flags is used to map ports between the host and the container?

* A) `-port`
* B) `-pmap`
* C) `-p`
* D) none of the above

3.  The Docker ________ provides a quick view of containers running on your machine and allows you to manage their lifecycle.

* A)  CLI
* B)  Dashboard
* C)  Engine
* D)  Registry

4.  A container image provides the isolated ________ for a container.

* A)  Network
* B)  Filesystem
* C)  Memory
* D)  CPU

5.  What is a Dockerfile?

* A)  A compiled binary file that runs containers.
* B)  A text-based script of instructions to create a container image.
* C)  A graphical user interface for Docker.
* D)  A network configuration file for Docker.

6.  What is the standard filename used to define instructions for building a Docker image?

* A)  `docker-image.txt`
* B)  `Containerfile`
* C)  `Dockerfile`
* D)  `image.def`

7.  The `_______` instruction in a Dockerfile specifies the base image to start from.

* A)  RUN
* B)  CMD
* C)  FROM
* D)  COPY

8.  **True or False:** The `docker build` command is used to run a container from an image.

9.  Which command is used to start a container from a Docker image?

* A)  `docker build`
* B)  `docker start`
* C)  `docker run`
* D)  `docker create`

10. **True or False:**  If you don't map ports when running a container, you can still access the application running inside from your host machine's browser.

11. Which command is used to stop a running Docker container?

* A)  `docker kill`
* B)  `docker halt`
* C)  `docker stop`
* D)  `docker pause`

12. The command `docker ______` is used to remove a stopped container.

* A)  `remove`
* B)  `delete`
* C)  `rm`
* D)  `erase`

13. **True or False:**  You must stop a container before you can remove it.

14. What is Docker Hub?

* A)  A command-line tool for Docker.
* B)  A type of Docker volume.
* C)  A cloud registry for Docker images.
* D)  A network configuration tool for Docker.

15. To share a Docker image, you first need to _____ it with a new name that includes your Docker Hub username.

* A)  build
* B)  push
* C)  tag
* D)  run

16. **True or False:** The `docker push` command is used to upload a Docker image to a registry like Docker Hub.

17. What happens to data created inside a container's filesystem when the container is removed if volumes are not used?

* A)  It is automatically backed up to Docker Hub.
* B)  It is persisted on the host machine.
* C)  It is lost.
* D)  It is moved to a named volume automatically.

18.  ________ provide the ability to connect specific filesystem paths of the container back to the host machine for data persistence.

* A)  Networks
* B)  Images
* C)  Volumes
* D)  Registries

19. **True or False:** Named volumes are physically stored inside the container image.

20. What is the primary purpose of bind mounts in a development workflow?

* A)  To persist database data.
* B)  To share container images with others.
* C)  To mount source code into a container for live development.
* D)  To improve container security.

21. Bind mounts give you the ability to  _________ the mount point on the host machine that is connected to the container.

* A)  randomly assign
* B)  let Docker choose
* C)  completely hide
* D)  specify and control

22. To enable communication between two Docker containers, they must be connected to the same Docker _________.

* A)  Volume
* B)  Image
* C)  Network
* D)  Registry

23. **True or False:** By default, containers on the same machine can automatically communicate with each other without being on the same network.

24. What is Docker Compose used for?

* A)  Building single container images.
* B)  Defining and managing multi-container applications.
* C)  Monitoring container resource usage.
* D)  Securing Docker containers.

25. Docker Compose uses a _______ file to define the services of a multi-container application.

* A)  .Dockerfile
* B)  .dockercompose
* C)  .compose
* D)  .docker-compose.yml

26. **True or False:** The command `docker compose up` is used to start all services defined in a Docker Compose file.