In this project we have created a simple html web app 

To containerize the application follow the below steps:  
#Build the Docker image from docker file :
docker build -t myapp .

#Run a container from the app :
docker run -d -p 8081:80 myapp

Now you can access the application on localhost:8081

#List all running containers :
docker ps

#List all containers :
docker ps -a

#To start,stop & remove containers:
docker start <container name> ,
docker stop <container name> ,
docker rm <container name> ,
docker rm -f <container name>  --to forcefully remove the container

#To inspect running containers and view logs :
docker inspect <container name> ,
docker logs <container name>

Now if you want to run the containers through a docker compose file use the below command.
#Run the containers from docker compose file:
docker compose up -d

Access the ports defined in the file and you will be able to see the desired result.

#To push the images to docker hub
Firstly tag the image with the repo name:
 docker tag <present-repo:tag>  <dockerub repo:tag>

 Now push the tagged image:
 docker push rahulgandhi01/test-repo/:v2

 #To pull the image:
 docker pull rahulgandhi01/test-repo:v2

 Now you can run the image with docker run to run it locally.

--#Bonus Question#--

#Firstly get inside the test folder then run docker compose :
docker compose up -d

#The port 8080 is being used for running the adminer application. Access it from localhost 8080 then login into the application using the credentials provides in the docker file. 
Note: For the server name use the service name from that is mysql

Once you are logged in create a table using the options given. Once the table is created then go inside the mql container through the terminal.

#To get inside the sql container :
docker exec -it mysql-db mysql  -u user -ppassword

#Go to the database exampledb using command :
use exampledb

#Check what all tables are created in this using the below command. The table which we created through the GUI will appear here :
show tables
