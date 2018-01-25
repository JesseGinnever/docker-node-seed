# Docker Node.js Seed

This project is a seed project for a Docker contained Node.js server

## Prerequisites

All you will need to get this project deployed is [Docker](https://docs.docker.com/engine/installation//)

## Deployment

To get started you will need to navigate to the root directory (directory with the Dockerfile) and build your docker container. 

```
docker build -t <your username>/node-web-app .
```

You can now verify that your docker container was created

```
$ docker images
 
# Example
REPOSITORY                      TAG        ID              CREATED
node                            carbon     1934b0b038d1    5 days ago
<your username>/node-web-app    latest     d64d3505b0d2    1 minute ago
```

You can then run your docker container to start your web application
```
$ docker run -p 49160:8080 -d <your username>/node-web-app
```


## Useful Docker commands

```
# Get container ID
$ docker ps
 
# Print app output
$ docker logs <container id>
 
# Example
Running on http://localhost:8080
```

If you need to go inside the container you can use the exec command:
```
# Enter the container
$ docker exec -it <container id> /bin/bash
```

## Test

You can now test that your Docker container, with your Node.js server, is up and running!

```
$ docker ps
 
# Example
ID            IMAGE                                COMMAND    ...   PORTS
ecce33b30ebf  <your username>/node-web-app:latest  npm start  ...   49160->8080
```

In the example above, Docker mapped the 8080 port inside of the container to the port 49160 on your machine.
 
You can now test your [running Node.js server](http://localhost:49160/)
```
localhost:49160
 
HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: text/html; charset=utf-8
Content-Length: 12
ETag: W/"c-M6tWOb/Y57lesdjQuHeB1P/qTV0"
Date: Mon, 13 Nov 2017 20:53:59 GMT
Connection: keep-alive

Hello world
```

## Built With

* [npm](https://www.npmjs.com/) - Dependency Management
* [Node.js](https://nodejs.org/en/) - The web framework used
* [Docker](https://docs.docker.com/engine/installation//) - Contained deployement


## Authors

* **Jesse Ginnever** - *Initial work*

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* https://nodejs.org/en/docs/guides/nodejs-docker-webapp/

