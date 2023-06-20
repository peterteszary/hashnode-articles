---
title: "How to install Docker on Pop OS?"
datePublished: Sat Jan 28 2023 16:21:51 GMT+0000 (Coordinated Universal Time)
cuid: cldg5utm6000309ieddva3sxs
slug: how-to-install-docker-on-pop-os
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1674922836001/c31e51b5-73ec-4cf4-815a-21df6ffebf32.png
tags: docker, wordpress, popos

---

Docker is a powerful tool that allows developers to easily create, deploy, and run applications in containers. Containers are lightweight, self-contained environments that allow developers to package all of the dependencies and configurations required for an application to run in a single place, making it easy to move the application between different environments. In this blog post, we will walk through the process of installing Docker on Pop!\_OS, an Ubuntu-based Linux distribution.

I wrote this article because I am using DevKinsta on my Pop OS PC, as a local WordPress environment. So It needs Docker to run, and I did not want to search for several Stackoverflow posts, to get things done If I have to reinstall my PC in the future. Also, it might help you as well :)

Before we begin, it is important to note that Pop!\_OS is based on Ubuntu, so the instructions in this guide should also work on Ubuntu and other Ubuntu-based distributions.

The first step in installing Docker on Pop!\_OS is to update the system packages. Open a terminal and run the following command:

`sudo apt update`

This will update the package list to ensure that we are installing the latest version of Docker.

Next, we need to install some dependencies that Docker requires. Run the following command to install these dependencies:

`sudo apt install -y apt-transport-https ca-certificates curl software-properties-common`

After the dependencies are installed, we can add the Docker repository to our system. Run the following command to do this:

`curl -fsSL` [`https://download.docker.com/linux/ubuntu/gpg`](https://download.docker.com/linux/ubuntu/gpg) `| sudo apt-key add -`

`sudo add-apt-repository "deb [arch=amd64]` [`https://download.docker.com/linux/ubuntu`](https://download.docker.com/linux/ubuntu) `$(lsb_release -cs) stable"`

With the repository added, we can now install Docker. Run the following command to do this:

`sudo apt update`

`sudo apt install -y docker-ce`

Now, Docker should be installed and running on your system. To verify that Docker is running, you can run the following command:

`sudo systemctl status docker`

This command should output information about the Docker service, including its current status. If Docker is running, you should see output similar to the following:

`● docker.service - Docker Application Container Engine Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled) Active: active (running) since Mon 2020-01-01 00:00:00 UTC; 1s ago`

If you see this, Docker is successfully installed and running on your system. To run Docker commands without using "sudo", add your user to the "docker" group with the following command:

`sudo usermod -aG docker $USER`

You will need to logout and login again for the changes to take effect.

Once you’ve completed the steps above, you can start using Docker on your Pop!\_OS system. You can use the `docker` command to interact with the Docker daemon, and you can use `docker-compose` to manage multiple containers at once.

Docker is a powerful tool that allows developers to easily create, deploy, and run applications in containers. By following the steps outlined in this guide, you should now have Docker installed and running on your Pop!\_OS system, and you can start using it to build and deploy your own applications.