---
layout: post
title: Useful commands
date: 2023-6-13
description: Some useful cheatsheet for coding
categories: research
giscus_comments: true
---
> Docker
- Set up an experiment environment based on Ubuntu
1. First pull and delopy my Docker image (OS:_ubuntu 20.04_, shell:_zsh_, IDE:_code-server_) from Docker hub
`
sudo docker pull winstonli96/ubuntu_env
sudo docker run --name ENV_NAME -it -p PORT_NUM:8080 zsh
`
_NOTE: change ENV_NAME and PORT_NUM accordingly_

2. Then start the IDE
`
code-server
`
and change the ==password== in _~/.config/code-server/config.yaml_

3. Access to your IDE
Start a web browser, the IDE is open at ==SERVER_IP_ADDRESS:PORT_NUM==

