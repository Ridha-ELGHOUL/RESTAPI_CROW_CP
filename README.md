# RESTAPI_CROW_CP
A Demonstration for REST API and Data Access using C++ and CROW Framework and azure cloud for docker depoyment.
Used Data Base : Mongo DB Cloud hosted.


# Setting up Environnment  
Install Docker for :
- Windows (https://docs.docker.com/docker-for-windows/install/).
- Linux, ubuntu 18.04 (https://docs.docker.com/install/linux/docker-ce/ubuntu/).

Download the project : 
```sh
$ git clone https://github.com/Ridha-ELGHOUL/RESTAPI_CROW_CP.git 
```
Build docker image : 
```sh

$ docker build --rm --squash --no-cache -t bbox:latest
``` 

Enable squash option on docker build : 
``` sh
$ mkdir ~/.docker
$ echo '{ "experimental": "enabled" }' > ~/.docker/config.json
$ sudo systemctl restart docker
$ docker version
  ...
  Experimental: true
  ...
``` 
Run docker with bash (just for testing) : 
``` sh
$ docker run -ti bbox:latest bash 
``` 
add Volume :
```sh
$ docker run -v <host>:<container -ti <image> bash
```
Example:
```sh
$docker run -v /home/vmlx/RESTAPI_CROW_CP/:/usr/src/cppweb -ti bbox:latest bash
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
docker run -v $LOCAL_HOST_PATH_PROJECT$:/usr/src/cppweb -p 8080:8080 -e PORT=8080  cppbox:latest  /usr/src/cppweb/demo_crow/build/demo_crow

```
- bbox folder:
```sh
$ docker build --rm --squash --no-cache -t bbox:latest . 

``` 
# Setting up mongodb Database:
Install mongodb 
- ubuntu : https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/
- Windows : https://docs.mongodb.com/manual/tutorial/install-mongodb-on-windows/
Add json file : 
```sh
mongoimport -h vmlx.eastus.cloudapp.azure.com:27017 -d cppdb -c contacts -u sa --file contacts.json --type json --jsonArray
```
# End point and Parsing Path
# Reading Query string.
This example  based on C++ REST API from linkedin learning   
