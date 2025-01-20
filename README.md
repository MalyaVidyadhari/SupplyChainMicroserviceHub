**Software required**

**Java version**: openjdk version "21.0.4" 2024-07-16<br/>
**Gradle version**: Gradle 8.11.1<br/>
**Git version**: git version 2.45.1.windows.1<br/>
**MYSQL**<br/>
Run these below queries after MYSQL setup<br/> 
username: root<br/>
password: root<br/>
```
CREATE DATABASE IF NOT EXISTS cmms;

USE cmms;

CREATE TABLE IF NOT EXISTS users (
    user_id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(255) UNIQUE NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    role VARCHAR(50) NOT NULL,
    status VARCHAR(50) DEFAULT 'active',  -- Can be 'active', 'inactive', or 'locked'
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);

select * from users;

INSERT INTO `roles` VALUES (1,'ROLE_ADMIN'),(2,'ROLE_USER');
```

**Step to setup microservice project**

git clone -b master https://github.com/MalyaVidyadhari/eureka-server.git<br/>
git clone -b master https://github.com/MalyaVidyadhari/register-service.git<br/>
git clone -b master https://github.com/MalyaVidyadhari/work-order-management.git<br/>
git clone https://github.com/MalyaVidyadhari/api-gateway.git<br/>

**How to Start Server**

	* Check Gradle Version in Command Prompt >> gradle -version (https://services.gradle.org/distributions/gradle-8.11.1-bin.zip)
	* Unzip & add Java Home & Gradle Home and also edit Path to set Java Home & Gradle Home

**Build Eureka Server**

	* Open Command Prompt for Eureka Server Project
	* gradle clean build
	* cd build
	* cd libs
	* java -jar eureka-server-0.0.1-SNAPSHOT.jar
	http://localhost:8761/

**Build Register Service**

	* Open Command Prompt for Register Service Project
	* gradle clean build
	* cd build
	* cd libs
	* java -jar register-service-0.0.1-SNAPSHOT.jar
	http://localhost:8761/

**Build Work Order Management Service**

	* Open Command Prompt for Work Order Management Project
	* gradle clean build
	* cd build
	* cd libs
	* java -jar work-order-management-0.0.1-SNAPSHOT.jar
	http://localhost:8761/
	
 **Build API Gateway Service**
 
	* Open Command Prompt for API gateway Project
	* gradle clean build
	* cd build
	* cd libs
	* java -jar api-gateway-0.0.1-SNAPSHOT.jar
	http://localhost:8761/
 
 ![image](https://github.com/user-attachments/assets/f1a76041-3c51-49b9-9a80-b16f6b8c7f03)

**UI Steps**

# CMMS

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 18.2.10.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.dev/tools/cli) page.

 

