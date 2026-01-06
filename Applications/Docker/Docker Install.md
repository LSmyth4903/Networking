# Install Docker on a VM (Proxmox)

This guide walks through setting up a **dedicated Docker virtual machine** on **Proxmox VE** using **Ubuntu Server**, then installing Docker using the official packages.

---

## 1. 🖥️ Create the Ubuntu Server VM

Create a new virtual machine in the Proxmox web interface. The settings below are chosen for performance and compatibility with Linux.

### VM Requirements

* **Name:** `docker-host`
* **ISO:** Ubuntu Server ISO
* **Firmware:** OVMF (UEFI)
* **Machine type:** q35
* **Disk:** 30–50 GB, VirtIO Block
* **CPU:** 2–4 cores, type `host`
* **Memory:** 4 GB minimum (8 GB recommended)
* **Network:** VirtIO (paravirtualized) on bridge `vmbr1`

Create the VM with these settings, then start it.

---

## 2. 📀 Install Ubuntu Server

Follow the Ubuntu Server installer using mostly default options.

**Installer choices:**

* Network: DHCP
* Storage: Use entire disk
* User: Create a normal user account (do not use root)
* Enable OpenSSH server
* Do not install Docker during setup

Once installation finishes, reboot and log in via the console or SSH.

---

## 3. 🛠️ Prepare the System

First, update the system and install packages needed to securely add external repositories.

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y ca-certificates curl gnupg lsb-release
```

Keeping the system updated reduces bugs and avoids issues later when installing Docker.

### Install QEMU Guest Agent (recommended)

The guest agent lets Proxmox:

* Display the VM’s IP address
* Perform clean shutdowns and reboots

```bash
sudo apt install -y qemu-guest-agent
sudo systemctl enable --now qemu-guest-agent
```

---

## 4. 🐳 Install Docker Engine

Docker is installed from Docker’s official repository to ensure you get a current, supported version.

### Add Docker’s GPG key

This allows Ubuntu to verify Docker packages.

```bash
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

### Add the Docker repository

This tells Ubuntu where to download Docker packages from.

```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### Install Docker

```bash
sudo apt update
sudo apt install -y docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

At this point, Docker is installed and running, but only accessible with `sudo`.

---

## 5. 👤 Allow Your User to Run Docker

Add your user to the Docker group so Docker commands can be run without `sudo`.

```bash
sudo usermod -aG docker $USER
newgrp docker
```

Verify the installation:

```bash
docker run hello-world
```

If this runs successfully, Docker is working correctly.

---

## 6. 🔁 Enable Docker at Boot

Ensure Docker starts automatically whenever the VM boots.

```bash
sudo systemctl enable docker
sudo systemctl status docker
```

---

## 7. 🌐 Networking Notes (Optional)

If this VM will host multiple services, it helps to keep its IP address consistent.

Common approaches:

* Reserve the VM’s IP address in pfSense or your router’s DHCP settings
* Configure a static IP using Netplan inside Ubuntu

This prevents service URLs from changing.

---

## 8. 📁 Basic Container Directory Layout (Optional)

Creating a simple directory structure keeps container data organised and easy to back up.

```bash
mkdir -p ~/docker/{data,configs}
```

These folders can be mounted into containers when using Docker Compose.

---

## 9. ✅ Test With a Simple Container

Run a basic Nginx container to confirm networking and port forwarding work.

```bash
docker run -d \
  --name nginx-test \
  -p 8080:80 \
  nginx
```

From another machine on the network, open:

```
http://<VM-IP>:8080
```

You should see the Nginx welcome page.

---
