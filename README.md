
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

1. **Check and Enable Virtualization**:  
   Ensure that virtualization is enabled on your machine.

   - **Check Virtualization**:  
     Open the **Task Manager** (Ctrl + Shift + Esc), go to the **Performance** tab, and confirm that **Virtualization: Enabled** is displayed in the bottom-right corner.

   - **Enable Virtualization in BIOS**:  
     Restart your computer, access BIOS/UEFI settings (commonly by pressing Del, F2, or F10 during startup), locate the virtualization option (e.g., Intel VT-x or AMD-V), enable it, save changes, and reboot.

2. **Download Docker Desktop**:  
   - Go to the official [Docker Desktop website](https://www.docker.com/products/docker-desktop).
   - Click **"Download for Windows"**.
   - Save the installer (`Docker Desktop Installer.exe`) to your computer.

3. **Run the Installer**:  
   - Double-click on the downloaded `Docker Desktop Installer.exe`.
   - Confirm any security prompts (UAC).
   - Select **"Use WSL 2 instead of Hyper-V"** (recommended).
   - Click **"Install"**.

4. **Complete Installation**:  
   - Wait for the installation to finish.
   - If prompted, restart your computer.

5. **Set Up Docker Desktop**:  
   - Launch **Docker Desktop** from the Start menu.
   - Accept the terms of service and complete the setup process.
   - Ensure **WSL 2** is selected as the backend during setup.

6. **Verify Docker Installation**:  
   - Open **Command Prompt** or **PowerShell**.
   - Check the Docker version:
     ```bash
     docker --version
     ```
   - You should see something like:
     ```
     Docker version XX.XX.X, build XXXXXXX
     ```

7. **Run a Test Container**:  
   Verify that Docker is working correctly by running a test container:
   ```bash
   docker run hello-world
