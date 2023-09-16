# Kaiburr Task 1: Java REST API Example

This README provides a step-by-step guide on how to create a Java REST API with endpoints for searching, creating, updating, and deleting "server" objects. This project demonstrates the use of Spring Boot and MongoDB to build a RESTful API.


## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Project Setup](#project-setup)
3. [Database Configuration](#database-configuration)
4. [Project Structure](#project-structure)
5. [Implementation Details](#implementation-details)
   - [Create a Server (POST Request)](#create-a-server-post-request)
   - [Get Servers (GET Request)](#get-servers-get-request)
   - [Get Server by ID (GET Request)](#get-server-by-id-get-request)
   - [Update Server by ID (PUT Request)](#update-server-by-id-put-request)
   - [Delete Server by ID (DELETE Request)](#delete-server-by-id-delete-request)
   - [Find Servers by Name (GET Request)](#find-servers-by-name-get-request)
6. [Testing with Postman](#testing-with-postman)
   - [Create Server Request](#create-server-request)
   - [Get Servers Request](#get-servers-request)
   - [Get Server by ID Request](#get-server-by-id-request)
   - [Update Server by ID Request](#update-server-by-id-request)
   - [Delete Server by ID Request](#delete-server-by-id-request)
   - [Find Servers by Name Request](#find-servers-by-name-request)

## Prerequisites
- Java Development Kit (JDK)
- Maven
- Spring Boot
- MongoDB
- Postman (for testing)
## Project Setup
1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/your-username/your-repository.git

2. Open the project in your preferred IDE.

3. Ensure that you have MongoDB installed and running locally.
## Database Configuration
In the 'application.properties' file, configure your MongoDB database settings:

        spring.data.mongodb.host=localhost
        spring.data.mongodb.port=27017
        spring.data.mongodb.database=task1

## Project Structure
### Directory Structure

The project follows a well-organized directory structure to keep the codebase clean and maintainable. Below is an overview of the main components and directories:

- `src/`: This directory contains the source code and resources for the project.
  - `main/`: The main application code.
    - `java/`: All Java source files are located here.
    - `resources/`: This directory holds resource files, such as configuration files.
  - `test/`: Contains test code to ensure the reliability of the application.
    - `java/`: Test source files are organized here.
    - `resources/`: You can find test-related resource files in this directory.
- `target/`: This directory stores compiled bytecode and built artifacts.
- `.gitignore`: The Gitignore file specifies which files and directories should be excluded from version control.
- `pom.xml`: The Project Object Model (POM) file, which is used for Maven configuration.
- `README.md`: This README file, where you're currently reading project documentation.

### Package Structure

The Java code is organized into the following packages:

- `com.kaiburr.task1.controller`: Contains REST controller classes responsible for handling HTTP requests and responses.
- `com.kaiburr.task1.model`: Defines data model classes that represent entities in the application.
- `com.kaiburr.task1.repository`: Provides data access and persistence logic using MongoDB.
- `com.kaiburr.task1.config`: Contains configuration classes for the application, including MongoDB setup.

### Resource Files

Resource files and configuration files are typically located in the `src/main/resources/` directory. Key configuration files, such as `application.properties`, are found here.

### Test Code

Test classes and resources can be found under the `src/test/` directory. These tests ensure the correctness and reliability of the application's functionality.

This structured organization simplifies code management and makes it easier for developers to work on different aspects of the project. It also encourages best practices for separation of concerns and maintainability.

## Implementation Details

1. Create a Server (POST Request):

To create a new server, send a POST request to the /api/servers endpoint. The request body should be in JSON format and include the following attributes:

- id (String): The unique ID for the server.
- name (String): The name of the server.
- language (String): The programming language used on the server.
- framework (String): The framework used on the server.

Example JSON request body:
    
    {
    "id": "123",
    "name": "Test Server",
    "language": "Java",
    "framework": "Spring Boot"
    }

2. Get Servers (GET Request):

To retrieve a list of all servers, send a GET request to the /api/servers endpoint. If no parameters are provided, this endpoint will return a list of all servers stored in the database.

3. Get Server by ID (GET Request):

To retrieve a specific server by its ID, send a GET request to the /api/servers/{id} endpoint, where {id} should be replaced with the server's unique ID. If the server with the specified ID exists, it will be returned; otherwise, a "404 Not Found" response will be returned.

4. Update Server by ID (PUT Request):

To update an existing server by its ID, send a PUT request to the /api/servers/{id} endpoint, where {id} should be replaced with the server's unique ID. The request body should contain the updated server information in JSON format. If the server with the specified ID exists, it will be updated with the provided data; otherwise, a "404 Not Found" response will be returned.

5. Delete Server by ID (DELETE Request):

To delete a server by its ID, send a DELETE request to the /api/servers/{id} endpoint, where {id} should be replaced with the server's unique ID. If the server with the specified ID exists, it will be deleted from the database; otherwise, a "404 Not Found" response will be returned.

6. Find Servers by Name (GET Request)
To search for servers by name, send a GET request to the /api/servers/findByName endpoint with the name query parameter. The server controller will search for servers whose names contain the provided string. If one or more servers are found, they will be returned; otherwise, a "404 Not Found" response will be returned.

These endpoints collectively provide the basic CRUD (Create, Read, Update, Delete) operations for managing server objects in the MongoDB database.

You can customize and extend these endpoints to fit your specific requirements and business logic.
## Testing With Postman
#### Create Server Request
![App Screenshot](https://drive.google.com/uc?id=1bE8S9W42CYVpaFQoOw_9fsbDWQStdpZo)

![App Screenshot](https://drive.google.com/uc?id=1Pu8KtAwXMVNzRQ6rO-XoF2T5MFA_yWZ7)

![App Screenshot](https://drive.google.com/uc?id=1GudCLBS_ahl6DZHnJ3-qsykAGD_R7xW1)

#### Get Servers Request
![App Screenshot](https://drive.google.com/uc?id=1-MMiGbgX_oJ8kMif4lk1qc3KYSFb2xrv)

#### Get Server by ID Request
![App Screenshot](https://drive.google.com/uc?id=1gglIfDB0xdSMifmX5mMO3LlY-dyl0MMZ)

#### Update Server by ID Request
![App Screenshot](https://drive.google.com/uc?id=1tjRekwj73LLNGtaxYGwaOm3NUlalD6hZ)

#### Find Servers by Name Request
![App Screenshot](https://drive.google.com/uc?id=1i7RSI9_X0Qx3SJW_KM94oEcMm-oPB5Oi)

#### Delete Server by ID Request
![App Screenshot](https://drive.google.com/uc?id=1ICP7hbSK0FUWtz0-X9ewFsHh7yYyIJid)

![App Screenshot](https://drive.google.com/uc?id=1JwSOGegC66-OAs6sWQb1o3Yb7j-2v-CA)
