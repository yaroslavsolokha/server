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
#### Joomla
##### 1. Create project
```
$ cd server/projects
$ git clone https://github.com/joomla/joomla-cms.git
```
##### 2. Add joomla.dev to you hosts
##### 3. Build docker
```
$ cd server
$ docker-compose stop
$ docker-compose -f docker-compose.yml -f joomla.yml build
$ docker-compose -f docker-compose.yml -f joomla.yml up
```
##### 4. Update
```
$ cd server
$ docker exec -it php /bin/sh
$ cd joomla-cms
$ composer install
$ composer update
```
##### 5. Check joomla.dev:8000, setup, host - 172.19.0.1, administrator panel - http://joomla.dev:8000/administrator/
#### WordPress
##### 1. Create project
```
$ cd server/projects
$ git clone https://github.com/WordPress/WordPress.git
```
##### 2. Add wordpress.dev to you hosts
##### 3. Build docker
```
$ cd server
$ docker-compose stop
$ docker-compose -f docker-compose.yml -f wordpress.yml build
$ docker-compose -f docker-compose.yml -f wordpress.yml up
```
##### 4. Check wordpress.dev:8000, setup, manually create db, host - 172.19.0.1
#### Drupal
##### 1. Create project
```
$ cd server/projects
$ git clone https://github.com/drupal/drupal.git
```
##### 2. Add drupal.dev to you hosts
##### 3. Build docker
```
$ cd server
$ docker-compose stop
$ docker-compose -f docker-compose.yml -f drupal.yml build
$ docker-compose -f docker-compose.yml -f drupal.yml up
```
##### 4. Update
```
$ cd server
$ docker exec -it php /bin/sh
$ cd drupal
$ composer install
$ composer update
```
##### 5. Check drupal.dev:8000, setup, host - 172.19.0.1, administrator panel - http://joomla.dev:8000/administrator/