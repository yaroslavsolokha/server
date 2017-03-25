### Docker setup
Docker environment include last versions of PHP, Nginx, MySQL.
#### Base server
##### 1. Install Docker - https://docs.docker.com/compose/install/
##### 2. Clone repository and configure shared paths in Docker
##### 3. Start everything up
```
$ cd server
$ docker-compose build
$ docker-compose up
```
##### 4. Check Nginx, PHP, PHPMyAdmin
```
localhost:8000
localhost:8000/phpinfo.php
localhost:8010
```
#### Symfony
##### 1. Add symfony.dev and demo.dev to your hosts
##### 2. Build docker
```
$ cd server
$ docker-compose stop
$ docker-compose -f docker-compose.yml -f symfony.yml build
$ docker-compose -f docker-compose.yml -f symfony.yml up
```
##### 3. Add symfony projects
```
$ cd server
$ docker exec -it php /bin/sh
$ symfony new symfony
$ cd symfony
$ composer update
$ cd ..
$ symfony new demo
$ cd demo
$ composer update
```
##### 4. Check symfony.dev:8000 and demo.dev:8000