# SOA

Projet du groupe :
   MINTSANIAINA christhino 
   Safidinimbonanana Basillisse 
   Troy Mario Fabice
   Paul Tony Natacha Quilichini

# How to run

- Navigate to root of the project
```
    cd SOA
```
- Build the project
```
    mvn clean package -DskipTests     
```
![Maven Build](https://github.com/Nasruddin/spring-boot-based-microservices/blob/master/images/build.png?raw=true)

- Locate the docker directory from the root directory and run docker compose to startup the containers
```
    cd docker && docker-compose up --build
```
![Docker Compose Build](https://github.com/Nasruddin/spring-boot-based-microservices/blob/master/images/docker-compose.png?raw=true)

- Check if all our services are running and healthy
```
    docker ps
```
![Docker PS](https://github.com/Nasruddin/spring-boot-based-microservices/blob/master/images/docker-ps.png?raw=true)

- Let's check if all the services are up and running. We will reach to eureka server using gateway. 
Open the browser and hit http://localhost:8443/eureka/web You will need to authenticate yourself before accessing the endpoint.
```
username : user
password : password
```
![Eureka](https://github.com/Nasruddin/spring-boot-based-microservices/blob/master/images/eureka.png?raw=true)

- Now, we have a look at our gateway endpoints configurations as well. Hit http://localhost:8443/actuator/gateway/routes in the browser again and, you should be able to find all the routes configured.
![Gateway Routes](https://github.com/Nasruddin/spring-boot-based-microservices/blob/master/images/gateway-routes.png?raw=true)


- Coming to swagger/openapi specs, here is the address to access them - http://localhost:8443/openapi/swagger-ui.html
![Swagger OpenApi Specs](https://github.com/Nasruddin/spring-boot-based-microservices/blob/master/images/swagger-openapi.png?raw=true)

- Please use the below curl to generate the access token with both read and write scope. 
```
curl -k http://writer:secret-writer@localhost:8443/oauth2/token -d grant_type=client_credentials -d scope="course:read course:write" 
```
![Swagger OpenApi Specs](https://github.com/Nasruddin/spring-boot-based-microservices/blob/master/images/oauth-endpoint.png?raw=true)
![Swagger OpenApi Specs](https://github.com/Nasruddin/spring-boot-based-microservices/blob/master/images/jwt-io.png?raw=true)