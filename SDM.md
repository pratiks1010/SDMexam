 ## sudo docker run --name docker-nginx -p 80:80 -d nginx


 ## sudo docker container ls
CONTAINER ID   IMAGE     COMMAND              CREATED         STATUS     PORTS    NAMES
bae03e0cea2c   nginx     "/docker-entrypoint.…"   3 minutes ago   Up 3 minutes   0.0.0.0:80->80/tcp, :::80->80/tcp   docker-nginx



## sudo docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
nginx        latest    448a08f1d2f9   8 days ago    142MB
mysql        latest    8189e588b0e8   3 weeks ago   564MB



# sudo docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                                                                                                                       PORTS                                                  NAMES
6df9b7d3ae81   mysql     "docker-entrypoint.s…"   3 minutes ago    Up 3 minutes                                                                                                                 0.0.0.0:3306->3306/tcp, :::3306->3306/tcp, 33060/tcp   some-mysql
bae03e0cea2c   nginx     "/docker-entrypoint.…"   11 minutes ago   Up 11 minutes                                                                                                                0.0.0.0:80->80/tcp, :::80->80/tcp                      docker-nginx



## sudo docker run -d -p 8081:8081 iacsd
fdf785bb6981e0fb35785d6ae6d67014101eecc72c28da3d20d9e27bd0602d9e


##  sudo docker run -d -p 8081:8081 iacsd
7af58a5fa37c86eecc18257534febca0beea3668109bcc2c6602a37aa8a5223a


## web/iacsdrepomarch23$ sudo docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS         PORTS                                       NAMES
fdf785bb6981   iacsd     "/bin/sh -c 'node se…"   4 minutes ago   Up 4 minutes   0.0.0.0:8081->8081/tcp, :::8081->8081/tcp   silly_pare


## running sir website 

# (-- sudo docker run -d -p 8081:8081 iacsd----)
## cmd> http://65.2.11.148:8081/