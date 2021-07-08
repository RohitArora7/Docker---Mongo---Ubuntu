# Docker---Mongo---Ubuntu

-------Backup Mongodump 
```bash
docker exec -it tutor_local_mongodb_1 bash

mongodump --out /data_backup/ 
or
mongodump --host localhost --port 27017  --out data_backup

```

------Mongo Basic Commands 
```bash
mongo
show dbs
use eat
db
db.movie.insert({"name":"tutorials point"})
show collections
db.movie.find().pretty()
```

------Delete Database
```bash
docker exec -it tutor_local_mongodb_1 bash
mongo
use eat
db.dropDatabase()
```

--------Restore Mongodump
```bash
mongorestore  /data_backup/ 
```


-- Docker One Line Command 
```bash
docker exec tutor_local_mongodb_1 sh -c 'mongodump --archive' > db.dump
docker exec -i tutor_local_mongodb_1 sh -c 'mongorestore --archive' < db.dump
```
