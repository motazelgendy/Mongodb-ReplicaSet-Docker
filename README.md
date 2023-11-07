# Mongodb-ReplicaSet-Docker

## Set up Replicaset using Docker Containers

### Create 3 directories 
```
mkdir mongo1 mongo2 mongo3
```


### Create a key File and 

```
touch key
```

#### Genarate Base64 bit key using openssl 
```
openssl rand -base64 756
```

### copy the output to the key file "u can use nano"

### copy key file to each mongos directories then change file permession to readonly to the owner 
```
chmod 400 key
```

### run docker compose to create 3 containers 
```
docker-compose up -d
```

## execute initiate command in monog primary container shell 
### change ip to the public ip 

```
rs.initiate({

 _id: \”rs0\”,

 members: [

   {_id: 0, host: <“ip:port>},

  {_id: 1, host: <“ip:port>},

   {_id: 2, host: <“ip:port>}

 ]

})”
```

