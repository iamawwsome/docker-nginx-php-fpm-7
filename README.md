## CentOS 7: Docker, Nginx, and php-fpm

This will build the neccessary services (nginx and php-fpm) to serve php files.

The project directory will mount to ```/opt/app```.

```
docker-compose -p php -f docker-compose.yml up
```

The example php website should be accessible at http://localhost
