# Running wordpress is Docker containers

This is a documentation to create a Wordpress website using Docker containers. Running WordPress in Docker requires two separate containers: a web container, running Apache and PHP, and a database container, hosting MySQL.

## Prerequisites

- Need to install docker and docker-compose
- Basic knowledge on how to create Docker images and start Docker containers.
- Basic knowledge on how to install and use WordPress


## How to Deploy the website

- ### Clone application from GitHub

```
git clone https://github.com/georgekcibi/docker-wordpress.git
```

- ### Execute the docker-compose.yml

```
root@ubuntu:~/wordpresscomposer# docker-compose -f wordpress.yml up -d
Creating network "wordpresscomposer_default" with the default driver
Creating volume "wordpresscomposer_database" with default driver
Creating volume "wordpresscomposer_wordpress1" with default driver
Creating wordpress         ... done
Creating wordpressdatabase ... done
```

- ### You can now see containers running

```
root@ubuntu:~# docker ps
CONTAINER ID   IMAGE              COMMAND                  CREATED        STATUS        PORTS                                                  NAMES
76c179afb714   mysql:5.7          "docker-entrypoint.s…"   3 hours ago    Up 3 hours    3306/tcp, 33060/tcp                                    wordpressdatabase
b652065f2436   wordpress:latest   "docker-entrypoint.s…"   3 hours ago    Up 3 hours    0.0.0.0:8000->80/tcp, :::8000->80/tcp                  wordpress
```

- ### Load IP:8000 in your browser and complete the wordpress setup

![Alt text](https://github.com/georgekcibi/docker-wordpress/blob/main/wordpress.png)

![Alt text](https://github.com/georgekcibi/docker-wordpress/blob/main/wordpress2.png)
