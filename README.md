Overview

This repository contains the source code for a microservices-based currency conversion application. The project demonstrates the use of various microservices concepts, including Spring Cloud, Spring Boot, Eureka Server, Spring Cloud Config Server, API Gateway, and RestTemplate/FeignClient for service communication.

Features
	•	Currency Conversion Service: Converts an amount between two currencies.
	•	Currency Exchange Service: Provides exchange rates between currencies.
	•	Limits Microservice: Provides dynamic limits configuration.
	•	API Gateway: Centralized API routing and filtering.
	•	Naming Server: Service discovery using Eureka.
	•	Spring Cloud Config Server: Centralized externalized configuration for microservices.

Table of Contents
	•	Project Structure
	•	Prerequisites
	•	How to Run
	•	Microservices Details
	•	API Gateway
	•	Currency Conversion Service
	•	Currency Exchange Service
	•	Limits Microservice
	•	Naming Server
	•	Spring Cloud Config Server
	•	Configuration
	•	Endpoints
	•	License

Project Structure

siddharth-upadhyayula-currency-conversion-microservices/
├── api-gateway/                  # API Gateway for centralized routing and filtering
├── currency-conversion-service/  # Service to perform currency conversion
├── currency-exchange-service/    # Service to provide exchange rates
├── limits-microservice/          # Microservice to provide dynamic configuration limits
├── naming-server/                # Eureka Naming Server for service discovery
├── spring-cloud-config-server/   # Config Server for centralized externalized configuration
├── git-localconfig-repo/         # Configuration files for Spring Cloud Config Server
├── README.md                     # Project documentation
├── LICENSE                       # License information

Prerequisites

Ensure the following tools are installed:
	1.	Java 17 or higher.
	2.	Maven 3.8+
	3.	Postman or a similar API testing tool.
	4.	MySQL (for the Currency Exchange Service database).
	5.	Docker (optional, for containerization).

How to Run

Step 1: Clone the Repository
```
git clone https://github.com/siddharth-upadhyayula/currency-conversion-microservices.git
cd siddharth-upadhyayula-currency-conversion-microservices
```
Step 2: Build the Microservices

Navigate to each microservice directory and build using Maven:
```
mvn clean install
```
Step 3: Start Services

Run each microservice from its root directory using:
```
mvn spring-boot:run
```
Step 4: Verify Services
	•	Access the Eureka Dashboard at http://localhost:8761/
	•	Test individual microservices using Postman or a web browser.

Microservices Details

API Gateway
	•	Path: api-gateway/
	•	Description: Acts as a single entry point to route and filter requests to other microservices.
	•	Port: 8765

Currency Conversion Service
	•	Path: currency-conversion-service/
	•	Description: Converts an amount from one currency to another.
	•	Port: 8100

Currency Exchange Service
	•	Path: currency-exchange-service/
	•	Description: Provides exchange rates for different currencies.
	•	Port: 8000
	•	Database: MySQL (data.sql initializes the database with sample data).

Limits Microservice
	•	Path: limits-microservice/
	•	Description: Provides minimum and maximum limits for application configurations.
	•	Port: 8080

Naming Server
	•	Path: naming-server/
	•	Description: Eureka server for service discovery.
	•	Port: 8761

Spring Cloud Config Server
	•	Path: spring-cloud-config-server/
	•	Description: Centralized configuration management.
	•	Port: 8888
	•	Configuration Repository: git-localconfig-repo/

Configuration

Currency Exchange Database
	1.	Create a database named currency_exchange.
	2.	Execute the SQL script in currency-exchange-service/src/main/resources/data.sql to populate the database.

Config Server
	•	Update the application.properties in spring-cloud-config-server/ to point to the local configuration repository.

Endpoints

API Gateway
	•	http://localhost:8765/{microservice-name}/{endpoint}

Currency Conversion Service
	•	Convert Currency: GET /currency-conversion/from/{from}/to/{to}/quantity/{quantity}

Currency Exchange Service
	•	Retrieve Exchange Rate: GET /currency-exchange/from/{from}/to/{to}

Limits Microservice
	•	Retrieve Limits: GET /limits

Eureka Dashboard
	•	http://localhost:8761/

Config Server
	•	http://localhost:8888/{application-name}/{profile}

