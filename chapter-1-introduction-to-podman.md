
# Chapter 1: Introduction to Podman

## 1.2 A Brief Overview of Containers

Containers are lightweight, portable, and efficient environments to run applications. They encapsulate an application and its dependencies, ensuring consistency across development, testing, and production.

### 1.2.1 Container Images: A New Way to Ship Software

Container images revolutionize the software distribution process by bundling application code, libraries, and dependencies into a single, portable artifact.

### 1.2.2 Container Images Lead to Microservices

The rise of container images has driven the adoption of microservices architecture, where applications are broken into small, independently deployable services.

### 1.2.3 Container Image Format

Container images adhere to formats like the Open Container Initiative (OCI) standards, ensuring compatibility across platforms.

### 1.2.4 Container Standards

Container standards such as OCI help maintain interoperability between container runtimes and orchestrators.

## 1.3 Why Podman Over Docker

Podman offers several advantages over Docker, making it a compelling choice for running containers.

### 1.3.1 Why Only Have One Way to Run Containers?

Podman provides an alternative to Docker, ensuring diversity and flexibility in container management.

### 1.3.2 Rootless Containers

Podman supports running containers as a non-root user, enhancing security by reducing the risk of privilege escalation.

### 1.3.3 Fork/Exec Model

Podman uses a fork/exec model, which eliminates the need for a central daemon to manage containers.

### 1.3.4 Podman Is Daemonless

Unlike Docker, Podman operates without a background daemon, reducing resource usage and potential points of failure.

### 1.3.5 User-Friendly Command Line

Podman's CLI is designed to be intuitive and compatible with Docker commands, making it easy for developers to transition.

### 1.3.6 Support for REST API

Podman provides a REST API for remote management and integration with automation tools.

### 1.3.7 Integration with Systemd

Podman integrates seamlessly with `systemd`, allowing containers to be managed as system services.

### 1.3.8 Pods

Podman introduces pods, a concept from Kubernetes, to group related containers that share resources.

### 1.3.9 Customizable Registries

Podman allows users to configure and prioritize container registries for pulling images.

### 1.3.10 Multiple Transports

Podman supports multiple transports for container images, including `docker://`, `oci://`, and `dir://`.

### 1.3.11 Complete Customizability

Podman's configuration files enable complete customization of storage, networking, and other settings.

### 1.3.12 User-Namespace Support

Podman leverages user namespaces to provide enhanced isolation and security for containers.

## 1.4 When Not to Use Podman

While Podman is highly versatile, it might not be the best choice in environments heavily reliant on Docker Compose or in scenarios requiring a central daemon for orchestration.

