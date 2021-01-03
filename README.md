# docker-commands
Some docker commands line 

# Search an image 
```
docker search <key>
```

# Pull an image
```
docker pull <repository>
```

# Run an image as container
```
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]

docker run --name=mysqlCon -p 3306:3306 -d mysql/mysql-server:5.7
```

# Show logs a container
```
docker logs [container name]
```

# Login to the container
```
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]

sudo docker exec -it mysqlCon mysql -uroot -p
```

# Build an image from container
```
docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]

docker commit -m "upload" c3f279d17e0a  mountainchan/test:v1
```

# Push an Image to docker hub
```
docker push IMAGE [REPOSITORY[:TAG]]

docker push mountainchan/test:v1
```

# Remove an Image
```
docker rmi [OPTIONS] IMAGE [IMAGE...]

docker rmi -f mountainchan/test:v1
```

# Show containers
```
docker ps # containers are running

docker ps -a # show all
```

# Stop/Start/Restart/Remove a containers
```
docker container start/stop/restart/rm [container id]
```
