
# How To Install Docker On Ubuntu

## System Requirements
- **OS**: Linux (Ubuntu 20.04+), Windows 10/11, macOS 10.15+
- **RAM**: Minimum 2 GB
- **Disk Space**: At least 2 GB free

## Installation on Ubuntu

1. **Update Packages**:  
   Ensure that all installed packages on your system are up to date.
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```

2. **Remove Old Docker Versions (if necessary)**:  
   If old versions of Docker are installed, remove them.
   ```bash
   sudo apt remove docker docker-engine docker.io containerd runc
   ```

3. **Install Required Dependencies**:  
   Install the necessary packages.
   ```bash
   sudo apt install -y ca-certificates curl gnupg lsb-release
   ```

4. **Add Docker GPG Key**:  
   Add the official GPG key for the Docker repository.
   ```bash
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
   ```

5. **Add Docker Repository**:  
   Add Docker to the APT sources.
   ```bash
   echo \
     "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
     $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   ```

6. **Update Package List**:  
   Update the package list to include the new repository.
   ```bash
   sudo apt update
   ```

7. **Install Docker Engine**:  
   Install the latest stable version of Docker and additional utilities.
   ```bash
   sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
   ```

8. **Verify Docker Installation**:  
   Check the Docker version.
   ```bash
   docker --version
   ```

9. **Run a Test Container**:  
   Verify that Docker is working correctly by running a test container.
   ```bash
   sudo docker run hello-world
   ```

10. **Add User to Docker Group (Optional)**:  
    To use Docker without `sudo`, add the current user to the Docker group.
    ```bash
    sudo usermod -aG docker $USER
    ```

    Restart the terminal or run:
    ```bash
    newgrp docker
    ```

11. **Verify Docker Without sudo**:  
    Confirm that Docker commands work without `sudo`.
    ```bash
    docker run hello-world
    ```
