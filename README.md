# Gnosis SFTP Service

Simple SFTP server using [atmoz/sftp](https://hub.docker.com/r/atmoz/sftp) image. <br> 
This repository is used to simply set the environment variables and use the docker-compose file to easily deploy an sftp server for [gnosis_main_service](https://github.com/damsog/gnosis-main-service) although it can be used for any application.

For more information about the face recognition application refer to : [gnosis_main_service](https://github.com/damsog/gnosis-main-service)

## :clipboard: Requirements
The nodejs dependencies can be installed simply by using ```npm ci```.

##### :penguin: Dependencies
- [Docker](https://docs.docker.com/engine/install/ubuntu/)

### :whale2: *Run as Container*

Before deploying the service you have to set up the environment variables. create a file called .env and copy the content from .base.env
```sh
cp .base.env .env
```
Let's explain the parameters to set on the .env file. <br>
Set the path to serve through the SFTP protocol (where to save the files). and set the access cretentials to access the service and the port tor run
```
FILES_PATH=<path>
SFTP_USER=<user>
SFTP_PASSWORD=<password>
SFTP_PORT=<port>
```

Run Docker container. deploy using the docker compose file
To run using docker compose
```sh
docker compose up
```
or in detatched mode
```sh
docker compose up -d
```
to stop 
```sh
docker compose down
```

Check outputs 
```sh
docker logs --tail N <container_id>
```