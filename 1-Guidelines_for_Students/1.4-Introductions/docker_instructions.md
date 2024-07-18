[Back to Home](../../README.md) / [1.4 Introductions](1.4-introductions.md) / **Docker Instructions**

<hr>

## Introduction

When you install a program you have to have a certain operating system, install other dependencies, libraries, etc. All this is done in the same environment and can collide with other programs. Docker solves all these problems because it encapsulates your application in a same work environment (container). In simpler terms, e.g if you want to run a ROS package without having to install ROS (not even Ubuntu!) on your local computer, Docker is the answer. We encourage you to use this tool! To do this, you must follow the following instructions:

Note: This is just a practical quick guide to Docker. Reading the article [R. White and H. Christensen. ROS and Docker](https://www.researchgate.net/publication/317751755_ROS_and_Docker) is recommended for a better understanding of the relationship between ROS and Docker.
## Install Docker

1- Depending on your operating system, follow the installation steps on the official page:

```
https://docs.docker.com/engine/install/
```

2- To avoid having to write the word "sudo" in each command and enable Docker for other functionalities such as container handling in VS code, it is recommended to follow this additional step (for Linux users only):

```
https://docs.docker.com/engine/install/linux-postinstall/
```

## Run Docker


The best way to learn about Docker is with an example. To do this we will execute the package "cmake_python_package" found in the guidelines of this repository with this tool and we will analyze the most important concepts.

The first step is to clone the package and go to its path from the terminal. 

```
$ cd ~/docker_packages/cmake_python_package
```

If you look at the files inside the package, you will see one called Dockerfile. With this you can build an image. In analogy with an .iso image this created image will contain the operating system, ROS and all the dependencies you need for your package. 

To build the image you must execute the following commands

```
$ export GIT_USERNAME=myusername
$ export GIT_PASSWORD=mypassword
$ chmod +x build.sh
$ ./build.sh
```

The first two commands are your gitlab account credentials and the last two are to build the image. If you open the build.sh file, you will see that the image will be called "cmake_python: dev".


You already have the image created for your package, but now you need to "install" it. You can install it several times and each of these instances is what is known as a container. To run a container, execute:

```
docker run -it cmake_python_package:dev
```

Another terminal will open. There you have everything you need to run your package. You do not need to source the terminal, docker has made it for you.

## Explanation of the Dockerfile


The first thing you'll see in the dockerfile is the command

```
FROM ros:dashing-ros-base-bionic
```

Dockerfile works with layers. This means that the following commands written in the file are based on a dashing ROS image and so on with each command. Also ros:dashing-ros-base-bionic is built based on other images:

```
->ubuntu:bionic
-->ros:dashing-ros-core-bionic
--->ros:dashing-ros-base-bionic
---->ros:dashing-ros-desktop-bionic
```


In this [link](https://github.com/osrf/docker_images/tree/df19ab7d5993d3b78a908362cdcd1479a8e78b35/ros/dashing/ubuntu/bionic) you can learn in more detail about each of these dockerfiles. 
In general terms, if the application requires a GUI like Rviz, gazebo, etc. the appropriate image is ros-desktop, otherwise ros-base.


The next step is to install all the necessary dependencies. For example in this example cmake 3.18.4 is required. Finally the workspace is created and compiled

## Useful Commands


The following are some of the most commonly used commands. Please read the official documentation to know more

1- To build an image (with a point at the end):
```
docker build -t ImageName:Tag .
```

2- To run a container:
```
docker run -it ImageName:Tag
```
with arguments: [doc](https://docs.docker.com/engine/reference/commandline/run/)
```
-d Run container in background and print container ID
-e Set environment variables
-h Container host name
-i Keep STDIN open even if not attached
-p Publish a container's port(s) to the host
-P Publish all exposed ports to random ports
-t Allocate a pseudo-TTY
-u Username or UID (format: <name|uid>[:<group|gid>])
-v Bind mount a volume
-w Working directory inside the container
--privileged Give extended privileges to this container
--rm Automatically remove the container when it exits
--name Assign a name to the container
```

3- To run another terminal of the same container:
```
docker exec -it IdContainer_or_Name bash
```

4- To see info about the images
```
docker images
```

5- To see info about the containers
```
docker ps (show active containers)
docker ps -a (show all containers)
```

6- Remove container or image
```
docker rmi IdImage_or_name
docker rmi $(docker images -q --filter "dangling=true") (delete all unused images)
docker rm IdContainer_or_name
docker rm $(docker ps -aq) -f   (delete all the containers)
```
7- Start or stop container
```
docker start IDcontainer
docker stop IDcontainer
docker restart IDcontainer
```
## Networking

Each container will be one or more ROS packages and you want them to communicate with each other. So, do you need to do something extra? ... No, docker creates a virtual network, so you do not have to run any extra commands.


and if you want to communicate a node of a container with my host? 
There are basically two ways (the second one is general and works for the next case). The easiest way is to run the container with the --network host argument. Example:

```
docker run --network host -it cmake_python:dev 
```

and if you want to communicate wit other computer? 
This also applies if containers are not used and it is by indicating the IP address of the other device in the ROS_MASTER_URI variable. Example (in your container):

```
export ROS_MASTER_URI=http://192.168.10.02:11311/
```
## VS Code and Docker

Working only from the terminal can be tedious. That is why it is advisable to install the Docker plugin in VS Code so that you can easily edit the container files

## Docker compose

This is a very useful tool if you need to run more than one container, with just one command! To use it you must install it following the instructions in the link:

```
https://docs.docker.com/compose/install/
```

If you want to see a complete example that makes use of all these concepts or need more inspiration, please see the PeTRA project

## Clone gitlab packages in Dockerfile / Access tokens
You can use a project access token to authenticate with Git, when using HTTP Basic Authentication.

To create a project access token:

1. On the top bar, select **Menu > Projects** and find your project.
1. On the left sidebar, select **Settings > Access Tokens**.
1. Enter a name.
1. Optional. Enter an expiry date for the token. The token will expire on that date at midnight UTC.
1. Select a role for the token.
1. Select the [desired scopes](https://www.w.hs-karlsruhe.de/gitlab/help/user/project/settings/project_access_tokens#scopes-for-a-project-access-token). (Write permissions not needed)
1. Select **Create project access token**.

In your Dockerfile create an enviroment variable for username and token:

```Docker
ENV GIT_<package>_NAME project_{project_id}_bot
ENV GIT_<package>_TOKEN {project_token}
```
You find your `project_id` on the repo page.

In your Dockerfile clone like this:

```Docker
RUN git clone https://$GIT_<package>_NAME:$GIT_<package>_TOKEN@www.w.hs-karlsruhe.de/gitlab/iras/<path-to-repo>.git
```