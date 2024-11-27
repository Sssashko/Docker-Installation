
# How To Install Docker On Ubuntu And Windows

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
   Check if Docker is installed and working.
   ```bash
   docker --version
   ```

9. **Run a Test Container**:  
   Test Docker functionality by running a test container.
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

---

## Installation on Windows

## System Requirements
- **OS**: Windows 10 64-bit Pro, Enterprise, or Education (version 1903 or higher), or Windows 11
- **RAM**: Minimum 4 GB
- **Disk Space**: At least 10 GB free 

## Installation Steps

1. **Download Docker Desktop**:  
   - Go to the official [Docker Desktop website](https://www.docker.com/products/docker-desktop).
   - Click **"Download for Windows"**.
   - Save the installer (`Docker Desktop Installer.exe`) to your computer.

2. **Run the Installer**:  
   - Double-click on the downloaded `Docker Desktop Installer.exe`.
   - Select **"Use WSL 2 instead of Hyper-V"** (recommended).
   - Click **"Install"**.

3. **Complete Installation**:  
   - Wait for the installation to finish.
     When prompted, restart your computer.

4. **Set Up Docker Desktop**:  
   - Launch **Docker Desktop** from the Start menu or double click on your desktop shortcut.
   - Ensure **WSL 2** is selected as the backend during setup.

5. **Verify Docker Installation**:  
   - Open **CMD** or **PowerShell**.
   - Check the Docker version:
     ```bash
     docker --version
     ```
   - You should see something like:
     ```
     Docker version XX.XX.X, build XXXXXXX
     ```

6. **Run a Test Container**:  
   Verify that Docker is working correctly by running a test container:
   ```bash
   docker run hello-world

