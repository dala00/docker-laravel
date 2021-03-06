# laravel-apache

This repository contains a script for create [Laravel](https://laravel.com/) server image.

You can use these tags as a version of PHP.

- `7.3`
- `7.2`

### docker-compose

```
app:
  image: dala00/laravel:7.2
  volumes:
    - .:/var/www/app
  ports:
    - "8000:80"
  tty: true
  stdin_open: true
```

full sample

```
version: '2'
volumes:
  mysql_data:
    driver: 'local'
services:
  mysql:
    image: mysql:5.7
    volumes:
      - mysql_data:/var/lib/mysql
    ports:
      - 3307:3306
    environment:
      MYSQL_ALLOW_EMPTY_PASSWORD: "true"
      MYSQL_DATABASE: yourdb

  phpmyadmin:
    image: phpmyadmin/phpmyadmin
    environment:
      - PMA_ARBITRARY=1
      - PMA_HOST=mysql
      - PMA_USER=root
      - PMA_PASSWORD=
    ports:
      - 8001:80

  app:
    image: dala00/laravel:7.3
    volumes:
      - .:/var/www/app
    working_dir: /var/www/app
    ports:
      - "8000:80"
    tty: true
    stdin_open: true
```
