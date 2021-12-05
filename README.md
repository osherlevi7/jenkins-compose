# jenkins-docker


### Setting up Jenkins Master 
Prerequisites: 
* Server with docker deamon.
* Compatible docker-compose on the server.
* Expose API server for docker daemon.

### This Project using the best practic methods : 

* Create an docker socket for building container inside container.
> In this project we run master container and many other slaves as a docker containers
<br /> 
<br /> 

# Compose the containers 
    $ docker-compose -f docker-compose.yaml up -d

<br /> 

> visit http://localhost:8080

<br /> 
<br /> 

For building the Docker master using the Dockerfile instaned of compose - 

    $ docker build -t jenkins-docker .

<br /> 
<br /> 

For running the Docker-image - 

    $ docker run -itd  -v /var/run/docker.sock:/var/run/docker.sock --name jenkins-docker  jenkins-docker




