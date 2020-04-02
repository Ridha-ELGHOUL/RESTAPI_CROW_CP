# RESTAPI_CROW_CP
A Demonstration for REST API and Data Access using C++ and CROW Framework and azure cloud for docker depoyment.
Used Data Base : Mongo DB Cloud hosted.
# Project Configuration and Env set up
Download the project : 
```sh
$ git clone https://github.com/Ridha-ELGHOUL/RESTAPI_CROW_CP.git 
```
Build docker image: 
```sh

``` 
add Volume :
```sh
$ docker run -v <host>:<container -ti <image> bash
```
Building Crow from Docker Image: (inside docker- No boost and dependencies exist on host machine )
```sh
cd /usr/src/cppweb
mkdir build & cd build
cmake ..
make 

```
Execute app from host:(open port and match it with docker port: example 8080)

```sh
docker run -v $LOCAL_HOST_PATH_PROJECT$:/usr/src/cppweb -p 8080:8080 -e PORT=8080  cppbox:latest  /usr/src/cppweb/demo-crow/build/demo_crow

```
- bbox folder:
```sh
$ docker build --rm --squash --no-cache -t bbox:latest . 

```
# DataBase Creation and configuration
# End point and Parsing Path
# Reading Query string.
This example  based on C++ REST API from linkedin learning   