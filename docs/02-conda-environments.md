## Section 2: Server setup & Anaconda installation
Once Git is configured, prepare the server/compute environment.

### 2.1 Download and execute Anaconda installer
Download the latest 64-bit Linux Anaconda installer:

```bash
# Download installer script
wget [https://repo.anaconda.com/archive/Anaconda3-2025.06-1-Linux-x86_64.sh](https://repo.anaconda.com/archive/Anaconda3-2025.06-1-Linux-x86_64.sh)

# Execute installer in silent or interactive mode
bash Anaconda3-2025.06-1-Linux-x86_64.sh

# Apply updated shell profile path
source ~/.bashrc
```

### 2.2 Verify installation
Ensure both Conda and system Python paths are correctly configured:

```bash
conda --version
python --version
```