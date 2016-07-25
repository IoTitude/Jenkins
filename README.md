# Jenkins
This repository contains Jenkins setup for [dockerized continuous integration.](https://github.com/IoTitude/docker_test_env/)
See [Wiki](https://github.com/IoTitude/docker_test_env/wiki) for details.


## Run with Docker-compose
Use docker-compose.yml to run Jenkins from ready docker images. It uses:  
* [iotitude/jenkins-data](https://hub.docker.com/r/iotitude/jenkins-data/)
* [iotitude/jenkins-slave](https://hub.docker.com/r/iotitude/jenkins-slave/)
* [iotitude/jenkins-master](https://hub.docker.com/r/iotitude/jenkins-master/)
* [iotitude/jenkins-nginx](https://hub.docker.com/r/iotitude/jenkins-nginx/)

To launch Jenkins in Rancher, use jenkins/rancher_docker-compose.yml.

## Build from dockerfiles
This Jenkins setup uses four dockerfiles from IoTitude/Jenkins repository: Jenkins master, slave, data volume and nginx proxy.  

If you want to pre install Jenkins plugins list them in jenkins/jenkins-master/plugins.txt

In Jenkins directory: 
```shell
# Builds images from the dockerfiles. Same as 'docker-compose build'.
make build

# Launch containers. Same as 'docker-compose up -d'.
make run
```
Now you have Jenkins running in containers and accessible at http://localhost/
