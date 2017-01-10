# Fujimisakari Apps With Docker

## Overview

Manage my Applications by docker.


## Setup apps

```sh
$ git clone https://github.com/fujimisakari/docker-fujimisakari-apps.git
$ git submodule init
$ git submodule update

$ mkdir mysql/log
$ mkdir -p nginx/log/otherbu
```


## Create docker image

```sh
$ cd otherbu
$ docker build . -t fujimi_otherbu

$ cd nginx
$ docker build . -t fujimi_nginx

$ cd mysql
$ docker build . -t fujimi_mysql
```


## Setup Apps

```sh
# otherbu
$ ./docker-compose.sh dev up
$ docker exec -it fujimi_otherbu_dev ./env/otherbu_init.sh develop
let exit docker-compose
```


## Docker Run

```sh
$ ./docker-compose.sh [dev|prod] up
```
