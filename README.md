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



For building the Docker master using the Dockerfile instaned of compose - 

    $ docker build -t jenkins-docker .

<br /> 
<br /> 

For running the Docker-image - 

    $ docker run -itd  -v /var/run/docker.sock:/var/run/docker.sock --name jenkins-docker  jenkins-docker


<br /> 
<br /> 

# Compose the containers 
    $ docker-compose -f docker-compose.yaml up -d

<br /> 

> visit http://localhost:8080

### collect the initial password login under - 
    $ /var/jenkins_home/secrets/initialAdminPassword

<br />
<br />


# Configure Jenkins for Slave

* Install Yet Another Docker Plugin in your Jenkins: Go to Manage Jenkins >> Manage Plugin >> Search for Yet Another Docker Plugin >> Install after restart >> Restart Jenkins when no job is running.

* Enable TCP port for JNLP agents: Jenkins is Java Network Launch Protocol, Jenkins slave will communicate with Jenkins Master on this protocol. Go to Manage Jenkins >> Configure Global Security >> Agent >> Select for Fixed and put 9080.





