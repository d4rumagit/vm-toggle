# vm-toggle

A shell script to easily toggle between VirtualBox and KVM on Linux.

VirtualBox cannot run when KVM is active because both require hardware virtualization (VT-x/AMD-V).  
This script unloads or loads the appropriate KVM modules, allowing you to switch modes without rebooting.

---

## Features
- Toggle between VirtualBox and KVM with one command
- Detects Intel or AMD CPUs automatically
- No reboot required
- Lightweight and minimal dependencies

---

## Requirements
- Linux (Debian, Ubuntu, ParrotOS, Arch, Fedora, etc.)
- `sudo` privileges
- VirtualBox and/or KVM/QEMU installed

---

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/d4rumagit/vm-toggle.git
   cd vm-toggle

    Copy the script to /usr/local/bin:

    sudo cp vm-toggle /usr/local/bin/vm-toggle
    sudo chmod +x /usr/local/bin/vm-toggle

Alternatively, you can create a symbolic link (so changes in the repo update automatically):

sudo ln -sf ~/vm-toggle/vm-toggle /usr/local/bin/vm-toggle

Usage

Run the script to toggle between VirtualBox and KVM:

vm-toggle

    If KVM is enabled, it will be disabled to allow VirtualBox to run.

    If KVM is disabled, it will be enabled for KVM/QEMU virtualization.

Customization

Some systems may use different kernel module names or configurations:

    Intel CPUs typically use kvm_intel

    AMD CPUs typically use kvm_amd

    Some distributions or kernels may only use kvm without a vendor-specific module

If your system uses different module names, edit the script and adjust the modprobe lines accordingly:

sudo nano /usr/local/bin/vm-toggle

Example for a custom module:

sudo modprobe -r kvm_custom
sudo modprobe kvm_custom

