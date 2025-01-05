# Chapter 2: Command Line Operations

## 2.1 Working with Containers

### 2.1.1 Exploring Containers

Use Podman to explore the properties and details of containers in your environment.

### 2.1.2 Running the Containerized Application

Run applications in a container using the following command:
```bash
podman run -d --name myapp nginx
```

### 2.1.3 Stopping Containers

Stop a running container using:
```bash
podman stop myapp
```

### 2.1.4 Starting Containers

Start a stopped container using:
```bash
podman start myapp
```

### 2.1.5 Listing Containers

List all containers, including running and stopped ones:
```bash
podman ps -a
```

### 2.1.6 Inspecting Containers

Inspect detailed properties of a container:
```bash
podman inspect myapp
```

### 2.1.7 Removing Containers

Remove a container using:
```bash
podman rm myapp
```

### 2.1.8 Exec-ing into a Container

Access a running container interactively:
```bash
podman exec -it myapp /bin/bash
```

### 2.1.9 Creating an Image from a Container

Save the state of a container as an image:
```bash
podman commit myapp myapp_image
```
Example 1: Save a basic container as an image.
Example 2: Save with specific metadata or instructions.

## 2.2 Working with Container Images

### 2.2.1 Differences Between a Container and an Image

- **Container**: A running instance of an image.
- **Image**: A template used to create containers.

### 2.2.2 Listing Images

List all available images:
```bash
podman images
```

### 2.2.3 Inspecting Images

View details about an image:
```bash
podman inspect myapp_image
```

### 2.2.4 Pushing Images

Push an image to a remote registry:
```bash
podman push myapp_image docker://myregistry/myapp_image
```

### 2.2.5 Podman Login

Log into a container registry:
```bash
podman login docker.io
```

### 2.2.6 Tagging Images

Tag an image for pushing to a registry:
```bash
podman tag myapp_image myregistry/myapp_image:v1
```

### 2.2.7 Removing Images

Remove a container image:
```bash
podman rmi myapp_image
```

### 2.2.8 Pulling Images

Download an image from a registry:
```bash
podman pull nginx
```

### 2.2.9 Searching for Images

Search for images on a registry:
```bash
podman search nginx
```

### 2.2.10 Mounting Images

Mount a container image to access its contents:
```bash
podman mount myapp_image
```

## 2.3 Building Images

### 2.3.1 Format of a Containerfile and Dockerfile

#### Containerfile Example
A `Containerfile` is the Podman equivalent of a `Dockerfile`. Here's an example:

```Dockerfile
# Containerfile
FROM ubuntu:20.04

LABEL maintainer="youremail@example.com"

# Update and install necessary packages
RUN apt-get update && apt-get install -y     python3     python3-pip     && rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /app

# Copy application code
COPY . /app

# Install dependencies
RUN pip3 install -r requirements.txt

# Expose the application port
EXPOSE 8080

# Command to run the application
CMD ["python3", "app.py"]
```

#### Dockerfile Example
A `Dockerfile` is used similarly to a `Containerfile` and can be used interchangeably:

```Dockerfile
# Dockerfile
FROM nginx:latest

LABEL maintainer="admin@example.com"

# Copy custom configuration
COPY nginx.conf /etc/nginx/nginx.conf

# Set up content directory
WORKDIR /usr/share/nginx/html

# Copy website content
COPY . /usr/share/nginx/html

# Expose port 80
EXPOSE 80

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
```

These examples illustrate how to define a base image, add application-specific dependencies, set up working directories, and define commands to execute when the container starts.

### 2.3.2 Automating the Building for Our Application

Demonstrate building an image using a `Containerfile` or `Dockerfile`:
```bash
podman build -t myapp_image .
