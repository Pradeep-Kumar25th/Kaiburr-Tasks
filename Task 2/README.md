# Task 2


**NOTE:** [README First](/README.md)

### Requirements

- Java
- Maven
- Spring Boot (Framework)
- MongoDB
- Docker

#### Dependencies

- spring-boot-starter-web
- spring-boot-starter-data-mongodb
- spring-boot-maven-plugin
- springfox-swagger2
- springfox-swagger-ui

## Building steps

1. Copy the `swagger.yaml` file contents to [Online Swagger Editor](http://editor.swagger.io/)

2. Click on `Generate Server` and choose  java-based server or server framework 
This will generate Server Stub.

3. Refactor the code according to the requiremets

4. Build the app by hitting following command
`mvn install`

5. Run the application by clicking `Run` option or pressing `F9`
SpringBoot application server will load and start on port `8080` of the `localhost`.

## Rest  API Endpoints and Resources
Rest API Endpoint is mapped to `http://127.0.0.1:8080/servers/`

- PUT a server	`http://127.0.0.1:8080/servers/createServer`
Accept "server" object in body in json format.

- GET servers	`http://127.0.0.1:8080/servers/getServer`
Returns a list of "server" objects.

- GET server	by ID	`http://127.0.0.1:8080/servers/getServer?id=<ID>`
Returns a  "server" object matching with ID.

- GET servers	by Name	`http://127.0.0.1:8080/servers/getServer?name=<Nmae>`
Returns a list of "server" objects matching with Name.

- DELETE server	`http://127.0.0.1:8080/servers/deleteServer?id=<ID>`
Deletes a  "server" object matching with ID.

## OpenAPI Documentation swagger.yaml snippet

```
swagger: '2.0'
info:
  description: 'This is a sample REST API with endpoints for searching, creating and deleting “server” objects.'
  version: 1.0.0
  title: Servers
  contact: {}
  license:
    name: Unlicense
    url: 'http://unlicense.org'
host: '127.0.0.1:8080'
basePath: /servers
tags:
  - name: createServer
    description: the createServer API
  - name: deleteServer
    description: the deleteServer API
  - name: getServer
    description: the getServer API
```

## Containerizing the app

`Dockerfile` contains all the commands required to build the app image

`
FROM openjdk:8-alpine
EXPOSE 8080
ADD target/demo.jar demo.jar
ENTRYPOINT ["java", "-Dspring.data.mongodb.uri=mongodb://mongod:27017/servers", "-jar", "/demo.jar"]
`

1. Run the following command to build docker image
`sudo docker build -t <container_image_name> .`
This will create the app container image and add to you local repository.

2. To Run the app from container, run the following command
`sudo docker run -p 80:80 <container_image_name>`
SpringBoot application server will load and start on port `8080` of the `localhost`
You will see application logs in the terminal.

**Note:** *The docker-compose part is Documented in Task3*

## Consuming APIs

A SwaggerUI is generated automatically at `http://127.0.0.1:8080/servers/` which Documentsthe API and gives UI to consume the same.

### Screenshots

![SwaggerDoc](/screenshots/task2SwaggerDoc.PNG)

![SwagGenServ](/screenshots/task2SwagGenServ.PNG)

![GetAllServ](/screenshots/task2GetAllServ.PNG)

# Swagger generated server

Spring Boot Server 


