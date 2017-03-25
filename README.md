**Setup**

Docker environment for Symfony projects.

1. Install Docker - https://docs.docker.com/compose/install/

2. Clone repository and configure shared paths in Docker

3. Start everything up:


    $ cd server
    $ docker-compose build
    $ docker-compose up
    
4. Check Nginx, PHP, PHPMyAdmin. Open:

    
    localhost:8000
    localhost:8000/phpinfo.php
    localhost:8010
    
5. Add symfony.dev and demo.dev to your hosts

6. Add symfony projects:


    $ cd server
    $ docker exec -it php /bin/sh
    $ symfony new symfony
    $ cd symfony
    $ composer update
    $ cd ..
    $ symfony new demo
    $ cd demo
    $ composer update
    
7. Check symfony.dev:8000 and demo.dev:8000