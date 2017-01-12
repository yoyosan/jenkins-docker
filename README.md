# Jenkins Docker

This is a simple to setup and run Jenkins with Nodes locally/remotely using Docka' Powa'.

## Installation steps

```
# start the Jenkins master container
$ mkdir -p ~/opt/jenkins
$ docker-compose up -d
# pull my jenkins slave image
$ docker pull yoyosan/jenkins-slave:latest
```

Now, follow the guide [here](https://wiki.jenkins-ci.org/display/JENKINS/Docker+Plugin) and profit!

## Screenshots

**Build index**

![Build index](http://i.imgur.com/bhigpiA.png "Build index")

**Build output**

![Build output](http://i.imgur.com/NkuWjHc.png "Build output")
