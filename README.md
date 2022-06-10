# IRIS_Systems_recruitment_Task-6
Now we are going to use docker-compose to open connect databases using single command
## Creating mongo.yaml file
```
version: '3'
services:
  # my-app:
  # image: ${docker-registry}/my-app:1.0
  # ports:
  # - 3000:3000
  mongodb:
    image: mongo
    ports:
      - 27017:27017
    environment:
      - MONGO_INITDB_ROOT_USERNAME=admin
      - MONGO_INITDB_ROOT_PASSWORD=password
      
  mongo-express:
    image: mongo-express
    restart: always # fixes MongoNetworkError when mongodb is not ready when mongo-express starts
    ports:
      - 8081:8081
    environment:
      - ME_CONFIG_MONGODB_ADMINUSERNAME=admin
      - ME_CONFIG_MONGODB_ADMINPASSWORD=password
      - ME_CONFIG_MONGODB_SERVER=mongodb
 docker-compose -f mongo.yaml up
```
Then in command prompt
```
docker-compose -f mongo.yaml up
```

![14](https://user-images.githubusercontent.com/84263946/173130600-be62fbcc-4235-4a25-a9dd-6e3417ce8144.PNG)

we can see tat two containers are started by single command in the image below

![13](https://user-images.githubusercontent.com/84263946/173130731-2e737ddb-f19e-4262-be14-b84adf2781a0.PNG)

