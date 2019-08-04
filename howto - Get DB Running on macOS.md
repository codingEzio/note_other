### MySQL
- 

### MongoDB
- ```brew update && brew install mongodb```
- ```sudo mkdir -p /data/db```
- ```sudo chown -R `id -un` /data/db```

### Redis
- ```brew update && brew install redis```
- ```redis-server --port WHATEVER```
- ```redis-cli```

----------

### Config files 
| DB | Location |
|--: | :-------: |
| Redis | ```/usr/local/etc/redis.conf``` |
| MongoDB | ```/usr/local/etc/mongod.conf``` |
|  |  |

### Universal cmds
- ```brew info APP_NAME```