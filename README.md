# Noter Application Arbaz Gazge

The Noter application is a simple Express REST application designed for managing notes. It allows users to perform basic CRUD (Create, Read, Update, Delete) operations on notes through a user-friendly interface.

## Table of Contents

- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Dockerization](#dockerization)
  - [Dockerizing the Noter Application](#dockerizing-the-noter-application)
  - [Running the Dockerized Noter Application](#running-the-dockerized-noter-application)
- [Noter Version 2](#noter-version-2)
  - [Updates and New Features](#updates-and-new-features)
- [Using Docker Compose](#using-docker-compose)
  - [Creating a Docker Compose File](#creating-a-docker-compose-file)
  - [Running the Application with Docker Compose](#running-the-application-with-docker-compose)
- [Contributing](#contributing)


## Getting Started

### Prerequisites

Before you begin, ensure you have the following installed on your machine:

- [Node.js](https://nodejs.org/) (at least version 14)
- [npm](https://www.npmjs.com/) (Node.js package manager)

### Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/your-username/noter-app.git
    ```

2. Change into the project directory:

    ```bash
    cd noter-app
    ```

3. Install dependencies:

    ```bash
    npm install
    ```

4. Start the application:

    ```bash
    npm start
    ```

The Noter application should now be running locally at http://localhost:3000.

## Dockerization

### Dockerizing the Noter Application

The Noter application has been dockerized for easier deployment. To build the Docker image, follow these steps:

1. Create a Dockerfile in the project root with the following content:

    ```Dockerfile
    # Use an official Node runtime as a base image
    FROM node:14

    # Set the working directory in the container
    WORKDIR /usr/src/app

    # Copy package.json and package-lock.json to the container
    COPY package*.json ./

    # Install app dependencies
    RUN npm install

    # Copy the application code to the container
    COPY . .

    # Expose the port that the app will run on
    EXPOSE 3000

    # Define the command to run your application
    CMD ["node", "app.js"]
    ```

2. Build and tag the Docker image:

    ```bash
    docker build -t your-dockerhub-username/noter .
    ```

### Running the Dockerized Noter Application

To run the Dockerized Noter application locally, use the following commands:

```bash
   docker run -p 3000:3000 -d your-dockerhub-username/noter:latest
```

Access the application at [http://localhost:3000](http://localhost:3000).

## Noter Version 2
### Updates and New Features

A new version of the Noter application, Version 2, has been introduced with additional features. In this version, a README file has been added to the root folder with the following content:

```vbnet
   THIS IS NOTER VERSION 2

   THIS IS JUST A README FILE
```
## Using Docker Compose
### Creating a Docker Compose File

Create a file named `docker-compose.yml` in the project root with the following content:

```yaml

  version: '3'
  services:
    noter:
      image: your-dockerhub-username/noter:v2
      ports:
        - "3000:3000"
```

### Running the Application with Docker Compose

To run the Noter application using Docker Compose, execute the following command:

```bash
   docker-compose up -d
```

#### Access the application at [http://localhost:3000](http://localhost:3000).

### Contributing

If you'd like to contribute to the development of the Noter application, please follow our [Contribution Guidelines](CONTRIBUTING.md).
