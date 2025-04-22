# 🛡️ Snort 3 IDS Lab – Detecting Unauthorized Remote Access

This project documents the full installation and configuration of **Snort++ (3.7.2.0)** on **Kali Linux**, compiled from source and enhanced with `snort3_extra`.

This lab attempts to simulates a realistic environment for traffic monitoring and alerting.

---

## 🎯 Objectives

- Compile and install Snort 3 from source
- Enable packet capture support
- Install `snort3_extra` modules for advanced inspection
- Simulate remote access attempts between VMs
- Build a detection-ready IDS

---

## 🧪 Environment

| Component       | Setup                                   |
|----------------|------------------------------------------|
| OS              | Kali Linux (Attacker + Target VMs)      |
| Hypervisor      | VirtualBox                               |
| Network Mode    | Host-only Adapter                        |
| IDS Tool        | Snort++ 3.7.2.0                          |

---

## 📸 Installation Steps (Visual Walkthrough)

### 1. Virtual Machine Setup  
Creating two virtual environments based on Kali Linux (one for IDS and analysis purposes and the other to create network traffic attempting to connect to the first machine) and launching the defending machine.

![VMs](images/1-VMs.png)

---

### 2. System Update  
Updating Kali Linux to ensure compatibility and stability before building Snort and its dependencies.

![System Update](images/2-kali-update.png)

---

### 3. Installing Dependencies  
Installing all necessary development tools and libraries (compilers, network capture libs, LuaJIT, etc.) required for compiling Snort and DAQ from source.

![Install Dependencies](images/3-Install-dependencies.png)

---

### 4. Downloading Snort, DAQ and Extras  
Downloading and extracting the Snort 3, DAQ 3.0.19 and snort3_extra source files.

![Download Snort](images/4-Download-Snort.png)

---

### 5. Compiling and Installing DAQ  
Compiling and installing **libdaq version 3.0.19** from source. This step enables Snort to interface with different packet acquisition methods (like `pcap`, `afpacket`, `nfq`, etc.), which are essential for capturing and inspecting live network traffic.

![Install DAQ](images/5-Install-daq.png)

---

### 6. Configuring Snort with CMake  
Preparing the Snort 3 build environment using its custom configuration script to generate the required CMake structure and enable optional features such as tcmalloc — a high-performance memory allocator that reduces memory fragmentation and improves allocation speed, especially in multi-threaded environments. This optimization is particularly beneficial for Snort, which processes high volumes of packets and performs intensive rule-matching operations in real time.

![CMake Setup](images/6-Cmake-setup.png)

---

### 7. Building Snort  
Compiling the Snort engine source code into executable binaries using the generated CMake files.

![Building Snort](images/7-Building-Snort.png)

---

### 8. Installing Snort  
Installing the compiled Snort binaries and libraries into the system path (/usr/local) and updating the dynamic linker cache.

![Installing Snort](images/8-Installing-Snort.png)

---

### 9. Post-install Configuration  
Running `ldconfig` to refresh shared library links after installing Snort. This ensures all dependencies (like DAQ modules) are correctly linked when Snort is executed.

![Configuring Snort](images/9-Configuring-snort.png)

---

### 10. Compiling snort3_extra  
Building the snort3_extra modules which include additional protocol parsers and enhancements to extend Snort’s detection capabilities.

![Compiling Extra](images/10-Compiling-Snort-extra.png)

---

### 11. Installing snort3_extra  
Installing the compiled snort3_extra modules into the system to be available for use by Snort during runtime.

![Installing Extra](images/11-Installing-snort-extra.png)

---

### 12. Testing Snort  
Running Snort with the validated Lua configuration to ensure that the engine initializes correctly and the DAQ modules are loaded successfully.

![Testing Snort](images/12-Testing-snort.png)

---

## ✅ Final Outcome

- ✅ Snort 3 built and installed successfully
- ✅ DAQ with `pcap` module fully working
- ✅ snort3_extra modules installed and ready
- ✅ Lab environment prepared for live testing and rule development

---

## 📂 Next Steps

- ✍️ Write detection rules (e.g., SSH brute-force)
- 🧪 Simulate traffic between attacker and target VM
- 📊 Capture alerts and logs for analysis (PCAP / fast alert)
- 📁 Organize your project with `/rules`, `/pcap`, `/log` folders

---

## 👤 Author

This repository was created during the **TryHackMe SOC1 path** to demonstrate real-world IDS deployment from scratch.

Feel free to fork, contribute, or reach out!

⭐ **Star the repo** if this helped you set up your own Snort lab!
