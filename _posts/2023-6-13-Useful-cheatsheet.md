---
layout: post
title: A useful cheatsheet come in handy
date: 2023-6-13
description: Some useful cheatsheet for coding
categories: research
giscus_comments: true
---

> Outline

1. [Experiment environment in docker](#experiment-environment-in-docker)
    - [Setup an Ubuntu environment](#setup-an-ubuntu-environment)
2. [Linux Commands Cheatsheet](#linux-commands-cheatsheet)
    - [Navigation](#navigation)
    - [File Operations](#file-operations)
    - [Process Management](#process-management)
    - [System Information](#system-information)
    - [Networking](#networking)
    - [Package Management](#package-management)
    - [Compression and Archiving](#compression-and-archiving)
    - [Permissions](#permissions)
3. [Docker Commands Cheatsheet](#docker-commands-cheatsheet)
    - [Images](#images)
    - [Containers](#containers)
    - [Networks](#networks)
    - [Volumes](#volumes)
    - [Compose](#compose)
    - [System](#system)
    - [Registry](#registry)
    - [Miscellaneous](#miscellaneous)

---

<!-- <details>
<summary><b>Details</b></summary>

_Markdown is valid, but add empty lines to separate from the HTML tags._

- Bullet
- Points

</details> -->

# Experiment environment in docker

## Setup an Ubuntu environment

1. First pull and delopy my Docker image (OS: __ubuntu 20.04__, shell: __zsh__, IDE: __code-server__) from Docker hub
```bash
sudo docker pull winstonli96/ubuntu_env:v1.0
sudo docker run --name ENV_NAME -it -p PORT_NUM:8080 winstonli96/ubuntu_env:v1.0 zsh
```
_NOTE: change **ENV_NAME** and **PORT_NUM** accordingly_

2. Then start the IDE
```bash
code-server .
```
and change the **password** in ```~/.config/code-server/config.yaml```. Default password: ```password```. Use ```Ctrl+P+Q``` to close and run the container in background.

3. Access to your IDE
Start a web browser, the IDE is open at ```SERVER_IP_ADDRESS:PORT_NUM```

---
# Linux Commands Cheatsheet

## Navigation

- `pwd`: Print the current working directory
- `ls`: List files and directories
  - `ls -a`: List all files and directories, including hidden ones
  - `ls -l`: List files and directories in long format
- `cd [directory]`: Change directory
  - `cd ..`: Go up one directory
  - `cd ~`: Go to the home directory
- `mkdir [directory]`: Create a new directory
- `rm [file]`: Remove a file
  - `rm -r [directory]`: Remove a directory and its contents recursively

## File Operations

- `touch [file]`: Create an empty file or update the access and modification times of an existing file
- `cp [source] [destination]`: Copy files and directories
  - `cp -r [source] [destination]`: Copy directories recursively
- `mv [source] [destination]`: Move or rename files and directories
- `cat [file]`: Print the contents of a file
- `head [file]`: Display the first few lines of a file
- `tail [file]`: Display the last few lines of a file
- `grep [pattern] [file]`: Search for a pattern in a file
- `wc [file]`: Count the number of lines, words, and characters in a file

## Process Management

- `ps`: Display information about active processes
  - `ps aux`: Display detailed information about all processes
- `kill [process_id]`: Terminate a process
  - `killall [process_name]`: Terminate all processes with a specific name
- `top`: Display real-time information about processes

## System Information

- `uname`: Print system information
  - `uname -a`: Print all system information
- `df`: Display disk space usage
- `free`: Display memory usage
- `uptime`: Display system uptime
- `who`: Display information about logged-in users

## Networking

- `ping [host]`: Send ICMP echo requests to a host
- `ifconfig`: Display network interface configuration
- `netstat`: Display network statistics
- `ssh [user]@[host]`: Connect to a remote host using SSH
- `scp [file] [user]@[host]:[destination]`: Copy files securely between hosts

## Package Management

- `apt-get`: Package handling utility for Debian-based systems
  - `apt-get update`: Update the list of available packages
  - `apt-get install [package]`: Install a package
  - `apt-get remove [package]`: Remove a package
- `yum`: Package manager for RPM-based systems (e.g., CentOS, Fedora)

## Compression and Archiving

- `tar`: Create or extract tar archives
  - `tar -czvf [archive.tar.gz] [file/directory]`: Create a gzip-compressed tar archive
  - `tar -xzvf [archive.tar.gz]`: Extract a gzip-compressed tar archive
- `zip`: Create or extract zip archives
  - `zip [archive.zip] [file/directory]`: Create a zip archive
  - `unzip [archive.zip]`: Extract a zip archive

## Permissions

- `chmod [permissions] [file]`: Change the permissions of a file
  - `chmod +x [file]`: Grant execute permission to a file
- `chown [user]:[group] [file]`: Change the owner and group of a file

---

# Docker Commands Cheatsheet

## Images

- `docker images`: List all available images
- `docker pull [image]:[tag]`: Download an image from a registry
- `docker build -t [image_name]:[tag] [path]`: Build an image from a Dockerfile
- `docker push [image]:[tag]`: Push an image to a registry
- `docker rmi [image]:[tag]`: Remove an image

## Containers

- `docker run [image]:[tag]`: Run a container from an image
  - `docker run -d [image]:[tag]`: Run a container in detached mode
  - `docker run -p [host_port]:[container_port] [image]:[tag]`: Run a container and map ports
  - `docker run -v [host_path]:[container_path] [image]:[tag]`: Run a container and mount volumes
  - `docker run --name [container_name] [image]:[tag]`: Run a container with a specified name
- `docker ps`: List running containers
  - `docker ps -a`: List all containers (running and stopped)
- `docker start [container]`: Start a stopped container
- `docker stop [container]`: Stop a running container
- `docker restart [container]`: Restart a container
- `docker rm [container]`: Remove a stopped container
- `docker logs [container]`: Display the logs of a container
- `docker exec -it [container] [command]`: Execute a command in a running container

## Networks

- `docker network ls`: List available networks
- `docker network create [network]`: Create a network
- `docker network connect [network] [container]`: Connect a container to a network
- `docker network disconnect [network] [container]`: Disconnect a container from a network

## Volumes

- `docker volume ls`: List available volumes
- `docker volume create [volume]`: Create a volume
- `docker volume inspect [volume]`: Inspect a volume
- `docker volume rm [volume]`: Remove a volume

## Compose

- `docker-compose up`: Start containers defined in a Compose file
  - `docker-compose up -d`: Start containers in detached mode
- `docker-compose down`: Stop and remove containers defined in a Compose file
- `docker-compose ps`: List containers managed by Compose

## System

- `docker system df`: Show Docker disk usage
- `docker system prune`: Remove unused Docker data (containers, networks, images, and volumes)
- `docker system prune -a`: Remove all unused Docker data, including unused images

## Registry

- `docker login`: Log in to a Docker registry
- `docker logout`: Log out from a Docker registry
- `docker search [term]`: Search for an image in a Docker registry

## Miscellaneous

- `docker info`: Display Docker system information
- `docker version`: Display Docker version information







