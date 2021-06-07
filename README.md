# Project Setup
## Start Docker Container
```shell
 $ docker-compose up
```

## Mongo Replica Setup
- Set Priamary and Secondary server.
```shell
 $ docker exec -it {mongo1 container ID} /bin/bash
```
```shell
 > rs.initiate({_id:0, members:[{_id:0, host:"mongo1:27017"}, {_id:1, host:"mongo2:27017"}, {_id:2, host:"mongo3:27017"}]})
```

- Allows read operation on secondary members.
```shell
 $ docker exec -it {mongo2,3 container ID} /bin/bash
```
```shell
 > rs.secondaryOk()
```