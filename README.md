# docker-commands
Some docker commands line 

# Basic commands

## Remove all containers
```
docker rm -f $(docker ps -a -q)
```

## Remove all images
```
docker rmi -f $(docker images -q)
```

## Search an image 
```
docker search <key>
```

## Pull an image
```
docker pull <repository>
```

## Run an image as container
```
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]

docker run --name=mysqlCon -p 3306:3306 -d -e MYSQL_ROOT_PASSWORD=123456 mysql/mysql-server:5.7
```

## Show logs a container
```
docker logs [container name]
```

## Login to the container
```
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]

sudo docker exec -it mysqlCon mysql -uroot -p
```

## Build an image from container
```
docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]

docker commit -m "upload" c3f279d17e0a  mountainchan/test:v1
```

## Push an Image to docker hub
```
docker push IMAGE [REPOSITORY[:TAG]]

docker push mountainchan/test:v1
```

## Remove an Image
```
docker rmi [OPTIONS] IMAGE [IMAGE...]

docker rmi -f mountainchan/test:v1
```

## Show containers
```
docker ps # containers are running

docker ps -a # show all
```

## Stop/Start/Restart/Remove a container
```
docker container start/stop/restart/rm [container id]
```

## Stop/remove all containers
```
docker stop/rm $(docker ps -a -q)
```

## Remove all Images
```
docker rmi -f $(docker images -a -q)
```

#  Volume commands

## Basic comand
```
docker volume create [volume name]      Tạo mạng mới
docker volume inspect  [volume name]    Xem chi tiết mạng
docker volume ls                        Hiển thị những mạng đang có
docker volume rm     [volume name]      Xóa volume
docker volume prune                     Xóa toàn bộ volumn
```

## Tao mot vulume mysql_data sau do tao mot container mysql luu du lieu vao day
```
docker volume create mysql_data
docker container run --name mysql -v mysql_data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -p 3306:3306 -d mysql:5.7
```

#  Networks

## Basic comand
```
docker network create       [nerwork name]       Tạo mạng mới
docker network inspect      [nerwork name]       Xem chi tiết mạng
docker network ls                                Hiển thị những mạng đang có
docker network rm           [nerwork name]       Xóa mạng
docker network prune                             Xóa đồng loạt các mạng không sử dụng
docker network connect      [nerwork name]       Tạo kết nối mạng
docker network disconnect   [nerwork name]       Ngắt kết nối mạng
```

## Tạo 1 mạng lớp C, tao 2 container su dung lop mang do, roi kiem tra ket noi giua 2 con container
```
docker network create --subnet 192.168.1.0/24 network1
docker run -itd --name=container1  --network network1 busybox
docker run -itd --name=container2  --network network1 busybox

docker attach container1
ping 192.168.1.3
```
