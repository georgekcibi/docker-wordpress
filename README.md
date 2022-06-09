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
root@ip-172-31-19-187:~/wordpres# docker-compose up -d
Creating network "wordpres_wordpress_network" with the default driver
Creating volume "wordpres_database" with default driver
Creating volume "wordpres_wordpress1" with default driver
Pulling wordpressdatabase (mysql:5.7)...
5.7: Pulling from library/mysql
c1ad9731b2c7: Pull complete
54f6eb0ee84d: Pull complete
cffcf8691bc5: Pull complete
89a783b5ac8a: Pull complete
6a8393c7be5f: Pull complete
af768d0b181e: Pull complete
810d6aaaf54a: Pull complete
81fe6daf2395: Pull complete
5ccf426818fd: Pull complete
68b838b06054: Pull complete
1b606c4f93df: Pull complete
Digest: sha256:7e99b2b8d5bca914ef31059858210f57b009c40375d647f0d4d65ecd01d6b1d5
Status: Downloaded newer image for mysql:5.7
Pulling wordpress (wordpress:latest)...
latest: Pulling from library/wordpress
42c077c10790: Pull complete
8934009a9160: Pull complete
5357ac116991: Pull complete
54ae63894b5a: Pull complete
772088206f85: Pull complete
3b81c5474649: Pull complete
c62a528527ae: Pull complete
4386b832d751: Pull complete
23b4fb100c69: Pull complete
9339b1ed77ad: Pull complete
6ad6583eba04: Pull complete
05e5f60f6add: Pull complete
744e7c78b843: Pull complete
d23996fdbd01: Pull complete
e47d68ad6905: Pull complete
06463c6b8395: Pull complete
935032d9891a: Pull complete
7b825b5ea5ac: Pull complete
4f882ef71278: Pull complete
ed9050832178: Pull complete
39f9aa71aa04: Pull complete
Digest: sha256:06c850f59d7bd1b96462fc6287e88f0cd08724077e54d9872c9002449b74309c
Status: Downloaded newer image for wordpress:latest
Pulling phpmyadmin (phpmyadmin:)...
latest: Pulling from library/phpmyadmin
42c077c10790: Already exists
8934009a9160: Already exists
5357ac116991: Already exists
54ae63894b5a: Already exists
772088206f85: Already exists
3b81c5474649: Already exists
c62a528527ae: Already exists
63666c622ffa: Pull complete
0de5e53aad5f: Pull complete
8e05551834b5: Pull complete
cf8fbd2cecc4: Pull complete
6c8265911726: Pull complete
7852d9eb2ff4: Pull complete
06cb18a830a4: Pull complete
fbf6e91b00bd: Pull complete
96f1280a5c8b: Pull complete
ad2ad24f6f53: Pull complete
3ef4edcc0334: Pull complete
Digest: sha256:e7dcb2033604b806128abeb0314cf4a0ae4acd11f8c6c157ae7ec2e8ddad095e
Status: Downloaded newer image for phpmyadmin:latest
Creating wordpress         ... done
Creating phpmyadmin        ... done
Creating wordpressdatabase ... done
```

- ### You can now see containers running

```
root@ip-172-31-19-187:~/wordpres# docker ps
CONTAINER ID   IMAGE              COMMAND                  CREATED          STATUS          PORTS                                   NAMES
0b3aa57bef66   mysql:5.7          "docker-entrypoint.s…"   10 minutes ago   Up 10 minutes   3306/tcp, 33060/tcp                     wordpressdatabase
caae1c8585f9   phpmyadmin         "/docker-entrypoint.…"   10 minutes ago   Up 10 minutes   0.0.0.0:8080->80/tcp, :::8080->80/tcp   phpmyadmin
3c2d87eb3c25   wordpress:latest   "docker-entrypoint.s…"   10 minutes ago   Up 10 minutes   0.0.0.0:80->80/tcp, :::80->80/tcp       wordpress
```

- ### Load IP in your browser and complete the wordpress setup

![Alt text](https://github.com/georgekcibi/docker-wordpress/blob/main/wordpress.png)

![Alt text](https://github.com/georgekcibi/docker-wordpress/blob/main/wordpress2.png)
