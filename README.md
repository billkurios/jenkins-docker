# Jenkins

[Jenkins](https://jenkins.io/) is an open source automation server. It helps automate the CI/CD (Continouos Integration, Continouos Delivering, Continouos Deployment) pipeline of software development.

# How to use this project
### Clone the project
```shell
git clone https://github.com/billkurios/jenkins-docker
```

### Environment variables
Create a `.envs` file and add environment variables. 
This is a file example.
```txt
VOLUME_ROOT_FOLDER='./.tmp_data'
JK_DOCKER_VERSION='dind'
JK_DOCKER_CONTAINER_NAME='jk-docker'
JENKINS_VERSION='2.391-jdk11'
DOCKER_TLS_CERTDIR='/certs'
DOCKER_HOST='tcp://${JK_DOCKER_CONTAINER_NAME}:2376'
DOCKER_CERT_PATH='${DOCKER_TLS_CERTDIR}/client'
DOCKER_TLS_VERIFY=1
```

### Docker compose
To run your jenkins docker, just run:
```shell
docker compose --env-file .envs up -d
```

`-d` is used to run in background, you can add it or remove it. It's optional.

To stop it:
```shell
docker compose down
```

# About
### License
MIT

### References
[https://www.jenkins.io/doc/book/installing/docker/](https://www.jenkins.io/doc/book/installing/docker/)

[https://docs.docker.com/compose/compose-file/](https://docs.docker.com/compose/compose-file/)

[https://docs.docker.com/compose/compose-file/build/#args](https://docs.docker.com/compose/compose-file/build/#args)