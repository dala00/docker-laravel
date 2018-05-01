# laravel-apache

This repository contains a script for create [Laravel](https://laravel.com/) server image.

You can use these tags as a version of PHP.

- `7.2`

### docker-compose

```
app:
    image: dala00/laravel-apache:7.2
    volumes:
      - .:/var/www/app
    ports:
      - "8000:80"
    tty: true
    stdin_open: true
```
