
# How To Install Docker On Windows

## Presentation link
https://pikcrvtlv-my.sharepoint.com/:p:/g/personal/11daostrovskis_rvt_lv/EfwhNJxXY1xFnqXd20iT5fABZN0uLKqVqLV3SZphDH8rcA?e=zDey4B

# Docker Installation Guide for Windows

## System Requirements
- **OS**: Windows 10 64-bit Pro, Enterprise, or Education (version 1903 or higher), or Windows 11
- **Virtualization**: Must be enabled in BIOS
- **RAM**: Minimum 4 GB
- **Disk Space**: At least 10 GB free

## Installation Steps

1. **Download Docker Desktop**:  
   - Go to the official [Docker Desktop website](https://www.docker.com/products/docker-desktop).
   - Click **"Download for Windows"**.
   - Save the installer (`Docker Desktop Installer.exe`) to your computer.

2. **Run the Installer**:  
   - Double-click on the downloaded `Docker Desktop Installer.exe`.
   - Click **"Install"**.

3. **Complete Installation**:  
   - Wait for the installation to finish and restart your computer.

4. **Set Up Docker Desktop**:  
   - Launch **Docker Desktop** from the Start menu or desktop

5. **Verify Docker Installation**:  
   - Open **Command Prompt** or **PowerShell**.
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
