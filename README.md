# Deploying Wordpress in a Docker container

This is a documentation on deploying wordpress on a docker container. Running WordPress in Docker requires two separate containers: a web container, running Apache and PHP, and a database container, hosting MySQL.

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
Pulling wordpressdatabase (mysql:5.7)...
5.7: Pulling from library/mysql
6552179c3509: Pull complete
d69aa66e4482: Pull complete
3b19465b002b: Pull complete
7b0d0cfe99a1: Pull complete
9ccd5a5c8987: Pull complete
2dab00d7d232: Pull complete
64d3afdccd4a: Pull complete
6992e58be0f2: Pull complete
67313986b81d: Pull complete
7c36a23db0a4: Pull complete
d34c396e3198: Pull complete
Digest: sha256:afc453de0d675083ac00d0538521f8a9a67d1cce180d70fab9925ebcc87a0eba
Status: Downloaded newer image for mysql:5.7
Pulling wordpress (wordpress:latest)...
latest: Pulling from library/wordpress
5eb5b503b376: Pull complete
8b1ad84cf101: Pull complete
38c937dadeb7: Pull complete
6a2f1dc96e59: Pull complete
f8c3f82c39d4: Pull complete
90fc6462bd8e: Pull complete
c670d99116c9: Pull complete
12c48eb41a93: Pull complete
0c537b2632b2: Pull complete
21a949b7ce7d: Pull complete
6e7c48790426: Pull complete
e1b625ec6dbf: Pull complete
345e72046e34: Pull complete
d7a851be6127: Pull complete
51171b781f53: Pull complete
385570a6c642: Pull complete
d51b06a8c66e: Pull complete
bb2b7daa382a: Pull complete
9b8a3ec3f4ba: Pull complete
d52ff99361be: Pull complete
1a379f259e0d: Pull complete
Digest: sha256:3e28e1e0b732e1828028d7d500eb73f273fc8365215f633414e60cdc631e0d91
Status: Downloaded newer image for wordpress:latest
Creating wordpressdatabase ... done
Creating wordpress         ... done
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
