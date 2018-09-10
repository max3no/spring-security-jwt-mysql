# Spring boot(Maven) - Spring Security(Annotations) - JWT/MySql(Authorization,Authentication)

## Getting Started

Need jdk, spring boot, working machine.

### Prerequisites

Install Spring Boot.
Configure your java in environmental variables.

### What is it?

 Spring boot project with, spring security.
 Signin and Signup API's with proper authentication and authorization
 Return a JWT token
 
 This project uses Bcrypt to encrypt the passwords.
 
### Setup
	* change the application.properties file with your database, id and pwd.
	* choose your own jwt-secret key
	* Insert following roles in dB 
	
```
INSERT INTO roles(name) VALUES('ROLE_USER');
INSERT INTO roles(name) VALUES('ROLE_ADMIN');
```
	
### Maven dependencies used
	* spring-boot-starter-data-jpa
	* spring-boot-starter-security
	* spring-boot-starter-web
	* mysql-connector-java
	* jjwt

### API Endpoints

SignUP - POST

```
http://localhost:5000/api/auth/signup

{
	"name": "Vaibhav",
	"username" : "vai",
	"email": "vaibhav@gmail.com",
	"password": "somepassword"
}

```

SignIn - POST

```
http://localhost:5000/api/auth/signin

{
	"usernameOrEmail" : "vai",
	"password" : "somepassword"
}

```

# use the token you get in signin as the header in the format
key-value
Authorization  Bearer eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIyIiwiaWF0IjoxNTM2MzE0MTI2LCJleHAiOjE1MzY5MTg5MjZ9.mrePFzltTzXvzD3Jbbsk4JAegxT3g66Tu80ntmt1shBRDRdijRlxEjG6qqYAVTmSN_ADZJMc8ghmGyrmsxioag

![Reference image](https://cdn1.imggmi.com/uploads/2018/9/7/087a1e50645445402ff0ee0dcc1654f3-full.jpg)

GET for role-user

```
http://localhost:5000/api/user
```

GET for role-admin

```
http://localhost:5000/api/admin
```

Currently setting role user as default.
change the role in dB of a user to admin to quick check the API

## Acknowledgments

* Open Source community

