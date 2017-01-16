# Fujimisakari Apps With Docker

## Overview

Manage my Applications by docker.

- Applications is:
  - otherbu
  - fuel-todo
  - trac


## Setup apps

```sh
$ git clone https://github.com/fujimisakari/docker-fujimisakari-apps.git
$ cd docker-fujimisakari-apps

# otherbu
$ git clone https://github.com/fujimisakari/otherbu

# todo
$ git clone https://github.com/fujimisakari/todo-server todo

# fuel-todo
$ git clone https://github.com/fujimisakari/fuel-todo
$ ./fuel-todo/composer.phar install

# trac
$ git clone https://github.com/fujimisakari/trac

$ mkdir mysql/log
$ mkdir -p nginx/log/otherbu nginx/log/todo nginx/log/fuel-todo nginx/log/trac
```


## Create docker image

```sh
$ cd otherbu
$ docker build . -t fujimi_otherbu

$ cd todo
$ docker build . -t fujimi_todo

$ cd fuel-todo
$ docker build . -t fujimi_fuel-todo

$ cd trac
$ docker build . -t fujimi_trac

$ cd nginx
$ docker build . -t fujimi_nginx

$ cd mysql
$ docker build . -t fujimi_mysql
```


## Initialize Apps

```sh
$ ./docker-compose.sh dev up

# otherbu
$ docker exec -it fujimi_otherbu_dev ./env/init.sh develop

# todo
$ docker exec -it fujimi_todo_dev ./env/init.sh develop

# fuel-todo
$ docker exec -it fujimi_fuel-todo ./init.sh

let exit docker-compose
```


## Docker Run

```sh
$ ./docker-compose.sh [dev|prod] up
```
