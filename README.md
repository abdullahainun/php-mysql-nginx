# Installation manually on ubuntu 20.04
1. Update system
```
apt-get update -y
apt-get upgrade -y
```
2. Install apache and php
```
apt-get install apache2 php7.4 libapache2-mod-php7.4 php7.4-curl php-pear php7.4-gd php7.4-dev php7.4-zip php7.4-mbstring php7.4-mysql php7.4-xml curl -y

```
3. Install composer
```
curl -sS https://getcomposer.org/installer | php
mv composer.phar /usr/local/bin/composer
chmod +x /usr/local/bin/composer
```
4. Install apps
```
cd src
composer install
php artisan key:generate
cd ..
sudo cp -R src/ /var/www/html/travellist
```
5. Configure Apache to Serve travellist App
```
sudo a2ensite travellist.conf
sudo a2enmod rewrite
sudo systemctl restart apache2
```
# Installation with Docker and Docker Compose
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
