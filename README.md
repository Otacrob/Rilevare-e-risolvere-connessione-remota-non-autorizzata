# 🛡️ Snort 3.7.2.0 - Manual Build & Installation (Kali Linux)

This repository documents the complete manual installation of **Snort 3.7.2.0** on **Kali Linux**, including **DAQ 3.0.19**, **PCAP support**, and **snort3_extra modules**.

The process was performed entirely from source to ensure full understanding of dependency management, module linkage, and Snort's modular architecture.

---

## ✅ System Requirements

- OS: Kali Linux (Debian-based)
- Kernel: 6.x+
- User: root or user with `sudo` privileges

---

## 📦 Dependencies

Install the full set of required libraries and tools:

```bash
sudo apt update && sudo apt install -y \
  build-essential cmake make g++ bison flex zlib1g-dev \
  libpcap-dev libpcre2-dev libdumbnet-dev libluajit-5.1-dev \
  libhwloc-dev libssl-dev libnghttp2-dev liblzma-dev \
  uuid-dev libffi-dev libmnl-dev \
  pkg-config git autoconf libtool automake \
  libgoogle-perftools-dev

## 📸 Installation Process – Step-by-Step Screenshots

---

### 🖥️ 1. Virtual Machines Setup
Creating and configuring Kali VMs for attacker and target in VirtualBox.

![VMs](images/1-VMs.png)

---

### 🔧 2. Updating Kali Linux
Keeping the system up to date before compiling.

![System Update](images/2-kali-update.png)

---

### 📦 3. Installing Dependencies
Installing all required libraries and tools via APT.

![Dependencies](images/3-Install-dependencies.png)

---

### ⬇️ 4. Downloading Snort, DAQ, and snort3_extra
Fetching the source packages from GitHub.

![Download Snort](images/4-Download-Snort.png)

---

### 🔧 5. Building and Installing DAQ
Compiling DAQ 3.0.19 with PCAP support.

![Install DAQ](images/5-Install-daq.png)

---

### ⚙️ 6. Configuring Snort with CMake
Preparing the Snort build with optional TCMalloc support.

![CMake Setup](images/6-Cmake-setup.png)

---

### 🧱 7. Building Snort
Compiling Snort 3 from source using `make -j$(nproc)`.

![Building Snort](images/7-Building-Snort.png)

---

### 📥 8. Installing Snort
Installing Snort binaries into the system.

![Installing Snort](images/8-Installing-Snort.png)

---

### ⚙️ 9. Configuring Snort
Validating configuration, environment, and DAQ path.

![Configuring Snort](images/9-Configuring-snort.png)

---

### 🧩 10. Compiling snort3_extra Modules
Building optional modules and Lua helpers.

![Compiling Snort Extra](images/10-Compiling-Snort-extra.png)

---

### 📦 11. Installing snort3_extra
Installing extended functionality and example rules.

![Installing Snort Extra](images/11-Installing-snort-extra.png)

---

### ✅ 12. Final Test – Snort Validated
Running Snort and validating proper DAQ setup.

![Testing Snort](images/12-Testing-snort.png)
