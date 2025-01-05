## Chapter 4: Working with Pods in Podman

Pods in Podman mimic Kubernetes pods, allowing multiple containers to share the same network and namespaces. This chapter covers the essential commands and concepts for managing pods.

### Key Commands:

1. **Create a Pod**:
   ```bash
   podman pod create --name mypod --hostname mypodhost
   ```
   - Creates a pod with a custom name and hostname.

2. **Add a Container to a Pod**:
   ```bash
   podman run --pod mypod -d nginx
   ```
   - Runs a container within the specified pod.

3. **Start a Pod**:
   ```bash
   podman pod start mypod
   ```
   - Starts all containers in the pod.

4. **Stop a Pod**:
   ```bash
   podman pod stop mypod
   ```
   - Stops all running containers within the pod.

5. **List Pods**:
   ```bash
   podman pod list
   ```
   - Displays details of all pods.

6. **Remove a Pod**:
   ```bash
   podman pod rm mypod
   ```
   - Deletes a pod and its containers (use `-f` to force).
