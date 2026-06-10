# Java CI/CD Pipeline with Jenkins Shared Library

This project demonstrates a complete CI/CD pipeline for a Java application using Jenkins Declarative Pipeline and a custom Shared Library.

## Overview

The pipeline automates the software delivery process by building, testing, archiving, containerizing, and publishing a Java application Docker image.

## Features

* Automated Maven build and testing
* Artifact archiving
* Docker image creation
* Docker Hub authentication
* Automated Docker image publishing
* Jenkins Shared Library integration
* Secure credentials management using Jenkins Credentials Store

## Technologies Used

* Jenkins
* Jenkins Shared Library
* Java 11
* Maven
* Docker
* Docker Hub
* Git

## Pipeline Stages

### 1. Build Application

Builds the Java application using Maven.

### 2. Test Application

Executes application tests.

### 3. Archive Artifacts

Stores generated JAR files as Jenkins build artifacts.

### 4. Build Docker Image

Creates a Docker image for the application.

### 5. Docker Login

Authenticates securely with Docker Hub using Jenkins credentials.

### 6. Push Docker Image

Publishes the versioned Docker image to Docker Hub.

## Jenkins Configuration

### Agent

* Jenkins Agent: `ahmed-agent-01`

### Tools

* JDK 11
* Maven 3.8.2

### Credentials

* `docker-username`
* `docker-password`

## Outcome

Implemented an automated CI/CD workflow that streamlines Java application delivery, improves deployment consistency, and reduces manual operational tasks.
