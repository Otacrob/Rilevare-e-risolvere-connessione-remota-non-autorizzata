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
