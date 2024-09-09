## Docker vs Virtual Machine
 Docker's `containers` are lightweight, Need less hardware resources, Use OS of host

 VMs SLow to start, Resource intensive, Each VM needs a full-blown OS

 ## Creating Images
 To create image just add Dockerfile to your application folder

 ## IMAGE
 To create image you need to run Dockerfile. But before you need to instruct Dockerfile. You need to specify:
 * A cut-down OS
 * Aruntime enviroment (eg Python)
 * Application files
 * Third-party libraries
 * Environmental variables

 ```Dockerfile
 FROM Python:alpine #which language : which linux
 COPY . /app        #copy all to (if not exits creates) /app in container
 WORKDIR /app       # telling working folder
 CMD python main.py # what command and which file

**Explanations: Copies all from python:alpine container(all kind of containers exist in Dockerhub and it copies from there) to my container
```


## BUILDING CONTAINER
To create container you need to run your IMAGE
```Bash
docker build -t my_container . # you need -t to give tag name  , and show location fo image. ' . ' if you are in folder. my_container is name of image
```

 ## Docker codes

```Bash
Docker version # Shows version
docker image ls # Shows all images , and image id on machine
docker ps # Shows running containers add flag -a to see all containers
docker run my_container # runs IMAGE and creates CONTAINER . Runs CMD command
docker run -it my_container /bin/bash # overwrites CMD and opens Linux bash for manually using terminal inside container
```

## LINUX DISTROS (MOST COMMON)
* **UBUNTU**
* **DEBIAN**
* **ALPINE**
* **FEDORA** 
