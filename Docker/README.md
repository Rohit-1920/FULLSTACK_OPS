# Day-1 : 🐳 Introduction to Containerization and Docker Basics ⚓


## Difference between Monolithic and Microservices

## Monolithic Architecture
- A single, unified application where all components are tightly coupled.
- Difficult to scale individual components.
- Deployment and updates require redeploying the entire application.
- Example: A traditional web application where frontend, backend, and database are all part of the same codebase.

## Microservices Architecture
- Application is broken down into smaller, independent services.
- Each service can be developed, deployed, and scaled independently.
- Enables better fault isolation and easier technology upgrades.
- Example: An e-commerce platform with separate services for user authentication, product catalog, and order management.

---

![Alt text](arch.gif)



# Difference between Traditional, Virtualization, and Containerization Deployment

| Deployment Type     | Description |
|--------------------|-------------|
| **Traditional**    | Directly installs applications on physical servers, leading to inefficient resource utilization. |
| **Virtualization** | Uses a hypervisor to create multiple virtual machines (VMs) on a single physical server. Each VM has its own OS. |
| **Containerization** | Uses container technology to package applications and dependencies together, sharing the host OS for lightweight and efficient deployment. |

---

# Introduction to Containerization 📦 
Containerization is a method of packaging applications and their dependencies together in isolated environments known as containers. It ensures that applications run consistently across different computing environments.

## Key Concepts:
- **Container**: A lightweight, standalone executable package that includes everything needed to run an application.
- **Image**: A template used to create containers. It includes application code, dependencies, and runtime.

---

# Introduction to Docker 🐳 
Docker is a platform for developing, shipping, and running applications in containers. It simplifies application deployment across different environments.

## Why Use Docker?
- Ensures consistent environments across development, testing, and production.
- Reduces infrastructure overhead and resource consumption.
- Improves application scalability and portability.

---

# Difference between Docker CE and Docker EE

| Feature         | Docker CE (Community Edition) | Docker EE (Enterprise Edition) |
|---------------|-----------------------------|-----------------------------|
| **License**   | Open-source and free        | Paid with enterprise support |
| **Security**  | Basic security features     | Advanced security features   |
| **Support**   | Community support           | Professional support from Docker |
| **Management** | Basic container management | Advanced container orchestration and management |

---

# Day-2 : Docker Container Commands

## Introduction
Docker is a containerization platform that allows developers to package applications and dependencies into lightweight, portable containers. This guide covers essential Docker container commands and hands-on experiments to help students understand container management.

---

## Essential Commands for Container Management using Docker

### 1. **Create a Container**
```sh
docker create --name my_container ubuntu
```
Creates a new container from an Ubuntu image but does not start it.

### 2. **Run a Container**
```sh
docker run -it ubuntu
```
Runs a new container interactively with an Ubuntu image.

### 3. **Run a Container in Detached Mode**
```sh
docker run -d --name my_container nginx
```
Starts a container in the background using the Nginx image.

### 4. **Stop a Running Container**
```sh
docker stop my_container
```
Stops the specified container.

### 5. **Start a Stopped Container**
```sh
docker start my_container
```
Starts an existing container.

### 6. **Remove a Container**
```sh
docker rm my_container
```
Removes a stopped container.

### 7. **List All Running Containers**
```sh
docker ps
```
Displays active containers.

### 8. **List All Containers (Running & Stopped)**
```sh
docker ps -a
```
Displays all containers, including stopped ones.



---

## Expose Applications to the World

### 1. **Run a Container and Expose a Port**
```sh
docker run -d -p 8080:80 nginx
```
Maps port `8080` on the host to port `80` inside the container.

### 2. **Run a Container with Environment Variables**
```sh
docker run -d -e "ENV_VAR=value" my_app
```
Passes environment variables to a container.

### 3. **Expose Random Ports Using `-P` Flag**
```sh
docker run -d -P nginx
```
Automatically assigns random ports to the container.

---

## Interacting with Containers using `exec`

### 1. **Execute Commands in a Running Container**
```sh
docker exec -it my_container bash
```
