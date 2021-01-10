
# WordPress install with docker-compose

## docker-compose.yaml

```yaml
version: '3.1'

services:

  wordpress:
    image: wordpress
    restart: always
    ports:
      - 8080:80
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: exampleuser
      WORDPRESS_DB_PASSWORD: examplepass
      WORDPRESS_DB_NAME: exampledb
    volumes:
      - ./wordpress:/var/www/html

  db:
    image: mysql:5.7
    restart: always
    environment:
      MYSQL_DATABASE: exampledb
      MYSQL_USER: exampleuser
      MYSQL_PASSWORD: examplepass
      MYSQL_RANDOM_ROOT_PASSWORD: '1'
    volumes:
      - db:/var/lib/mysql

volumes:
  wordpress:./wordpress
  db:
```


## In terminal

docker-compose up

![](docker-compose_up.png)




## Open web browser

http://localhost:8080/

![](WordPress_install_step01.png)




## Documentation
https://hub.docker.com/_/wordpress


## Thanks

Thanks to [technote-space](https://github.com/marketplace/actions/release-github-actions) for publish Github releases action.
