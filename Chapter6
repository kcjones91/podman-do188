## Chapter 6: Rootless Containers

Rootless containers allow non-root users to run containers, enhancing security by isolating privileges. This chapter outlines the rootless container lifecycle and configurations.

### 6.1 Pulling an Image
```bash
podman pull nginx
```
- Downloads the specified image for container use.

### 6.2 Creating and Running a Rootless Container
1. **Create a Container**:
   ```bash
   podman create --name mycontainer nginx
   ```
   - Prepares a container without starting it.

2. **Set Up Networking**:
   - Rootless containers use `slirp4netns` for user-mode networking.

3. **Start the Container**:
   ```bash
   podman start mycontainer
   ```
   - Initiates the container with configured settings.

### 6.3 Monitoring and Lifecycle
1. **Container Monitor**:
   - `conmon` handles container runtime monitoring.
2. **Launch OCI Runtime**:
   - Podman uses OCI-compatible runtimes (e.g., `runc`) to execute the container.

3. **Running the Container**:
   - The container runs until completion or termination.

4. **Inspect and Logs**:
   - Inspect container:
     ```bash
     podman inspect mycontainer
     ```
   - View logs:
     ```bash
     podman logs mycontainer
     ```

5. **Stop and Remove Container**:
   ```bash
   podman stop mycontainer
   podman rm mycontainer
   ```
