# Node.js CI/CD Project

A simple Node.js web application that demonstrates a modern DevOps workflow using Docker for containerization and GitHub Actions for a fully automated CI/CD pipeline.

## Overview

This project serves as a hands-on example of a containerized application with a continuous integration and continuous deployment (CI/CD) pipeline. The workflow is entirely defined as code, ensuring it is repeatable, auditable, and version-controlled.

The pipeline automates the following steps:

1.  A developer pushes code to the `main` branch of this GitHub repository.
2.  A GitHub Actions workflow is automatically triggered.
3.  The workflow builds a Docker image of the application.
4.  The built image is pushed to a Docker Hub container registry.
5.  (Optional future step) The application can then be deployed to a production environment.

This process ensures that every change is automatically built and tested, which is a core practice of DevOps.

## Technologies Used

* **Node.js**: A JavaScript runtime for building the application.
* **Express**: A minimal and flexible Node.js web application framework.
* **Docker**: Used to containerize the application, providing consistency across development and production environments.
* **GitHub Actions**: A powerful automation platform for building CI/CD pipelines as code.
* **Docker Hub**: A cloud-based registry service for storing public and private Docker images.

## Getting Started

### Prerequisites

* Node.js and npm
* Docker
* Git

### Local Development

1.  Clone the repository to your local machine:
    `git clone https://github.com/wilson7777777/node.js-project.git`
    `cd node.js-project`

2.  Install the Node.js dependencies:
    `npm install`

3.  Build and run the Docker container:
    `docker build -t my-node-app .`
    `docker run -p 3000:3000 my-node-app`

The application will be available at `http://localhost:3000`.

## CI/CD Pipeline Configuration

The CI/CD pipeline is defined in the `.github/workflows/ci-cd.yml` file. It connects to Docker Hub using repository secrets to build and push the Docker image.

* `DOCKER_USERNAME`: Your Docker Hub username.
* `DOCKER_PASSWORD`: Your Docker Hub Access Token (generated in Docker Hub's Security settings).

These secrets are configured in the repository's settings to securely handle credentials.
