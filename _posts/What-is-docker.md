---

layout: post
title:  "What is docker?"
date:   2023-08-05
tags: [Jekyll, GitHub, Markdown, Blog, Website]
---

In layman terms, docker is a platform which helps us to package an application along with its dependecies, libraries and configurations into a single unit called container.

A container usually runs one service or one part of an application. Docker manages all these different containers to ulitimately run the application in different compute enviroment.

Ultimately solving the problem for developers of "This runs on my machine only!"

Now lets tackle different components for working of docker,

Dockerfile: It is a text-file containing instructions like which base OS to use, which dependencies to install etc.

Docker Image: When we execute the dockerfile, eg. using the command docker build -t <repo-name>. The instructions inside the dockerfile are performed to store them as reusable template i.e Docker Image.
Basically, docker image is like a snapshot of the application along with the enviroment.

Next, when we run this image it becomes a container.
