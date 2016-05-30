# rockermongo
Dockerization of excellent mongodb UI rockmongo http://rockmongo.com/

[![Docker Stars](https://img.shields.io/docker/stars/tonysickpony/rockermongo.svg?maxAge=2592000)](https://hub.docker.com/r/tonysickpony/rockermongo/)
[![Docker Pulls](https://img.shields.io/docker/pulls/tonysickpony/rockermongo.svg?maxAge=2592000)](https://hub.docker.com/r/tonysickpony/rockermongo/)


## run

To connect to a mongo database from localhost, simply run
`docker run --detach --name rockermongo --env MONGO_HOST=localhost --env MONGO_PORT=27017 --publish 80:80 tonyfu/rockermongo`


To connect to a mongo container, either use the good old link flag
```
docker run --detach --name mongodb  mongo
docker run --detach --name rockermongo --link mongodb:mongo --env MONGO_HOST=mongo --publish 80:80 tonyfu/rockermongo
```
or use the docker network
```
docker run --detach --name mongo --net my_network mongo
docker run --detach --name rockermongo --net my_network --env MONGO_HOST=mongo --publish 80:80 tonyfu/rockermongo
```

To connect to a url, run
```
docker run --detach --name rockermongo --env MONGO_HOST=[remote url] --publish 80:80 tonyfu/rockermongo
```
