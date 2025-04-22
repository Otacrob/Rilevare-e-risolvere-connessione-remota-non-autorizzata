# 🛡️ Snort 3 IDS Lab – Detecting Unauthorized Remote Access

This project documents the full installation and configuration of **Snort++ (3.7.2.0)** on **Kali Linux**, compiled from source and enhanced with `DAQ` and `snort3_extra`.

This lab is based on the **TryHackMe SOC1** path and simulates a realistic environment for traffic monitoring and alerting.

---

## 🎯 Objectives

- Compile and install Snort 3 from source
- Enable packet capture support (DAQ + PCAP)
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
Creating and launching the virtual Kali machines.

![VMs](images/1-VMs.png)

---

### 2. System Update  
Updating the system to ensure a stable base before installing dependencies.

![System Update](images/2-kali-update.png)

---

### 3. Installing Dependencies  
Installing all the required libraries and development tools.

![Install Dependencies](images/3-Install-dependencies.png)

---

### 4. Downloading Snort, DAQ and Extras  
Cloning or downloading the Snort 3, DAQ 3.0.19 and snort3_extra source files.

![Download Snort](images/4-Download-Snort.png)

---

### 5. Compiling and Installing DAQ  
Building the DAQ modules (including `daq_pcap`) required by Snort.

![Install DAQ](images/5-Install-daq.png)

---

### 6. Configuring Snort with CMake  
Setting up the Snort 3 build using the included configuration script.

![CMake Setup](images/6-Cmake-setup.png)

---

### 7. Building Snort  
Compiling Snort from source using `make`.

![Building Snort](images/7-Building-Snort.png)

---

### 8. Installing Snort  
Installing Snort binaries and libraries on the system.

![Installing Snort](images/8-Installing-Snort.png)

---

### 9. Configuring Snort  
Linking the DAQ module path and preparing the Lua configuration file.

![Configuring Snort](images/9-Configuring-snort.png)

---

### 10. Compiling snort3_extra  
Building the additional inspection modules and protocol parsers.

![Compiling Extra](images/10-Compiling-Snort-extra.png)

---

### 11. Installing snort3_extra  
Installing the compiled extras into the system.

![Installing Extra](images/11-Installing-snort-extra.png)

---

### 12. Testing Snort  
Launching Snort with its Lua config and confirming DAQ functionality.

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
