Android Development Environment

using Docker

![hello](icon.png)

---

### What is Docker

- software container platform
- automates the task of setting up and configuring development environment |
- build once, run anywhere |
- lightweight - a process, not a virtual machine |
- uses Linux kernel features like cgroups and namespaces to isolate |
- previously based on LXC, but now uses libcontainer

---

![whale](http://blog.docker.com/wp-content/uploads/2014/03/docker-execdriver-diagram.png)

---

## Example of Docker

`docker run -i -t ubuntu bash`

- downloads an ubuntu image (if needed)
- launches an interactive container running bash
- run `ps aux` - only bash is there

+++

`docker images`

List the images on your system

+++

`docker ps`

List the running containers

+++

`docker rmi`

To delete an image.

There can be so called 'dangling images' - use `clean.sh`

---

Why using Docker for development environment

- one defined environment
- everyone use the same environment
- perhaps useful in ~6 months when new versions of various tools/packages exist
- environment can be automatically verified to e.g. build AOSP

---

## What is an image and container

- container is an instance of an image
- there can be many instances of the same image

---

## Build a Docker image

- Dockerfile
- `docker build`
- `build.sh` - wrapper with useful options

---

## Run a Docker image

- `docker run [options] <image-name>`
- `run.sh` - wrapper with lots of options, like mounting points, X11 and user id
- `adk` - bash function to run container from any directory

+++

## Examples

- `adk bash` - to start an interactive shell and e.g. build AOSP
- `adk studio` - start a Android Studio
- `adk code` - or Visual Studio Coden

## User ID

The `run.sh` script etc will configure a user in the container with the same
user id and group id as your user on host.
--> any created file in container is owned by user

---

## Questions?

