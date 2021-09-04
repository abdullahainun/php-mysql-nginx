# php-mysql-nginx
### Requirement
- docker
- docker compose

How to install
1. Cloning project
```
git@github.com:abdullahainun/php-mysql-nginx.git
```
2. Run Project
```
docker-compose exec app composer update
docker-compose exec php app artisan key:generate
docker-compose build
docker-compose up -d
Creating network "php-mysql-nginx_travellist" with driver "bridge"
Creating travellist-app   ... done
Creating travellist-nginx ... done
Creating travellist-db    ... done
```
3. visit apps
Visit http://localhost:8000/
