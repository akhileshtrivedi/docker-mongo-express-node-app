## demo app - developing with Docker

#### To start the application

Step 1: Now you can see docker network
    docker network ls
    
Step 2: Now you can create docker network
    docker network create mongo-network
    
Step 3: start mongodb 

    docker run -d -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password --name mongodb --net mongo-network mongo    

Step 4: start mongo-express
    
    docker run -d -p 8080:8080 -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin -e ME_CONFIG_MONGODB_ADMINPASSWORD=password --net mongo-network --name mongo-express -e ME_CONFIG_MONGODB_SERVER=mongodb mongo-express   

Step 5: Go mongo-express from browser

    http://localhost:8080



Step 6: Start your nodejs application locally - go to `app` directory of project 

    npm install 
    node app.js
    
Step 7: Access you application UI from browser and you will be able to edit profile 

    http://localhost:3000

