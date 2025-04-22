# 🛡️ Detecting and Resolving Unauthorized Remote Access with Snort 3

This project documents the process of installing, configuring, and testing **Snort 3.7.2.0** on **Kali Linux**, with full `DAQ` and `snort3_extra` support.  
It is based on my learning path from the **TryHackMe SOC1** module, focusing on **network traffic inspection** and **intrusion detection** in a virtualized lab environment.

---

## 🎯 Project Goals

- ✔️ Install Snort 3 from source
- ✔️ Enable DAQ with PCAP live capture
- ✔️ Compile and load `snort3_extra` modules
- ✔️ Prepare Snort for alerting on malicious activity
- ✔️ Document the entire build and testing process

---

## 🧰 Environment

- 🖥️ Virtualization: **VirtualBox**
- 🐧 OS: **Kali Linux 2025.1a**
- 💡 Setup: 2 VMs – `Kali-attacker` and `Kali-target`
- 🌐 Network: Host-only adapter for internal attack simulation

---

## ⚙️ Dependencies

Run the following commands before compiling Snort:

```bash
sudo apt update && sudo apt upgrade -y

sudo apt install -y \
  build-essential libpcap-dev libpcre3-dev libdumbnet-dev \
  bison flex zlib1g-dev liblzma-dev openssl libssl-dev \
  libnghttp2-dev autoconf libtool cmake pkg-config \
  libluajit-5.1-dev libhwloc-dev libmnl-dev \
  libgoogle-perftools-dev
🔧 Build Process (from source)
Download Snort, DAQ, and Snort Extra from GitHub

Compile & install DAQ (libdaq 3.0.19)

Build Snort 3 with --enable-tcmalloc

Set DAQ module path:

bash
Copia
Modifica
export SNORT_DAQ_PATH=/usr/local/lib/daq
Install snort3_extra modules

Run Snort with snort.lua config and test it

🖼️ Installation Process – Step-by-Step
1. Virtual Machines Setup

2. System Update

3. Installing Dependencies

4. Downloading Snort, DAQ, snort3_extra

5. Installing DAQ

6. Snort CMake Configuration

7. Building Snort

8. Installing Snort

9. Configuring Snort

10. Compiling snort3_extra

11. Installing snort3_extra

12. Testing Snort

✅ Result
🧠 Snort 3 compiled and installed

📡 PCAP support enabled via DAQ

📦 Extra modules ready (Modbus, S7Comm, AppID, etc.)

🔄 Configuration validated successfully

🔜 Next Steps
✍️ Write a custom Snort rule

🧪 Simulate a remote connection attempt (e.g., SSH brute force)

📊 Analyze and capture alerts via alert_fast, PCAPs, or Wireshark

📂 Organize detections under /rules and /pcap folders

👤 Author
Built during the TryHackMe SOC1 learning path
📚 Focused on real-world detection engineering using open-source IDS

Feel free to fork this project, contribute, or reach out!
