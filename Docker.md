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
 **MUSTS
 FROM Python:alpine #which language : which linux
 COPY . /app        #copy all to (if not exits creates) /app in container
 WORKDIR /app       # telling working folder
 CMD python main.py # what command and which file - always last line
 **Arguments
 ENV name "Chingiz" # give environmental variable to container
 VOLUME ["/path/in/container"] #
 EXPOSE <port> # exposing port to container
 RUN pip install selenium # runs code to install ,export etc (everything the program(main.py) will need)
 *
 ENTRYPOINT ["python main.py"] # unlike CMD it cant be overwritten and will always run
 ** using togheter with cmd
 ENTRYPOINT ["python"]
 CMD ["main.py"]  # you cant overwrite entrypoint but cmd can ("main2.py" etc)
 
**Explanations: FROM - Brings all from python:alpine container(all kind of containers exist in Dockerhub and it copies from there) to my container so container has OS and Language
```
## VOLUMES
 Docker volume is like an external storage space where you can save data from your container so that it doesn’t get lost when the container stops or is deleted. Containers themselves are temporary, and once they stop or are removed, all data inside them usually disappears. You can use same volume data(lets say it has data base) among couple containers.
 You can also use Volume to change container. If you change something in volume the container binded tp this will also change. So instead building cotainer every time , you can do this.
 Volumes can be Binded or just Named. Binded when you choose folder to become volume and store data where in Named Docker itself creates folder somwhere. So better use Binded.


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
docker container prune # to remove all non-running container
docker image prune # to remove all dangling images 
```

## Dockercompose
Installing
```Bash
sudo apt install docker-compose -y
```
Create folder for Docker-compose
And create file called **docker-compose.yaml**
```Bash
docker-compose up




## Dockerhub
To be able to interact you need to login
```Bash
Docker login
```


## LINUX DISTROS (MOST COMMON)
* **UBUNTU**
* **DEBIAN**
* **ALPINE**
* **FEDORA** 
