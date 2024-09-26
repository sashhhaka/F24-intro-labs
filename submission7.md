# Virtualization Lab

## Task 1: VM Deployment

### 1. Virtual Box version: 7.1.0

### 2. Deploying a VM
**Name of the VM**: virtual_kwa
- Installation of Ubuntu 20.04.1 LTS from pre-downloaded ISO file.
![img.png](data/7_img.png)


**VM settings:**
- RAM: 8192 MB
- CPU: 6 cores

![img_1.png](data/7_img_1.png)

**Virtual Disk Space:**
- Choosed to add a new virtual hard disk 
- Disk size: 3 GB
![img_2.png](data/7_img_2.png)

**Result:**
![img_3.png](data/7_img_3.png)

- **VM running:**

![img_6.png](data/7_img_6.png)


## Task 2: System Information Tools

### 1. Processor, RAM, and Network Information
**CPU:**
- Tool: lscpu
- Command: `lscpu`
- Output:
![img_4.png](data/7_img_4.png)
![img_5.png](data/7_img_5.png)
**RAM:**
- Tool: free
- Command: `free -h`
- Output:
![img_7.png](data/7_img_7.png)

**Network:**
- Tool: ip
- Command: `ip addr`
- Output:
![img_8.png](data/7_img_8.png)

### 2. Operating System Specifications
**OS:**
- Tool: lsb_release
- Command: `lsb_release -a`
- Output:

![img_9.png](data/7_img_9.png)