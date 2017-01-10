# Jenkins Docker

This is a simple to setup and run Jenkins with Nodes locally/remotely using Docka' Powa'.

## Installation steps

```
# start the Jenkins master container
$ mkdir -p ~/opt/jenkins
$ docker-compose up -d

############################################
# setting up the docker slave base container
############################################
$ docker pull clearlinux:latest
$ docker run -it clearlinux /bin/bash
# in the container, execute the following
$ swupd update
$ swupd bundle-add java-basic openssh-server
$ adduser jenkins
$ passwd jenkins
$ /usr/bin/ssh-keygen -A
$ mkdir /var/empty
$ /usr/sbin/sshd
$ exit
# you've now exited the container
$ docker ps -a
$ docker commit <container_id> mpalade/jenkins-slave
# remove the container since it's no longer needed
$ docker rm <container_id>
```

Now, follow the guide [here](https://wiki.jenkins-ci.org/display/JENKINS/Docker+Plugin) and profit!

## Screenshots

**Build index**

![Build index](http://i.imgur.com/bhigpiA.png "Build index")

**Build output**

![Build output](http://i.imgur.com/NkuWjHc.png "Build output")
