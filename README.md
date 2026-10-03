# CST8915 Lab 2

**Student Name:** Samuel Vachon  
**Student ID:** 041101891  
**Course:** CST8915 Full-stack Cloud-native Development  
**Semester:** Fall 2026  

## Demo Video

[Watch the Lab 2 Demo Video](https://youtu.be/NoYE1qdRluQ)

## Service Repositories

- [Order Service](https://github.com/SamVachon/CST8915-Lab2-Order-Service)
- [Product Service](https://github.com/SamVachon/CST8915-Lab2-Product-Service)
- [Store Front](https://github.com/SamVachon/CST8915-Lab2-Store-Front)

## Reflection Questions

### 1. What changes did you make to the order-service and product-service to comply with the Configurations and Backing Services factors of the 12-Factor App methodology?

For the order-service, I moved the RabbitMQ connection string and port number out of the code and into environment variables stored in a `.env` file. The order-service was also changed to connect to RabbitMQ running on a separate Azure VM instead of using a local RabbitMQ instance. For the product-service, I moved the port number into an environment variable and added the dotenv dependency so the service could read the value from the `.env` file. These changes make the services easier to configure without changing their source code.

### 2. Why is it important to use environment variables instead of hard-coding configurations in your application?

Environment variables make an application easier and safer to configure because values can be changed without modifying the source code. This is useful when moving an application between different environments because things such as IP addresses, ports, and connection strings may be different. It also helps keep sensitive information such as passwords out of the source code and GitHub repository.

### 3. Why is it important to have separate repositories for each microservice? How does this help maintain independence and scalability of each service?

Having a separate repository for each microservice allows each service to be developed, updated, and deployed independently. A change to one service does not require the entire application to be changed or redeployed. This also helps scalability because individual services can be updated or given more resources based on their own needs without affecting the other services.
