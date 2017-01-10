# Fujimisakari Apps With Docker

## Overview

Manage my Applications by docker.


## Setup apps

```sh
$ git clone https://github.com/fujimisakari/docker-fujimisakari-apps.git
$ cd docker-fujimisakari-apps

# otherbu
$ git clone https://github.com/fujimisakari/otherbu

# fuel-todo
$ git clone https://github.com/fujimisakari/fuel-todo
$ ./fuel-todo/composer.phar install

$ mkdir mysql/log
$ mkdir -p nginx/log/otherbu
$ mkdir -p nginx/log/fuel-todo
```


## Create docker image

```sh
$ cd otherbu
$ docker build . -t fujimi_otherbu

$ cd fuel-todo
$ docker build . -t fujimi_fuel-todo

$ cd nginx
$ docker build . -t fujimi_nginx

$ cd mysql
$ docker build . -t fujimi_mysql
```


## Initialize Apps

```sh
$ ./docker-compose.sh dev up

# otherbu
$ docker exec -it fujimi_otherbu_dev ./env/otherbu_init.sh develop

# fuel-todo
$ docker exec -it fujimi_fuel-todo ./init.sh

let exit docker-compose
```


## Docker Run

```sh
$ ./docker-compose.sh [dev|prod] up
```
