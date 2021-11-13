# Docker files sandbox

## Build dockerfile to create docker image
```
sudo docker build -t < docker-image-name > .
```

## Build dockerfile in another location
```
sudo docker build . -t < docker-image-name > -f <path-to-docker>/Dockerfile
```

## Check list of built docker images

```
sudo docker image ls
```

## Check list running docker containers

```
sudo docker ps
```

## Run docker container using image

### Interactive
```
sudo docker run --name < container-name > --rm -i -t < image-name >
```

### Run in the background
```
sudo docker run --name < container-name > --rm -d -t < image-name >
```



## Remove container then remove image

### Stop container
```
sudo docker stop < container-name  >
```

```
sudo docker rm < container-id  >
```

```
sudo docker image rmi < image-id  >
```


### Start shell in running container
```
sudo docker exec -it < container-image > /bin/bash
```

### Run bash script inside docker container running

```
sudo docker exec < container-name > bash -c "bash <full-path>/bash-script.sh"
```


# Recipe
1. Build docker file
``` 
sudo docker build . -t marsvin-image -f <path-to-dockerfile>/Dockerfile
``` 
2. Run container using docker image: Go to directory where code is located
```
sudo docker run --name marsvin-container --rm -d -t marsvin-image
```
3. Copy files you need to build from host to container. Go to directory with source code and run
```
sudo docker cp . marsvin-container:/tmp/app_dir/
```
4. Run build script inside docker container
```
sudo docker exec marsvin-container bash -c "bash /tmp/app_dir/build-code.sh"
```

