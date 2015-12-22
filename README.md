# dockerMongo
Having fun with MongoDB and Docker

```
docker run --name mongo \
  -p 27017:27017 \
  --volume=$HOME/mongo/data:/data \
  -e MONGODB_PASS=${MONGO_PASSWD} \
  -d herrhelms/mongo:latest
```

###setting up db access
```
db.createUser({user: ${MONGO_USER}, pwd: ${MONGO_PASSWD}, roles: [{ role: "readWrite", db: ${MONGO_DB} }]})
```

**don't forget** (before starting your meteorjs app later on...)

```
MONGO_URL="mongodb://USER:PASSWORD@SERVER:27017/DB" meteor
```
