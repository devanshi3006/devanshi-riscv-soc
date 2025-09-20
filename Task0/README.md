# 🔧 Task 0: System Check and Tool Installation

<div align="center">

![Assignment](https://img.shields.io/badge/Task-0-brightgreen?style=plastic)
![Tools_Setup](https://img.shields.io/badge/Tools-Successfully_Configured-blue?style=plastic)
![Linux](https://img.shields.io/badge/Platform-Ubuntu-red?style=plastic&logo=linux)

</div>

This task involves setting up a complete VLSI design workspace through systematic installation of essential EDA tools on Ubuntu Linux platform. The process includes downloading, compiling, and configuring software packages required for digital circuit design and verification workflows.

---

## 📑 **Navigation Guide**

- [🎯 Project Objective](#-project-objective)
- [🖥️ Hardware & Software Specifications](#️-hardware--software-specifications)  
- [⚡ Yosys Setup](#-yosys-setup---synthesis-engine)
- [🔍 Iverilog Configuration](#-iverilog-configuration---simulation-framework)
- [📈 GTKWave Deployment](#-gtkwave-deployment---signal-analyzer)
- [🛠️ Issue Resolution](#️-issue-resolution)
- [✔️ Functionality Testing](#️-functionality-testing)
- [📂 Project Organization](#-project-organization)

---

## 🎯 **Project Objective**

This documentation provides a comprehensive walkthrough for building a professional digital design environment from scratch. The setup process covers three fundamental tools that form the backbone of modern VLSI development workflows.

Each software package serves a specialized function in circuit design:
- **Yosys**: Converts RTL descriptions into gate-level representations
- **Iverilog**: Executes HDL simulations for design verification  
- **GTKWave**: Provides visual analysis of simulation results

---

## 🖥️ **Hardware & Software Specifications**

### System Configuration Details:

- **🔧 Operating System:** Ubuntu 24.04.3 LTS (minimum requirement: Ubuntu 20.04+)
- **💾 Memory Configuration:** 16GB DDR5 RAM (recommended minimum: 4GB+)
- **💽 Storage Capacity:** 100GB NVMe SSD (minimum required: 2GB+ free space)
- **⚙️ Processing Power:** 12 cores, 16 threads (minimum: dual-core processor)
- **🌐 Network Access:** Broadband connection available (required for package downloads)

### Additional Requirements:
- Root/sudo privileges for system-wide installation
- Active internet connection for repository access
- Terminal/command-line access

---

## ⚡ **Yosys Setup - Synthesis Engine**

### 📚 **Tool Overview**
Yosys serves as a comprehensive synthesis framework that transforms high-level Verilog descriptions into optimized gate-level implementations through advanced algorithms.

### 🔨 **Setup Procedure**

```bash
# Step 1: Update package repositories
sudo apt-get update && sudo apt-get upgrade -y

# Step 2: Download Yosys source code
git clone https://github.com/YosysHQ/yosys.git
cd yosys

# Step 3: Initialize Git submodules (important for ABC solver)
git submodule update --init

# Step 4: Install build dependencies
sudo apt-get install build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev

# Step 5: Configure build environment for GCC
make config-gcc

# Step 6: Compile the source code
make -j$(nproc)

# Step 7: Install to system directories
sudo make install
```

### 🏁 **Successful Installation Check**

```bash
yosys
```

<img width="1123" height="281" alt="Screenshot from 2025-09-20 14-51-16" src="https://github.com/user-attachments/assets/91ef666a-4185-44aa-88dc-5aaa466759d5" />

**Confirmation:** Yosys interactive shell opens with build information and command prompt.

---

## 🔍 **Iverilog Configuration - Simulation Framework**

### 📚 **Tool Overview**
Icarus Verilog provides comprehensive IEEE-1364 standard compliance for both behavioral modeling and synthesizable RTL design simulation.

### 🔨 **Setup Procedure**

```bash
# Refresh package database
sudo apt-get update

# Install Iverilog package from repository
sudo apt-get install iverilog -y
```

### 🔎 **Testing the Installation**

```bash
iverilog
```

<img width="920" height="495" alt="image" src="https://github.com/user-attachments/assets/e7ce01f8-fdef-4600-bde5-ee833aa979b5" />

**Output Verification:** Command displays help information and usage syntax confirming proper setup.

---

## 📈 **GTKWave Deployment - Signal Analyzer**

### 📚 **Tool Overview**
GTKWave provides advanced waveform visualization capabilities with comprehensive support for various simulation output formats and interactive analysis features.

### 🔨 **Setup Procedure**

```bash
# Update system package list
sudo apt-get update

# Install GTKWave waveform viewer
sudo apt install gtkwave -y
```

### 🚀 **Launch Verification**

```bash
gtkwave
```

<img width="1166" height="816" alt="Screenshot from 2025-09-20 14-55-12" src="https://github.com/user-attachments/assets/1f6e2f4e-d5ba-41c3-9738-43d6e8d34011" />

**Application Launch:** GTKWave graphical interface opens successfully with file browser dialog.

---

## 🛠️ **Issue Resolution**

### Common Problems & Their Solutions:

**🔧 Yosys Compilation Issues:**
- **Missing submodules:** Run `git submodule update --init` before building
- **Dependency errors:** Ensure all build-essential packages are installed
- **Permission problems:** Use sudo for system-wide installation commands

**🔍 Iverilog Installation Problems:**
- **Package not found:** Update repository cache with `sudo apt-get update`
- **Broken dependencies:** Try `sudo apt-get install -f` to fix broken packages
- **Version conflicts:** Remove old versions before installing new ones

**📈 GTKWave Setup Difficulties:**
- **Display issues:** Ensure X11 forwarding is enabled for remote systems
- **GUI not launching:** Check if desktop environment is properly configured
- **File association problems:** Manually associate .vcd files with GTKWave

### 💡 **Recommended Practices**

- Always update package repositories before installing new software
- Verify system requirements before beginning installation process
- Keep build logs for troubleshooting compilation errors  
- Test each tool individually after installation completion

---

## 🧪 **Final Testing & Verification**

### Tool Validation Commands

```bash
# Check Yosys build version
yosys --version

# Display Iverilog compiler info  
iverilog -v

# Show GTKWave application details
gtkwave --version
```

### 🎯 **Installation Summary**

**🔧 EDA Toolchain Status:**

- **⚡ Yosys (v0.57+153):** ✅ Successfully compiled and installed - Ready for RTL synthesis operations
- **🔍 Iverilog (v12.0):** ✅ Package installation completed - HDL simulation capabilities active
- **📈 GTKWave (v3.3.116):** ✅ Application deployed successfully - Waveform analysis tools available

**🎉 VLSI Development Environment is Operational!**
