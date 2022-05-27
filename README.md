# Udagram Image Filtering Application

Udagram is a simple cloud application developed alongside the Udacity Cloud Engineering Nanodegree. It allows users to register and log into a web client, post photos to the feed, and process photos using an image filtering microservice.

The project is split into two parts:
1. Frontend - Angular web application built with Ionic Framework
2. Backend RESTful API - Node-Express application

## Getting Started
> _tip_: it's recommended that you start with getting the backend API running since the frontend web application depends on the API.

### Prerequisite
1. The depends on the Node Package Manager (NPM). You will need to download and install Node from [https://nodejs.com/en/download](https://nodejs.org/en/download/). This will allow you to be able to run `npm` commands.
2. Environment variables will need to be set. These environment variables include database connection details that should not be hard-coded into the application code.

#### Environment Script
A file named `set_env.sh` has been prepared as an optional tool to help you configure these variables on your local development environment.
 
We do _not_ want your credentials to be stored in git. After pulling this `starter` project, run the following command to tell git to stop tracking the script in git but keep it stored locally. This way, you can use the script for your convenience and reduce risk of exposing your credentials.
`git rm --cached set_env.sh`

Afterwards, we can prevent the file from being included in your solution by adding the file to our `.gitignore` file.

### 1. Database
Create a PostgreSQL database either locally or on AWS RDS. The database is used to store the application's metadata.

* We will need to use password authentication for this project. This means that a username and password is needed to authenticate and access the database.
* The port number will need to be set as `5432`. This is the typical port that is used by PostgreSQL so it is usually set to this port by default.

Once your database is set up, set the config values for environment variables prefixed with `POSTGRES_` in `set_env.sh`.
* If you set up a local database, your `POSTGRES_HOST` is most likely `localhost`
* If you set up an RDS database, your `POSTGRES_HOST` is most likely in the following format: `***.****.us-west-1.rds.amazonaws.com`. You can find this value in the AWS console's RDS dashboard.


### 2. S3
Create an AWS S3 bucket. The S3 bucket is used to store images that are displayed in Udagram.

Set the config values for environment variables prefixed with `AWS_` in `set_env.sh`.

### 3. Backend API
Launch the backend API locally. The API is the application's interface to S3 and the database.

* To download all the package dependencies, run the command from the directory `udagram-api/`:
    ```bash
    npm install .
    ```
* To run the application locally, run:
    ```bash
    npm run dev
    ```
* You can visit `http://localhost:8080/api/v0/feed` in your web browser to verify that the application is running. You should see a JSON payload. Feel free to play around with Postman to test the API's.

### 4. Frontend App
Launch the frontend app locally.

* To download all the package dependencies, run the command from the directory `udagram-frontend/`:
    ```bash
    npm install .
    ```
* Install Ionic Framework's Command Line tools for us to build and run the application:
    ```bash
    npm install -g ionic
    ```
* Prepare your application by compiling them into static files.
    ```bash
    ionic build
    ```
* Run the application locally using files created from the `ionic build` command.
    ```bash
    ionic serve
    ```
* You can visit `http://localhost:8100` in your web browser to verify that the application is running. You should see a web interface.

## Tips
1. Take a look at `udagram-api` -- does it look like we can divide it into two modules to be deployed as separate microservices?
2. The `.dockerignore` file is included for your convenience to not copy `node_modules`. Copying this over into a Docker container might cause issues if your local environment is a different operating system than the Docker image (ex. Windows or MacOS vs. Linux).
3. It's useful to "lint" your code so that changes in the codebase adhere to a coding standard. This helps alleviate issues when developers use different styles of coding. `eslint` has been set up for TypeScript in the codebase for you. To lint your code, run the following:
    ```bash
    npx eslint --ext .js,.ts src/
    ```
    To have your code fixed automatically, run
    ```bash
    npx eslint --ext .js,.ts src/ --fix
    ```
4. `set_env.sh` is really for your backend application. Frontend applications have a different notion of how to store configurations. Configurations for the application endpoints can be configured inside of the `environments/environment.*ts` files.
5. In `set_env.sh`, environment variables are set with `export $VAR=value`. Setting it this way is not permanent; every time you open a new terminal, you will have to run `set_env.sh` to reconfigure your environment variables. To verify if your environment variable is set, you can check the variable with a command like `echo $POSTGRES_USERNAME`.














![build-succeed](https://user-images.githubusercontent.com/22004327/170793145-1e2a3bc0-fefe-4669-999d-b8fa151890ff.png)![deployments](https://user-images.githubusercontent.com/22004327/170793151-5db6ffef-b826-4236-8b4c-cd19176db652.png)
![final](https://user-images.githubusercontent.com/22004327/170793160-2705f84c-cf32-4950-bd7e-fd0b6e84e4ce.png)
![frontend-v6](https://user-images.githubusercontent.com/22004327/170793163-296c01bb-39b3-4ae7-b407-52bf856b21da.png)
![gitlab-build](https://user-images.githubusercontent.com/22004327/170793167-85258a12-326e-4df8-bd80-b82dd33be0a8.png)
![images-up](https://user-images.githubusercontent.com/22004327/170793176-88b48fef-e7c7-49e2-adcf-104edb172a42.png)
![kubernetes](https://user-images.githubusercontent.com/22004327/170793192-74c51705-3832-4d5e-8a9e-84fd89d40261.png)
![logs](https://user-images.githubusercontent.com/22004327/170793216-65f84f71-c0c2-41da-a540-754834e116e8.png)
![logs-running](https://user-images.githubusercontent.com/22004327/170793225-d364982e-cbe4-4bf8-824d-7dd464bac6b3.png)
![services](https://user-images.githubusercontent.com/22004327/170793240-7b391f4f-d9d2-4d56-9c91-3a3bf6975b02.png)
![together](https://user-images.githubusercontent.com/22004327/170793247-c94b48f9-fe95-438e-a47f-cf6113e1fc82.png)
![v6](https://user-images.githubusercontent.com/22004327/170793256-89f8209c-9f87-433b-96d9-601d26bd98be.png)
![working](https://user-images.githubusercontent.com/22004327/170793260-409e1b1a-054e-47bf-b98b-5915d1844412.png)


