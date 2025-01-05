## Chapter 6: Rootless Containers

Rootless containers allow non-root users to run containers, enhancing security by isolating privileges.

### Pulling an Image

```bash
podman pull nginx
```
- Downloads the specified image for container use.

### Creating and Running a Rootless Container

1. **Create a Container**:
   ```bash
   podman create --name mycontainer nginx
   ```
2. **Start the Container**:
   ```bash
   podman start mycontainer
   ```
