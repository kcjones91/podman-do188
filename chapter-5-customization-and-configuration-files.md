## Chapter 5: Customization and Configuration Files

Podman offers extensive customization through configuration files for storage, registries, and the engine. These files are located in system-wide (`/etc/containers/`) or user-specific (`~/.config/containers/`) directories.

### 5.1 Storage Configuration
- **File**: `/etc/containers/storage.conf`
- **Customizations**:
  - Change storage location:
    ```ini
    [storage]
    graphroot = "/custom/path/to/storage"
    ```
  - Set storage driver:
    ```ini
    [storage]
    driver = "overlay"
    ```

### 5.2 Registries Configuration
- **File**: `/etc/containers/registries.conf`
- **Customizations**:
  - Define default registries:
    ```yaml
    unqualified-search-registries = ["docker.io", "quay.io"]
    ```
  - Allow insecure registries:
    ```yaml
    [[registry]]
    location = "insecure-registry.com"
    insecure = true
    ```

### 5.3 Engine Configuration
- **File**: `/etc/containers/containers.conf`
- **Customizations**:
  - Set default runtime:
    ```yaml
    [engine]
    runtime = "runc"
    ```
  - Configure cgroup manager:
    ```yaml
    cgroup_manager = "systemd"
    ```

### 5.4 Systemd Service for Pods
- Example systemd service file to start a pod on boot:
  ```ini
  [Unit]
  Description=Podman Pod Service
  After=network.target

  [Service]
  ExecStart=/usr/bin/podman pod start mypod
  ExecStop=/usr/bin/podman pod stop mypod
  Restart=always

  [Install]
  WantedBy=multi-user.target
  ```
  Enable and start the service:
  ```bash
  sudo systemctl enable mypod.service
  sudo systemctl start mypod.service
  ```
