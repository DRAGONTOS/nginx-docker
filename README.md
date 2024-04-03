# nginx-docker
A docker container for running a nginx server!

## Configuring
By default the compose file won't work to make it work you need to add your name for your server like -smp, also you will need to set an ip for it. (I will give you an example on how to set it up for a proxy)
```
version: "3.8"

services:
  nginx:
    restart: always
    image: nginx:latest
    ports:
      - "80:80" # Change this if you want to use SSL or anything else.
    volumes:
      - "./data/conf/nginx.conf:/etc/nginx/nginx.conf" # The nginx config. 
      - "./data/sites/:/etc/nginx/conf.d/" # This has the configuration for configuring sites and enabling them.
      - "./data/html/:/var/www/html/" # Where the website source code resides.
      - "./data/certs/:/etc/certs/" # Put your SSL certificates in here!
``` 
Happy configuring!

## Spinning them up!
To first test it, run the container without -d, but when it all works, you can just use -d (example):

### Without -d for testing
```
docker-compose up
```

### With -d for daemoninzing 
```
docker-compose up -d
```

# Contributors
- DRAGONTOS

